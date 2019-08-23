# Sözlük

https://developers.google.com/machine-learning/glossary/



Bu sözlük, genel makine öğrenme terimlerini ve TensorFlow'a özgü terimleri tanımlar.

## A

**A / B testi**
Genellikle yeni bir rakibe karşı gelen iki (veya daha fazla) tekniği karşılaştırmanın istatistiksel yolu. A / B testi, sadece hangi tekniğin daha iyi performans gösterdiğini belirlemekle kalmayıp aynı zamanda farkın istatistiksel olarak anlamlı olup olmadığını da anlamayı amaçlamaktadır. A / B testi genellikle tek bir ölçüm kullanan sadece iki tekniği göz önüne alır, ancak herhangi bir sonlu sayıda tekniklere ve ölçümlemelere uygulanabilir.

---

**doğruluk** (accuracy)
Bir *sınıflandırma modelinin* doğru bulduğu *tahminlerin* oranı. *Çok sınıflı sınıflandırmada* doğruluk aşağıdaki gibi tanımlanır:
$$
Dogruluk = Doğru tahminler / Örneklerin Toplam sayısı
$$
İkili sınıflandırmada, doğruluk aşağıdaki tanımlara sahiptir:
$$
Doğruluk = (Doğru Pozitifler + Doğru Negatifler) / Örneklerin Toplam Sayısı
$$
*Doğru pozitif* ve *doğru negatif* tanımlarına bakın.

---

**aksiyon 															#RL (Pekiştirmeli Öğrenme : Reinforcement Learning)**

Pekiştirmeli öğreniminde, *ajanın* *çevrenin* *durumları* arasında geçişi sağlayan mekanizma. Ajan, eylemi bir *politika* kullanarak seçer.

---

**aktivasyon fonksiyonu**
Bir önceki katmandan bütün girdilerin ağırlıklı toplamını alan ve daha sonra bir çıkış değeri (tipik olarak doğrusal olmayan) üreten ve bir sonraki katmana çıktı veren bir fonksiyon (örneğin, *ReLU* veya *sigmoid*).

---

**aktif öğrenme**
Algoritmanın öğrendiği verilerin bir kısmını seçtiği bir *eğitim* yaklaşımı. Aktif öğrenme, *etiketli örneklerin* elde edilmesi zor veya pahalı olduğunda özellikle değerlidir. Farklı bir etiketli örnek yelpazesini kör bir şekilde aramak yerine, aktif bir öğrenme algoritması seçmeli olarak öğrenme için ihtiyaç duyduğu belirli örnek aralığını aramaktadır.