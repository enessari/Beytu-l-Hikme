## II .AI ile problem çözme

### AI'nın tarihine bi bakalım: aramadan başlayarak

AI muhtemelen bilgisayar bilimi kadar eskidir. Bilgisayarlara girmeden çok önce insanlar otomatik akıl yürütme ve istihbarat olasılığını düşünüyorlardı. Bölüm 1’de de belirttiğimiz gibi, bu soruyu düşünen en büyük düşünürlerden biri Alan Turing’di. Turing testine ek olarak, AI'ya ve daha genel olarak bilgisayar bilimlerine olan katkıları, hesaplanabilecek herhangi bir şeyin (= sayılar veya diğer semboller kullanılarak hesaplanan) otomatikleştirilebileceği görüşünü içerir.

> Not
>
> ## 2. Dünya Savaşı'nı kazanmaya yardımcı olmak
>
> Turing, hesaplanabilir her şeyi hesaplayabilen çok basit bir cihaz tasarladı. Cihazı Turing makinesi olarak bilinir. Pratik olarak kullanışlı olmayan teorik bir model olsa da, programlanabilir bilgisayarların icat edilmesine yol açıyor: ne yapmak için programlandıklarına bağlı olarak farklı görevleri yerine getirmek için kullanılabilecek bilgisayarlar. 
>
> Dolayısıyla her görev için farklı bir cihaz oluşturmak yerine, aynı bilgisayarı birçok görev için kullanıyoruz. Programlama fikri budur. Bugün bu buluş önemsiz geliyor, ancak Turing'in günlerinde bu fikirden uzaktı. Programlanabilir ilk bilgisayarlardan bazıları, II. Dünya Savaşı sırasında, Turing'in de kişisel olarak dahil olduğu bir proje olan Alman gizli kodlarını kırmak için kullanıldı.

Yapay Zeka terimi, sıklıkla AI'nın Babası olarak da adlandırılan John McCarthy'ye (1927-2011) atfedilir, ancak aslında kendisi terim ile akla gelmetyi reddeder. Yine de, ortaya çıkan alanın adı olarak benimsenmesinde kendisi etkili oldu. Terim , McCarthy tarafından düzenlenen ve 1956'da New Hampshire'daki Dartmouth Koleji'nde düzenlenen [Dartmouth konferansı](https://en.wikipedia.org/wiki/Dartmouth_workshop) olarak bilinen bir yaz semineri konusu olarak seçildiğinde belirlendi . Semineri düzenleme teklifinde, McCarthy, Turing'in otomatik hesaplama konusundaki tartışmasına devam etti. Teklif aşağıdaki önemli ifadeyi içermektedir:

> Not
>
> ## John McCarthy'nin AI ile ilgili kilit açıklaması
>
> “Çalışma, öğrenmenin her yönünün ya da zekanın herhangi bir özelliğinin prensipte o kadar kesin olarak tanımlanabileceği ve onu simüle etmek için bir makinenin yapılabileceği varsayımına dayanarak devam etmektir.”

Başka bir deyişle, herhangi bir zeka unsuru küçük adımlara bölünebilir, böylece her adım bir bilgisayar programı olarak yazılabilecek kadar basit ve “mekanik” olur. Bu ifade bugün hâlâ bir varsayımdı ve bu gerçekten doğru olduğunu kanıtlayamayacağımız anlamına geliyor. Bununla birlikte, AI ile ilgili düşünme şeklimiz söz konusu olduğunda, bu fikir kesinlikle temeldir. Örneğin, McCarthy'nin Searle Çin Odası ruhundaki herhangi bir tartışmayı atlamak istediğini gösteriyor: zekâ, onu uygulayan sistem sadece bir programı izleyen bir bilgisayar olsa bile zekadır.

### Arama ve Oyunlar, AI araştırmalarında neden merkezinde?

1950'lerde pratik AI algoritmaları ile deney yapmanın mümkün olduğu düzeyde bilgisayarlar geliştikçe, en belirgin AI problemleri (Nazi kodlarını kırmanın yanı sıra) oyunlardı. Oyunlar, kolayca resmileştirilebilecek uygun bir sınırlı alan sağlamıştır. Dama, satranç ve son zamanlarda oldukça belirgin olan tahta oyunları (en az 2500 yıl önce Çin'den gelen oldukça karmaşık bir strateji oyunudur) sayısız araştırmacıya ilham verdi ve yapmaya devam etti.

Oyunlarla yakından ilgili, arama ve planlama teknikleri, AI'nın 1960'larda büyük ilerlemelere yol açtığı bir alandı: Minimax algoritması veya Alpha-Beta Pruning gibi isimler içeren algoritmalar, daha sonra hala oyun AI oynamak için temel oluşturuyordu. Elbette yıllar içinde daha gelişmiş değişkenler önerilmiştir. Bu bölümde oyunlar ve planlama problemlerini kavramsal olarak ele alacağız.