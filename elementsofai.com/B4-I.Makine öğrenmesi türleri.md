## I.Makine öğrenmesi türleri

### El yazısı rakamları, neden makine öğrenmeyi kullandığımızı tartışırken sıkça kullanılan klasik bir durumdur ve istisna yapmayacağız.

Aşağıda, çok kullanılan MNIST veri setinden elle yazılmış görüntülerin örneklerini görebilirsiniz.

![mnist](https://course.elementsofai.com/static/4_1-mnist.9fe2c1b5.svg)

Her görüntü üzerinde doğru etiket (yazıcının yazması gereken rakam) gösterilir. Bazı "doğru" sınıf etiketlerin bazılarının sorgulanabilir olduğuna dikkat edin: örneğin soldan ikinci resme bakın: bu gerçekten 7 mi, yoksa 4 mü?

> Not
>
> ## MNIST - Bu nedir?
>
> Her makine öğrenen öğrenci MNIST veri setini bilir. Kısaltmanın ne anlama geldiğini daha az bilir. Aslında, M'nin Modifiye anlamına geldiğini ve NIST'in Ulusal Standartlar ve Teknoloji Enstitüsü'nü temsil ettiğini söyleyebilmek için araştırmamız gerekti. Muhtemelen ortalama bir makine öğrenim uzmanının bilmediği şimdi bir şey biliyorsunuz!

En yaygın makine öğrenme problemlerinde, bir kerede tam olarak bir sınıf değer doğrudur. Bu, MNIST durumunda da geçerlidir, ancak söylediğimiz gibi, doğru cevabı çoğu zaman söylemek zor olabilir. Bu tür bir problemde, bir örneğin aynı anda birden fazla sınıfa (veya hiçbirine) ait olması mümkün değildir. Elde etmek istediğimiz, bir AI yöntemi, yukarıdakiler gibi bir resim verilerini ve otomatik olarak doğru etiketi (0 ile 9 arasında bir sayı) yayar.

> Not
>
> ## Problem nasıl çözülmez
>
> Bir otomatik rakam tanıyıcı prensip olarak aşağıdakiler gibi kuralları yazarak manuel olarak oluşturulabilir:
>
> - siyah pikseller çoğunlukla tek bir döngü biçimindeyse, etiket 0 olur
> - eğer siyah pikseller kesişen iki ilmek oluşturuyorsa, etiket 8'dir.
> - Siyah pikseller çoğunlukla şeklin ortasındaki düz bir dikey çizgide ise, etiket 1'dir.
>
> ve bunun gibi… 
> Bu yöntem, AI yöntemlerinin çoğunlukla 1980'lerde (“uzman sistemler” olarak adlandırılıyor) nasıl geliştirildiğiydi. Ancak, rakam tanıma gibi basit bir görev için bile, bu tür kuralların yazılması çok zahmetlidir. Aslında, yukarıdaki örnek kuralların programlama ile uygulanacak yeteri kadar spesifik olamaz - “çoğunlukla”, “döngü”, “satır”, “orta” vb. İle ne demek istediğimizi tam olarak tanımlamamız gerekir. 



### Üç çeşit makine öğrenmesi

Makine öğreniminin kökleri istatistiktedir **ve verilerden bilgi çıkarma** sanatı olarak da düşünülebilir . Özellikle, iki yüzyıldan daha eski olan (!) Doğrusal regresyon ve Bayesian istatistikleri gibi yöntemler, makine öğreniminin merkezinde bugün bile var. Daha fazla örnek ve kısa bir tarih için, [makine öğreniminin zaman çizelgesine](https://en.wikipedia.org/wiki/Timeline_of_machine_learning)bakın (Wikipedia).

Makine öğrenmesi alanı, problemlerin saldırısına uğrayan yoğun sorun türlerine göre genellikle alt alanlara bölünür. Kaba bir sınıflandırma aşağıdaki gibidir:

**Denetimli öğrenme** : (**Supervised**)Bir giriş, örneğin trafik işaretli bir fotoğraf verilmiştir ve görev, örneğin hangi trafik işaretinin resimde (hız sınırı, dur işareti vb.) Olduğunu doğru çıktıyı veya etiketi tahmin etmektir. En basit durumlarda, cevaplar evet / hayır şeklindedir (bu *ikili sınıflandırma problemleri olarak adlandırıyoruz* ).

**Denetimsiz öğrenme** : (**Unsupervised**) Etiket veya doğru çıktı yok. Görev, verinin yapısını keşfetmektir: örneğin, “kümeler” oluşturmak üzere benzer öğeleri gruplamak veya verileri az sayıdaki önemli “boyutlara” azaltmak. Veri görselleştirme, denetimsiz öğrenme olarak da kabul edilebilir.

**Takviye öğrenme** : (**Reinforcement**) Genellikle kendi kendini süren bir araba gibi bir AI aracısının bir ortamda çalışması gereken durumlarda ve iyi veya kötü seçimler hakkında geri bildirimin biraz gecikmeli olarak mevcut olduğu durumlarda kullanılır. Sonuçlara yalnızca oyunun sonunda karar verilebilecek oyunlarda da kullanılır.

Kategoriler biraz örtüşüyor ve bulanık, bu nedenle belirli bir yöntem bazen bir kategoride yerleştirmek zor olabilir. Örneğin, adından da anlaşılacağı gibi yarı denetimli **öğrenme** , kısmen denetlenir ve kısmen Denetimsizdir.

> Not
>
> ## sınıflandırma
>
> Makine öğrenmesi söz konusu olduğunda, öncelikle denetimli öğrenmeye ve özellikle de sınıflandırma görevlerine odaklanacağız. Sınıflandırmada, bir trafik işaretinin fotoğrafı gibi girdileri gözlemliyoruz ve işaret türü (hız sınırı 80 km / s, yaya geçidi, dur işareti, vb.) Gibi “sınıfını” çıkarmaya çalışıyoruz. Diğer sınıflandırma görevlerine örnekler: sahte Twitter hesaplarının tanımlanması (giriş, takipçilerin listesini ve hesabı takip etmeye başladıkları oranı ve sınıfın sahte veya gerçek hesap olduğunu) ve el yazısı rakam tanımanın (giriş bir görüntü, sınıf 0, ..., 9).

![denetimli öğrenme](https://course.elementsofai.com/static/4_1_supervised-learning.093ef920.svg)

### İnsanlar makinelere öğretiyor : denetimli öğrenme

Sınıflandırmayı yapmak için kesin kuralları elle yazmak yerine, denetlenen makine öğrenimindeki önemli nokta, birkaç örnek almak, her birini doğru etiketle etiketlemek ve doğru etiketi otomatik olarak tanımak için bir AI yöntemini “eğitmek” için kullanmaktır. eğitim örnekleri için ve (en azından umulur) diğer resimler için. Bu elbette doğru etiketlerin sağlanmasını gerektirir, bu yüzden denetimli öğrenme hakkında konuşuyoruz. Doğru etiketleri sağlayan kullanıcı, öğrenme algoritmasını doğru cevaplara yönlendiren ve sonunda algoritmanın bağımsız olarak üretebilmesi için bir süpervizördür.

Bir sınıflandırma probleminde doğru etiketin nasıl tahmin edileceğini öğrenmenin yanı sıra, denetlenen öğrenme, öngörülen sonucun bir sayı olduğu durumlarda da kullanılabilir. Örnekler, reklam içeriğine dayalı olarak bir Google reklamını tıklayacak olan kişilerin sayısını ve kullanıcının önceki çevrimiçi davranışına ilişkin verileri tahmin etmeyi, yol koşullarına ve hız sınırına dayalı trafik kazalarının sayısını tahmin etmeyi veya emlak satış fiyatını tahmin etmeyi içerir. yeri, büyüklüğü ve durumu. Bu sorunlara *regresyon* denir . Muhtemelen, *regresyon* için hala çok popüler bir teknik olan *lineer regresyon* terimini tanıyorsunuzdur .

> Not
>
> ## Örnek
>
> Dairede satış verilerinden oluşan bir veri kümemiz olduğunu varsayalım. Her bir satın alım için, dairenin büyüklüğü ile birlikte metrekare olarak (veya isterseniz metrekare), ve yatak odası sayısı, yapım yılı, durum (bir “felaketten” “hüzme ve yayılma” ya kadar ölçeklendirme). Daha sonra bu özellikleri temel alarak satış fiyatını öngören bir regresyon modelini eğitmek için makine öğrenmeyi kullanabiliriz. [Burada gerçek hayattan bir örnek](http://kannattaakokauppa.fi/#/en/) görün

![fiyat-gayrimenkul](data:image/svg+xml;base64,PHN2ZyBpZD0iTGF5ZXJfMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2aWV3Qm94PSIwIDAgNzEwIDM2MC45Ij4KICAgIDxzdHlsZT4KICAgICAgICAuc3Qwe2ZpbGw6I2ZmZn0uc3Qxe2ZpbGw6Izg1YTBmZn0uc3Qye2ZpbGw6IzM0MmQ3MX0uc3Qze2ZpbGw6Izc3OTllYn0uc3Q0e2ZpbGw6IzgwODBkOH0uc3Q1e29wYWNpdHk6Ljh9LnN0NntmaWxsOiM0NzQ3YTF9LnN0N3tmaWxsOiNmZGJmODR9LnN0OHtvcGFjaXR5Oi4yNjY0fS5zdDl7ZmlsbC1ydWxlOmV2ZW5vZGQ7Y2xpcC1ydWxlOmV2ZW5vZGQ7ZmlsbDojMzQyZDcxfS5zdDEwe29wYWNpdHk6LjV9LnN0MTF7ZmlsbDojNTBiOWU4fQogICAgPC9zdHlsZT4KICAgIDx0aXRsZT4KICAgICAgICAzXzEtb2RkcwogICAgPC90aXRsZT4KICAgIDxwYXRoIGNsYXNzPSJzdDAiIGQ9Ik01NDEuNyAyNTguOFYyNzEuOWgyMy42di0yMC40aDkzdjQ0LjZINzEwaC01MS43djJINzEwdjYyLjhINTYzLjJ2LTQ2LjZoLTI1LjV2NDYuNkg0NTV2LTU3LjdoLjF2LTcxLjVoODYuNnYyNy4xIi8+CiAgICA8cGF0aCBjbGFzcz0ic3QxIiBkPSJNNTAwLjYgMzE0LjJINDgwLjh2MjQuN0g1MTEuOXYtMjQuN3pNNDc1IDI1MC4xaDQyLjd2MzMuM0g0NzV6TTU4OS4xIDMxNC4yaDQyLjd2MzMuM2gtNDIuN3oiLz4KICAgIDxwYXRoIGNsYXNzPSJzdDIiIGQ9Ik01MzcuOCAzMTQuM2gyNS41djQ2LjZoLTI1LjV6TTQ1NS4yIDIyNS43djZoODYuNXYtNy4yaC04Ni41ek01NjUuMyAyNDUuNnY1LjloOTN2LTcuMmgtOTN6TTY1OC4zIDI5Mi4ydjUuOUg3MTB2LTcuMmgtNTEuN3pNNTQxLjcgMjY1Ljl2NmgyMy42di03LjJoLTIzLjZ6TTM4OS4xIDIyNC41SDI2OWMtMS41IDAtMi43IDEuMi0yLjcgMi43djY4LjZoMTAuMnY2NC44aDExNC4yVjIyNi4yYy4xLTEtLjYtMS43LTEuNi0xLjd6Ii8+CiAgICA8cGF0aCBjbGFzcz0ic3QwIiBkPSJNMzU0LjggMzYwLjVIMzMxdi00Ni44aDIzLjgiLz4KICAgIDxwYXRoIGNsYXNzPSJzdDMiIGQ9Ik0zMzcuOCAzMTkuOWgxMC4zdjIwLjNoLTEwLjN6Ii8+CiAgICA8cGF0aCBjbGFzcz0ic3Q0IiBkPSJNMjQyLjIgMzEzLjZoMzQuNHY0Ni45aC0zNC40eiIvPgogICAgPGcgY2xhc3M9InN0NSI+CiAgICAgICAgPHBhdGggY2xhc3M9InN0MSIgZD0iTTM5MS45IDI5NS42aC0yNS40VjI0NWMwLS44LjYtMS40IDEuNC0xLjRoMjMuOXY1MnoiLz4KICAgIDwvZz4KICAgIDxnIGNsYXNzPSJzdDUiPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDEiIGQ9Ik0yODQgMjQzLjZoMzMuN3Y1MkgyODR6Ii8+CiAgICA8L2c+CiAgICA8cGF0aCBjbGFzcz0ic3QyIiBkPSJNOTguOCAyNzMuOXYyNy4zSDB2LTIzLjljMC0xLjkgMS41LTMuNCAzLjQtMy40aDk1LjR6Ii8+CiAgICA8cGF0aCBjbGFzcz0ic3Q2IiBkPSJNMTQ4LjQgMjg2LjRsLTE3LTIuN1YyNjNjMC0xLjEuOS0yIDItMmgxMi45YzEuMSAwIDIgLjkgMiAydjIzLjR6Ii8+CiAgICA8cGF0aCBjbGFzcz0ic3Q3IiBkPSJNMTE0IDI2OS41bC02MCAzNS40di0uN0gwdjU2LjNoMTc0LjF2LTU1LjZ6Ii8+CiAgICA8cGF0aCBjbGFzcz0ic3QyIiBkPSJNMTI2LjUgMzE5aC0yNC44Yy0uMSAwLS4yLjEtLjIuMnY0MS4yaDI1VjMxOXoiLz4KICAgIDxwYXRoIGNsYXNzPSJzdDYiIGQ9Ik0xMzkuOSAzMTloMTkuMnYxOS4yaC0xOS4yek02OC4xIDMxOS4zaDE5LjJ2MTkuMkg2OC4xeiIvPgogICAgPHBhdGggY2xhc3M9InN0MiIgZD0iTTExNSAyNjQuMmMtLjYtLjQtMS4zLS40LTEuOSAwbC0xNi4zIDkuNS00NyAyNy41SDB2Ni4yaDQ5LjhsNjMuMy0zNy4xYy42LS4zIDEuMy0uMyAxLjkgMGw2My4zIDM3LjF2LTYuMmwtNjMuMy0zN3oiLz4KICAgIDxnIGNsYXNzPSJzdDgiPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDkiIGQ9Ik00OS44IDMwNy4zbC0zNS42IDUzLjJoMzUuNnoiLz4KICAgIDwvZz4KICAgIDxnIGNsYXNzPSJzdDgiPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDkiIGQ9Ik0yNzYuNyAzMTMuNWwtMzQuNSA0N2gzNC41eiIvPgogICAgPC9nPgogICAgPGcgY2xhc3M9InN0OCI+CiAgICAgICAgPHBhdGggY2xhc3M9InN0OSIgZD0iTTY1OC4zIDI5MC45bC01MS4xIDY5LjZoNTEuMXoiLz4KICAgIDwvZz4KICAgIDxwYXRoIGNsYXNzPSJzdDciIGQ9Ik03Ni4zIDMxNi42aDIuOXYyNi41aC0yLjl6Ii8+CiAgICA8cGF0aCB0cmFuc2Zvcm09InJvdGF0ZSg5MCA3Ny4yMTkgMzI4Ljk0OCkiIGNsYXNzPSJzdDciIGQ9Ik03NS44IDMxNS43aDIuOXYyNi41aC0yLjl6Ii8+CiAgICA8cGF0aCBjbGFzcz0ic3Q3IiBkPSJNMTQ4LjEgMzE2LjZoMi45djI2LjVoLTIuOXoiLz4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDkwIDE0OS41MzUgMzI4Ljk0OCkiIGNsYXNzPSJzdDciIGQ9Ik0xNDguMSAzMTUuN2gyLjl2MjYuNWgtMi45eiIvPgogICAgPGNpcmNsZSBjbGFzcz0ic3Q2IiBjeD0iNTYzLjMiIGN5PSI0Ny44IiByPSI0Ny44Ii8+CiAgICA8ZyBjbGFzcz0ic3QxMCI+CiAgICAgICAgPHBhdGggY2xhc3M9InN0MTEiIGQ9Ik01NjAuOSAxODYuM3YtNjQuNCIvPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDYiIGQ9Ik01NTcuMiAxODYuM2MwLTIgMS42LTMuNyAzLjctMy43IDIgMCAzLjcgMS42IDMuNyAzLjcgMCAyLTEuNiAzLjctMy43IDMuN3MtMy43LTEuNy0zLjctMy43em0wLTIwLjljMC0yIDEuNi0zLjcgMy43LTMuNyAyIDAgMy43IDEuNiAzLjcgMy43IDAgMi0xLjYgMy43LTMuNyAzLjdzLTMuNy0xLjctMy43LTMuN3ptMC0yMC45YzAtMiAxLjYtMy43IDMuNy0zLjcgMiAwIDMuNyAxLjYgMy43IDMuNyAwIDItMS42IDMuNy0zLjcgMy43cy0zLjctMS43LTMuNy0zLjd6bTAtMjAuOWMwLTIgMS42LTMuNyAzLjctMy43IDIgMCAzLjcgMS42IDMuNyAzLjcgMCAyLTEuNiAzLjctMy43IDMuN3MtMy43LTEuNi0zLjctMy43eiIvPgogICAgPC9nPgogICAgPGNpcmNsZSBjbGFzcz0ic3Q2IiBjeD0iMzMzLjUiIGN5PSI0Ny44IiByPSI0Ny44Ii8+CiAgICA8ZyBjbGFzcz0ic3QxMCI+CiAgICAgICAgPHBhdGggY2xhc3M9InN0MTEiIGQ9Ik0zMzEuMSAxODYuM3YtNjQuNCIvPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDYiIGQ9Ik0zMjcuNCAxODYuM2MwLTIgMS42LTMuNyAzLjctMy43IDIgMCAzLjcgMS42IDMuNyAzLjcgMCAyLTEuNiAzLjctMy43IDMuN3MtMy43LTEuNy0zLjctMy43em0wLTIwLjljMC0yIDEuNi0zLjcgMy43LTMuNyAyIDAgMy43IDEuNiAzLjcgMy43IDAgMi0xLjYgMy43LTMuNyAzLjdzLTMuNy0xLjctMy43LTMuN3ptMC0yMC45YzAtMiAxLjYtMy43IDMuNy0zLjcgMiAwIDMuNyAxLjYgMy43IDMuNyAwIDItMS42IDMuNy0zLjcgMy43cy0zLjctMS43LTMuNy0zLjd6bTAtMjAuOWMwLTIgMS42LTMuNyAzLjctMy43IDIgMCAzLjcgMS42IDMuNyAzLjcgMCAyLTEuNiAzLjctMy43IDMuN3MtMy43LTEuNi0zLjctMy43eiIvPgogICAgPC9nPgogICAgPGc+CiAgICAgICAgPGNpcmNsZSBjbGFzcz0ic3Q2IiBjeD0iMTEyLjUiIGN5PSI0Ny44IiByPSI0Ny44Ii8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ic3QxMCI+CiAgICAgICAgPHBhdGggY2xhc3M9InN0MTEiIGQ9Ik0xMTAuMSAxODYuM3YtNjQuNCIvPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDYiIGQ9Ik0xMDYuNSAxODYuM2MwLTIgMS42LTMuNyAzLjYtMy43czMuNyAxLjYgMy43IDMuN2MwIDItMS42IDMuNy0zLjcgMy43LTIgMC0zLjYtMS43LTMuNi0zLjd6bTAtMjAuOWMwLTIgMS42LTMuNyAzLjYtMy43czMuNyAxLjYgMy43IDMuN2MwIDItMS42IDMuNy0zLjcgMy43LTIgMC0zLjYtMS43LTMuNi0zLjd6bTAtMjAuOWMwLTIgMS42LTMuNyAzLjYtMy43czMuNyAxLjYgMy43IDMuN2MwIDItMS42IDMuNy0zLjcgMy43LTIgMC0zLjYtMS43LTMuNi0zLjd6bTAtMjAuOWMwLTIgMS42LTMuNyAzLjYtMy43czMuNyAxLjYgMy43IDMuN2MwIDItMS42IDMuNy0zLjcgMy43LTIgMC0zLjYtMS42LTMuNi0zLjd6Ii8+CiAgICA8L2c+CiAgICA8Zz4KICAgICAgICA8cGF0aCBjbGFzcz0ic3QwIiBkPSJNMTEzLjIgMzcuNmMzLjYuNCA1LjQgMyA1LjQgNS43aC00LjJjMC0xLjYtLjgtMi42LTIuMy0yLjYtMS4yIDAtMi4yLjYtMi4yIDEuOSAwIDEuMiAxLjEgMS45IDIuNiAyLjQgMyAxIDYuNCAyLjIgNi40IDUuOSAwIDMuNC0yLjMgNS40LTUuNyA1Ljh2Mi44aC0yLjN2LTIuOGMtMy4zLS40LTUuNy0yLjctNS43LTYuNGg0LjJjMCAyIDEuMiAzLjIgMi45IDMuMiAxLjQgMCAyLjQtLjkgMi40LTIuMSAwLTEuNS0xLjMtMi0yLjgtMi42LTMuNC0xLjItNi4yLTIuMy02LjItNiAwLTIuOSAyLjQtNC43IDUuMi01LjF2LTIuOGgyLjN2Mi43eiIvPgogICAgPC9nPgogICAgPGc+CiAgICAgICAgPHBhdGggY2xhc3M9InN0MCIgZD0iTTMyMy42IDM4LjNjMy42LjQgNS40IDMgNS40IDUuN2gtNC4yYzAtMS42LS44LTIuNi0yLjMtMi42LTEuMiAwLTIuMi42LTIuMiAxLjkgMCAxLjIgMS4xIDEuOSAyLjYgMi40IDMgMSA2LjQgMi4yIDYuNCA1LjkgMCAzLjQtMi4zIDUuNC01LjcgNS44djIuOGgtMi4zdi0yLjhjLTMuMy0uNC01LjctMi43LTUuNy02LjRoNC4yYzAgMiAxLjIgMy4yIDIuOSAzLjIgMS40IDAgMi40LS45IDIuNC0yLjEgMC0xLjUtMS4zLTItMi44LTIuNi0zLjQtMS4yLTYuMi0yLjMtNi4yLTYgMC0yLjkgMi40LTQuNyA1LjItNS4xdi0yLjhoMi4zdjIuN3oiLz4KICAgIDwvZz4KICAgIDxnPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDAiIGQ9Ik0zNDUuOCAzOC4zYzMuNi40IDUuNCAzIDUuNCA1LjdIMzQ3YzAtMS42LS44LTIuNi0yLjMtMi42LTEuMiAwLTIuMi42LTIuMiAxLjkgMCAxLjIgMS4xIDEuOSAyLjYgMi40IDMgMSA2LjQgMi4yIDYuNCA1LjkgMCAzLjQtMi4zIDUuNC01LjcgNS44djIuOGgtMi4zdi0yLjhjLTMuMy0uNC01LjctMi43LTUuNy02LjRoNC4yYzAgMiAxLjIgMy4yIDIuOSAzLjIgMS40IDAgMi40LS45IDIuNC0yLjEgMC0xLjUtMS4zLTItMi44LTIuNi0zLjQtMS4yLTYuMi0yLjMtNi4yLTYgMC0yLjkgMi40LTQuNyA1LjItNS4xdi0yLjhoMi4zdjIuN3oiLz4KICAgIDwvZz4KICAgIDxnPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDAiIGQ9Ik01NDEuOSAzOC4zYzMuNi40IDUuNCAzIDUuNCA1LjdINTQzYzAtMS42LS44LTIuNi0yLjMtMi42LTEuMiAwLTIuMi42LTIuMiAxLjkgMCAxLjIgMS4xIDEuOSAyLjYgMi40IDMgMSA2LjQgMi4yIDYuNCA1LjkgMCAzLjQtMi4zIDUuNC01LjcgNS44djIuOGgtMi4zdi0yLjhjLTMuMy0uNC01LjctMi43LTUuNy02LjRoNC4yYzAgMiAxLjIgMy4yIDIuOSAzLjIgMS40IDAgMi40LS45IDIuNC0yLjEgMC0xLjUtMS4zLTItMi44LTIuNi0zLjQtMS4yLTYuMi0yLjMtNi4yLTYgMC0yLjkgMi40LTQuNyA1LjItNS4xdi0yLjhoMi4zdjIuN3oiLz4KICAgIDwvZz4KICAgIDxnPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDAiIGQ9Ik01NjQuOCAzOC4zYzMuNi40IDUuNCAzIDUuNCA1LjdINTY2YzAtMS42LS44LTIuNi0yLjMtMi42LTEuMiAwLTIuMi42LTIuMiAxLjkgMCAxLjIgMS4xIDEuOSAyLjYgMi40IDMgMSA2LjQgMi4yIDYuNCA1LjkgMCAzLjQtMi4zIDUuNC01LjcgNS44djIuOGgtMi4zdi0yLjhjLTMuMy0uNC01LjctMi43LTUuNy02LjRoNC4yYzAgMiAxLjIgMy4yIDIuOSAzLjIgMS40IDAgMi40LS45IDIuNC0yLjEgMC0xLjUtMS4zLTItMi44LTIuNi0zLjQtMS4yLTYuMi0yLjMtNi4yLTYgMC0yLjkgMi40LTQuNyA1LjItNS4xdi0yLjhoMi4zdjIuN3oiLz4KICAgIDwvZz4KICAgIDxnPgogICAgICAgIDxwYXRoIGNsYXNzPSJzdDAiIGQ9Ik01ODYuNyAzOC4zYzMuNi40IDUuNCAzIDUuNCA1LjdoLTQuMmMwLTEuNi0uOC0yLjYtMi4zLTIuNi0xLjIgMC0yLjIuNi0yLjIgMS45IDAgMS4yIDEuMSAxLjkgMi42IDIuNCAzIDEgNi40IDIuMiA2LjQgNS45IDAgMy40LTIuMyA1LjQtNS43IDUuOHYyLjhoLTIuM3YtMi44Yy0zLjMtLjQtNS43LTIuNy01LjctNi40aDQuMmMwIDIgMS4yIDMuMiAyLjkgMy4yIDEuNCAwIDIuNC0uOSAyLjQtMi4xIDAtMS41LTEuMy0yLTIuOC0yLjYtMy40LTEuMi02LjItMi4zLTYuMi02IDAtMi45IDIuNC00LjcgNS4yLTUuMXYtMi44aDIuM3YyLjd6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=)



### Uyarı: Bu makine öğrenme algoritmasına dikkat edin

Sizi haberdar etmek istediğimiz birkaç olası hata var. Makine öğrenme yöntemlerini uygulama şeklinize dikkat etmediğiniz sürece, tahminlerinizin doğruluğu konusunda kendinizden emin olabileceğiniz ve doğruluk beklenenden daha kötü olduğu ortaya çıktığında çok fazla hayal kırıklığına uğrayabileceğinizle ilgilidir.

Büyük hatalardan kaçınmak için akılda tutulması gereken ilk şey, verilerinizi iki bölüme ayırmaktır: **eğitim verileri** ve **test verileri** . İlk önce algoritmayı sadece eğitim verilerini kullanarak eğitiriz. Bu bize girdi değişkenlerini temel alarak çıktıyı tahmin eden bir model ya da kural verir.

Çıktıları ne kadar iyi tahmin edebileceğimizi değerlendirmek için, eğitim verilerine güvenemeyiz. Bir model eğitim verilerinde çok iyi bir tahmin edici olabilirken, diğer verilere **genelleyebileceğinin bir** kanıtı değildir . Test verilerinin kullanışlı olduğu yer burasıdır: Test verilerinin çıktılarını tahmin etmek ve tahminleri gerçek çıktılarla (örneğin, gelecekteki apartman satış fiyatları) karşılaştırmak için eğitimli modeli uygulayabiliriz.

> Not
>
> ## Gerçek olamayacak kadar uygun! Aşırı uyum (overfitting) uyarısı
>
> Makine öğrenmesi tarafından öğrenilen bir tahmincinin doğruluğunun, eğitim verilerinde ve ayrı test verilerinde oldukça farklı olabileceğini unutmamak önemlidir. Bu sözde **aşırı uyum** fenomeni ve bir çok makine öğrenimi araştırması, bir şekilde ya da başka bir şeyden kaçınmaya odaklanmıştır. Sezgisel olarak, overfitting çok akıllı olmaya çalışıyor demektir. Bilinen bir sanatçının yeni bir şarkının başarısını tahmin ederken, sanatçının önceki şarkılarının parça kayıtlarına bakabilir ve “şarkı aşkla ilgiliyse ve akılda kalıcı bir koro içeriyorsa, en iyi 20". Bununla birlikte, belki de ilk 20’yi yapmayan akılda kalıcı korolara sahip iki aşk şarkısı vardır, bu nedenle kuralınızı geliştirmek için “… ya da yogadan söz edilmediği sürece” kuralına devam etmeye karar verirsiniz. Bu, kuralınızın geçmiş verilere mükemmel bir şekilde uymasını sağlayabilir, ancak aslında **gelecekteki test verilerinde daha da kötü** çalışmasını **sağlayabilir** .
>
> Makine öğrenim yöntemleri özellikle fazla donuk kalmaya meyillidir çünkü eğitim verilerine mükemmel bir şekilde uyana kadar çok sayıda farklı “kural” deneyebilirler. Özellikle çok esnek olan ve verideki hemen hemen tüm kalıplara uyum sağlayabilen yöntemler, veri miktarı çok fazla olmadıkça yerine gelebilir. Örneğin, lineer regresyonla elde edilen oldukça sınırlı lineer modellerle karşılaştırıldığında, sinir ağları güvenilir tahmin üretmeden önce büyük miktarda veri gerektirebilir.

Fazla taklit etmekten kaçınmayı ve çok kısıtlı olmayan ya da çok esnek olmayan bir model seçmeyi öğrenmek, bir veri bilimcisinin en temel becerilerinden biridir.

### Bir öğretmen olmadan öğrenme: denetimsiz öğrenme

Yukarıda, doğru cevapların bulunduğu denetimli öğrenmeyi tartıştık ve makine öğrenme algoritmasının görevi, girdi verilerine dayanarak onları öngören bir model bulmak.

Denetimsiz öğrenmede doğru cevaplar verilmez. Bu, durumu eğitim verilerindeki doğru cevaplara uyarak yapamadığımız için durumu oldukça farklı kılar. Ayrıca, performans değerlendirmesini daha karmaşık hale getirir çünkü öğrenilen modelin iyi çalışıp çalışmadığını kontrol edemeyiz.

Tipik denetimsiz öğrenme yöntemleri, verinin altında bir tür “yapı” öğrenmeye çalışır. Bu, örneğin, benzer öğelerin birbirine yakın yerleştirildiği ve birbirine benzemeyen öğelerin birbirinden uzağa yerleştirildiği **görselleştirme** anlamına gelebilir . Aynı zamanda , verileri birbirine benzer öğelerin gruplarını veya “kümelerini” tanımlamak için kullandığımız ve diğer kümelerdeki verilerden farklı olan **kümelenme** anlamına da gelebilir .

> Not
>
> ## Örnek
>
> Somut bir örnek olarak, market zincirleri, müşterilerinin alışveriş davranışları hakkında veri toplar (bu nedenle tüm bu sadakat kartlarına sahipsiniz). Mağaza, müşterilerini daha iyi anlamak için, her müşterinin bir nokta ile temsil edildiği bir grafiği kullanarak verileri görselleştirebilir ve aynı ürünleri satın alma eğiliminde olan müşteriler, farklı ürünler satın alan müşterilerden daha yakın yerleştirilir. Veya mağaza, “düşük bütçeli sağlık gıda meraklıları”, “üst düzey balık severler”, “soda ve haftanın 6 günü pizza” gibi bir dizi müşteri grubunu elde etmek için kümelemeyi uygulayabilir. Makine öğrenme yönteminin müşterileri yalnızca kümeler halinde gruplayacağını, ancak küme etiketlerini otomatik olarak üretmeyeceğini (“balık severler” vb.) Unutmayın. Bu görev kullanıcı için bırakılacaktır.

Yine denetlenmemiş öğrenmenin bir başka örneği **üretici modelleme** (**generative** ) olarak adlandırılabilir . Bu, son birkaç yıldan beri, üretici rakip ağlar (GAN) adı verilen derin bir öğrenme tekniğinin büyük ilerlemelere yol açmasından beri belirgin bir yaklaşım haline gelmiştir. Bazı veriler, örneğin, insanların yüzlerinin fotoğrafları göz önüne alındığında, üretken bir model daha fazlasını üretebilir: insanların yüzlerinin daha gerçek görünümlü fakat yapay görüntüleri.

Kurstan biraz sonra GAN'lara ve yüksek kaliteli yapay görüntü içeriğini üretmenin sonuçlarına geri döneceğiz, ancak daha sonra denetimli öğrenmeye daha yakından bakacağız ve bazı özel yöntemleri daha ayrıntılı olarak tartışacağız.