## III .Naif Bayes sınıflaması

### Bayes kuralının en kullanışlı uygulamalarından biri de Naif Bayes sınıflandırıcısıdır.

Bayes sınıflandırıcısı, metin belgeleri gibi nesneleri iki veya daha fazla sınıfa sınıflandırmak için kullanılabilecek bir makine öğrenme tekniğidir. Sınıflandırıcı, doğru sınıfların verildiği bir dizi eğitim verisini analiz ederek eğitilir.

Naif Bayes sınıflandırıcısı, bir dizi farklı gözlem verilen sınıfların olasılıklarını belirlemek için kullanılabilir. Modeldeki varsayım, özellik değişkenlerinin sınıfa göre koşullu olarak bağımsız olduğu varsayımıdır (bu derste koşullu bağımsızlığın anlamını tartışmayacağız. Amaçlarımız için, sınıflandırıcıyı oluşturmak için koşullu bağımsızlığı kullanabilmek yeterlidir).

### Gerçek dünya uygulaması: spam filtreleri

Naif Bayes sınıflandırıcısının fikrini göstermek için çalışan bir örnek olarak spam e-posta filtresi kullanacağız. Bu nedenle, sınıf değişkeni bir iletinin spam olup olmadığını (veya “önemsiz e-posta”) veya yasal bir ileti olup olmadığını gösterir. Mesajdaki kelimeler özellik değişkenlerine karşılık gelir, böylece modeldeki özellik değişkenlerinin sayısı mesajın uzunluğuna göre belirlenir.

> Not
>
> ## Neden buna “Naive=Basit, saf” diyoruz
>
> Bir örnek olarak spam filtreleri kullanmak, kelimelerin birbiri ardına bir kelime seçerek üretildiğini düşünmektir, böylece kelimenin seçimi sadece mesajın spam mı yoksa spam olmayan mı olduğuna bağlıdır. Bu, sürecin kaba bir basitleştirilmesidir, çünkü bitişik kelimeler arasında bir bağımlılık olmadığı ve kelimelerin sırasının önemi yoktur. Aslında bu yönteme bu yüzden Naive deniyor.

Yukarıdaki fikir, genellikle mesajın sınıfının (spam veya ham:spam olmayan) kelimeler üzerinde etkisi olan tek faktör olduğu aşağıdaki çizim kullanılarak tasvir edilmiştir.

![spam veya-jambon](https://course.elementsofai.com/static/3_3_spam-or-ham.1f831dc4.svg)

Basitliğine yada Naiveliğine rağmen, NaiveBayes yöntemi pratikte çok iyi çalışma eğilimindedir. Bu, istatistiklerde sıkça söylenenlerin “tüm modeller yanlıştıt, ancak bazıları faydalıdır” derken ne anlama geldiğinin güzel bir örneğidir (aforizma genellikle istatistikçi [George EP Box'a](https://en.wikipedia.org/wiki/George_E._P._Box) atfedilir ).

### Parametreleri tahmin etmek

Başlamak için, spam için önceki-prior  ihtimalleri belirtmemiz gerekir (spam olmayanlara karşı). Basit olması için, bunun 1: 1 olduğunu varsayalım; bu, gelen mesajların ortalama yarısının spam olduğu anlamına gelir (gerçekte, spam miktarı muhtemelen daha yüksektir).

Olabilirlik oranlarımızı elde etmek için, ortaya çıkan herhangi bir kelime için iki farklı olasılık gerekir: biri spam mesajlarında diğeri spam olmayan mesajlarında.

İki sınıf için kelime dağılımları en iyi şekilde bazı spam mesajları ve meşru mesajları içeren gerçek eğitim verilerinden tahmin edilir. En basit yol, her kelimenin kaç kez, abaküs, akasya, ..., zurg, verilerde göründüğünü saymak ve sayıyı toplam kelime sayımına bölmektir.

Bu fikri göstermek için, elimizde biraz spam ve biraz jambon bulunduğunu varsayalım. Bir e-posta grubunuzu iki dosyaya kaydederek bu verileri kolayca elde edebilirsiniz.

İki mesaj sınıfında aşağıdaki kelimelerin (diğer tüm kelimelerin yanı sıra) tekrarlanma sayısını hesapladığımızı varsayın:

| sözcük           | Spam  | Spam olmayan |
| :--------------- | :---- | :----------- |
| milyon           | 156   | 98           |
| dolar            | 29    | 119          |
| adclick          | 51    | 0            |
| konferanslar     | 0     | 12           |
| **Genel Toplam** | 95791 | 306438       |

Örneğin, bir spam mesajındaki bir kelimenin milyon olabileceği gibi, örneğin, 95791’den yaklaşık 156 olduğunu ve kabaca spamlarda 614’de 1 ve 3127 de 1 non-spam mesajında ile aynı olduğunu tahmin edebiliyoruz. Bu olasılık tahminlerinin her ikisi de küçüktür, 500'de 1'den daha azdır, ancak daha önemlisi, öncekileri ikinciden daha yüksektir: 614'te 1, 3127'de 1'den yüksektir. Bu, birinci oran olan bölünme oranının, bölü ikinci oran, birinci orandan fazla. Daha kesin olmak gerekirse, oran (1/614) / (1/3127) = 3127/614 = 5.1'dir (bir ondalık basamağa yuvarlanır).

Bu bölümdeki matematiği takip etmekle ilgili herhangi bir probleminiz varsa, daha önce verdiğimiz notları kullanarak aritmetiği fraksiyonlarla yenilemelisiniz ( *Ihtimaller ve Olasılık* bölümündeki *Ihtimaller bölümüne bakınız ).

> Not
>
> ## Sıfır sorun demektir
>
> Olasılıkları doğrudan sayımlardan tahmin etmedeki bir sorun, sıfır sayımların sıfır hesaplamaya yol açmasıdır. Bu, sınıflandırıcının performansı için oldukça zararlı olabilir - kolayca arka oranların 0/0 olduğu, saçma sapan durumlara yol açar. En basit çözüm, tüm olasılık tahminleri için küçük bir alt sınır kullanmaktır. Örneğin 1/100000 değeri işi yapar.

Yukarıdaki mantığı kullanarak, sıfırı kullanmak zorunda kalmadan tüm olası kelimelerin olasılık oranını belirleyebiliriz, bize aşağıdaki olasılık oranlarını vererek:

| sözcük       | olabilirlik oranı |
| :----------- | :---------------- |
| milyon       | 5.1               |
| dolar        | 0.8               |
| adclick      | 53,2              |
| konferanslar | 0.3               |

Şimdi yeni mesajları sınıflandırmak için bu yöntemi uygulamaya hazırız.

### Örnek: Spam mı yoksa Spam değil mi?

Önceden tahmin edilen oranlara ve olabilirlik (likelihood ) oranlarına sahip olduğumuzda, tıbbi tanı durumunda halihazırda uyguladığımız Bayes kuralını örneğimiz olarak uygulamaya hazırız. Akıl yürütme, daha önce olduğu gibi devam eder: spam oranlarını olasılık oranıyla çarparak güncelleriz. Kendimize prosedürü hatırlatmak için, en baştan tek kelimeyle deneyelim. Yukarıda belirtilen öncelik ihtimalleri için yukarıda belirtildiği gibi, oran 1: 1'i kullanmalısınız.

### 

### Alıştırmalar için ilgili sayfaya gidebilirsiniz.

https://course.elementsofai.com/3/3



To handle the rest of the words in a message, we can use exactly the same procedure. The posterior odds after one word, which you calculated in the previous exercise, will become the prior odds for the next word, and so on.

### 

### Alıştırmalar için ilgili sayfaya gidebilirsiniz.

https://course.elementsofai.com/3/3