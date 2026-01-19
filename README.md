Bu projede, bir akıllı evin enerji tüketimini hava durumuna bakarak ne kadar elektrik harcayacağını tahmin eden bir  model geliştirdim.

Veri Hazırlığı:
Veri setindeki zaman bilgisi ilk başta Unix timestampdi. Bunu saat, gün ve ay olarak düzenledim.
Çünkü enerji tüketimi saate,aylara göre değişir.Sonra veri türlerini sayısal forma çevirdim.
Sonra amaç hava durumuna bakarak evin tüketeceği toplam enerjiyi tahmin etmek olduğu için pivot kullanarak hava durumu bilgilerini gruplandırıp daha kolay anlaşılır forma getirdim.

Veriyi test ve train olarak ayırma:
Veri setinde fırın, buzdolabı, çamaşır makinesi gibi cihazların tek tek ne yaktığı yazıyordu. Eğer bunları modelde bıraksaydım, model toplam tüketimi bulmak için bu cihazları toplar ve %100 sonuç verirdi. Ama bu tahmin olmazdı, sadece toplama işlemi olurdu.
Bu yüzden tüm cihaz verilerini sildim.y(hedef) evin toplam tükettiği enerji oldu x ise hava durumu bilgileri oldu. Modelin hava durumuna bakarak tüketilen enerjiyi train seti ile öğrenmesini bekledim.

Model Eğitimi
Eğitim için 3 farklı modelle test ettim,kullandığım modeller:Decision Tree,Random Forest,Linear Regression.

Model Sonuçları
Decision Tree=>Model Başarı Oranı (R2):%55.67,Ortalama Hata (MAE):0.34 kW
Random Forest=>Model Başarı Oranı (R2):%55.63,Ortalama Hata (MAE):0.34 kW 	
Linear Regression=>Model Başarı Oranı (R2):%2.03,Ortalama Hata (MAE):0.57 kW

Model başarı oranının yaklaşık %55 olmasının temel nedeni, enerji tüketiminin yalnızca hava koşullarına değil, insan davranışlarına da bağlı olmasıdır.
Bir kişinin ne zaman televizyon izleyeceği vb. hava durumu verilerinden kesin olarak tahmin edilemez.

Linear Regression Başarısız Oldu çünkü enerji tüketimi düz bir çizgi üzerinde artmaz. Hava sıcaklığı 10 dereceden 20 dereceye çıkınca ısıtıcı kapanır tüketim azalır , ama 20'den 30'a çıkınca  klima açılır tüketim artabilir. Linear Regression bu mantığı anlayamadığı için başarısız oldu.
Decision Tree  ve Random Forest daha başarılı oldu çünkü bu modeller if else matığıyla çalıştığı için bu tarz verilerde daha başarılı olur.

Bu çalışma sonucunda, bir evin enerji talebinin yarısından fazlasının sadece dış hava koşulları ve zaman parametreleriyle tahmin edilebileceğini kanıtlamış olduk. Bu model, enerji şirketlerinin yük tahmini yapması veya akıllı şehir yönetimi için bir temel oluşturabilir.

Python Programlama Sertifika

<img width="739" height="482" alt="Python101Sertifika" src="https://github.com/user-attachments/assets/a12e4636-25a8-40de-ba01-b4e579d8a65b" />
<img width="769" height="473" alt="Python201Sertifika" src="https://github.com/user-attachments/assets/3ef993b7-a5f4-49e8-9e5c-4a00bd418273" />
<img width="740" height="464" alt="Python301Sertifika" src="https://github.com/user-attachments/assets/dd75a0ce-5bc5-45f0-8c80-17cd7e806724" />
<img width="768" height="496" alt="Python401Sertifika" src="https://github.com/user-attachments/assets/f48c41d9-46e0-4c19-89d3-9a5c6013f3b6" />



