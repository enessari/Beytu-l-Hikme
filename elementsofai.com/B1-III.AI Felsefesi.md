## III .AI Felsefesi

### **“Yapay zeka” teriminin doğası, zekice davranışın bir zihnin varlığını gerektirip gerektirmediğine veya gerektirdiğine ve bilincin hesaplama olarak tekrarlanabileceğine dair felsefi sorular getirir.**

### Turing testi

[Alan Turing](https://en.wikipedia.org/wiki/Alan_Turing) (1912-1954) bir İngiliz matematikçi ve mantıkçısı. Haklı olarak bilgisayar biliminin babası olarak kabul edilir. Turing, zeka ve düşünce ile onları makinelerle simüle etme ihtimalini büyüledi. Turing'in AI'ya en önemli katkısı, daha sonra [Turing testi](https://en.wikipedia.org/wiki/Turing_test) olarak bilinen taklit oyunudur .

Testte, bir insan sorgulayıcı, yazılı mesaj alışverişi yaparak (bir sohbette) A ve B olmak üzere iki oyuncu ile etkileşime girer. Eğer sorgulayıcı hangi oyuncunun (A veya B) bir bilgisayar olduğunu ve hangisinin bir insan olduğunu belirleyemezse, bilgisayarın testi geçtiği söylenir. Argüman, eğer bir bilgisayar genel bir doğal dil konuşmasında bir insandan ayırt edilemezse, o zaman insan düzeyinde zekâya ulaşmış olması gerektiğidir.

![Turing testi](https://course.elementsofai.com/static/1_3_turing-test.76dd06f5.svg)



Turing'in testten kastettiği, Forrest Gump'ın aforizmasına çok benziyor: “aptal, aptallık yapandır”. Turing'in sürümü “zekinin dediği gibi, zeki” olacaktır. Başka bir deyişle, bir davranışını gözlemleyerek başka bir akıllı varlıktan ayırt edilememesi durumunda, akıllıdır. Turing davranış setini tartışmaya dahil etti, böylece sorgulayıcı onun kararını görünüşe dayandıramazdı.

### Bir problem: insan gibi olmak zeki olduğun anlamına mı geliyor?

Turing testinin istihbarat testi olarak eleştirilmesi, bilgisayarın zeki olup olmadığından daha fazla bir insan gibi davranıp davranmadığını ölçebileceği yönündedir. Test gerçekten konuyu değiştiren, birçok yazım hatası yapan ve bazen hiç cevap vermeyi reddeden bilgisayar programları tarafından “geçti”. Meşhur bir örnek, 13 yaşında Ukraynalı bir çocuk olan [Eugene Goostman](https://en.wikipedia.org/wiki/Eugene_Goostman) , sürekli şaka yaparak soruları cevaplamaktan kaçınmaya çalışan ve konuyu evcil hayvan guineapig'ine çevirmekten kaçınmaya çalışıyor. İşte [Scott Aaronson'ın blogundan](https://www.scottaaronson.com/blog/?p=1858) Eugene Goostman ile örnek bir sohbete kısa bir bölüm :

### Eugene bir bilgisayar mı yoksa bir insan mı?

**Soru** : Bir devenin kaç bacağı var?

**Eugene:** 2 ile 4 arasında bir şey. Belki, üç? :-))) Bu arada, uzmanlığınızı hâlâ bilmiyorum - ya da muhtemelen kaçırdım?

**Soru:** Bir kırkayak kaç bacağı var?

**Eugene:** Sadece iki, ama Çernobil mutantları beşe kadar alabilir. Beni kandırman gerektiğini biliyorum.

**Soru:** Hayır, bir sohbetçi olmadığını bilmem gerekiyor. Lütfen soruyu basitçe cevaplayın: Bir karıncanın kaç ayağı var?

**Eugene:** 2 ile 4 arasında bir şey. Belki, üç? :-))) Ah, ne verimli bir konuşma ;-)

**Soru:** Neden bu kadar temel sorular sorduğumu anlıyor musunuz? "Blade Runner" filminde olduğu gibi, sizi en kısa sürede bir robot olarak maskesini çıkarmaya çalıştığımın farkında mısın?

**Eugene:** ... bekle

*Gerçekte bir bilgisayar programı olan Eugene Goostman, 30 yargıçtan 10'unu gerçek bir insan olduğunu düşünerek kandırdı.*

![çince odalı](https://course.elementsofai.com/static/1_3_chinese-room.2e4e0257.svg)



### Çin oda tartışması

Zekanın zekice davranışıyla aynı olduğu fikri bazılarına meydan okuyor. En iyi bilinen karşı tartışma John Searle'ın [Çin Odası](http://www.iep.utm.edu/chineser/) düşünce deneyidir. Searle, Çince bilmeyen bir kişinin bir odada kilitli olduğu bir deneyi açıklar. Odanın dışında, odanın içinde Çince yazılmış notları posta yuvasından geçirebilen bir kişi var. Odanın içindeki kişiye, dışarıdan aldığı notlara cevap vermek için ayrıntılı talimatlar bulabileceği büyük bir el kitabı verilir.

Searle, odanın dışındaki kişi, Çince konuşan başka biriyle konuşmakta olduğu izlenimini edinse bile, odanın içindeki kişinin Çince anlamadığını savundu. Aynı şekilde, argümanı, bir makine akıllı bir şekilde davransa bile, örneğin, Turing testini geçerek devam eder, zeki olduğunu veya bir insanın sahip olduğu gibi bir “aklı” olduğunu takip etmez. “Akıllı” kelimesi aynı zamanda “bilinçli” kelimesiyle de değiştirilebilir ve benzer bir tartışma yapılabilir.

### Kendi kendini süren bir araba akıllı mıdır?

Çin Odası argümanı, istihbaratın otomatikleştirilebilecek küçük mekanik talimatlara bölünebileceği fikrine aykırıdır.

Kendi kendini süren bir araba, otomatik hale getirilebilecek bir istihbarat unsurunun (araba süren) bir örneğidir. Çin Odası argümanı,  bunun gerçekten akıllıca bir düşünce olmadığını öne sürüyor: öyle gözüküyor. “Valiz kelimeler” konusundaki yukarıdaki tartışmaya geri dönersek, arabadaki AI sistemi çevresini görmüyor veya anlamıyor ve bir insanın nasıl gördüğü, anladığı ve bildiği gibi güvenli bir şekilde nasıl sürüleceğini bilmiyor . Searle'a göre, bu, sistemin akıllı davranışının esasen akıllı olmaktan farklı olduğu anlamına gelir.

### Uygulamada felsefe ne kadar önemlidir?

Zekanın, doğal ya da yapay ve bilincin tanımı son derece kaçınılmaz görünmektedir ve görünüşte hiç bitmeyen bir konuşmaya yol açmaktadır. Bir entelektüel şirkette, bu tartışma oldukça zevkli olabilir (uygun şirket yokluğunda, Hofstadter'ın The Mind's I ve Dennett gibi kitapları teşvik edilebilir).

Bununla birlikte, [John McCarthy'nin](http://jmc.stanford.edu/articles/aiphil/aiphil.pdf) işaret ettiği gibi , AI felsefesi “AI araştırmalarının uygulanmasında, bilim felsefesinin genel olarak bilimin uygulamalarından daha fazla etkisinin olması muhtemel değildir” şeklindedir. pratik problemleri çözmede zeki olup olmadıklarını sormadan ya da sanki oldukları gibi davranmalarını isteyin.

> Anahtar terminoloji
>
> ## Genel vs dar anlamda AI
>
> Haberleri okurken, "genel" ve "dar" AI terimlerini görebilirsiniz. Peki bunlar ne anlama geliyor? Dar AI, bir görevi yerine getiren AI anlamına gelir. Genel AI veya Yapay Genel Zeka (AGI), herhangi bir entelektüel görevi yerine getirebilecek bir makine anlamına gelir. Bugün kullandığımız bütün AI yöntemleri dar AI altında kalmaktadır, genel AI ise bilim kurgu alanındadır. Aslında, ideal AGI, AI araştırmacıları tarafından tüm çabalarına rağmen 50 yıldan fazla bir süredir gelişme göstermediği için terkedilmiştir. Buna karşılık, dar AI sıçrama ve sınırlarda ilerleme kaydeder.
>
> ## Güçlü vs zayıf AI
>
> İlgili bir ikilik, "güçlü" ve "zayıf" AI'dir. Bu, Searle tarafından vurgulanan, akıllı olmak ve akıllıca davranmak arasındaki yukarıdaki felsefi ayrımdan kaynaklanmaktadır. Güçlü AI, gerçekten zeki ve bilinçli bir “akıl” anlamına gelir. Zayıf AI aslında sahip olduğumuz şeydir, yani “sadece” bilgisayar olmasına rağmen akıllı davranışlar gösteren sistemler.