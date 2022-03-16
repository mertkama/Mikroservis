***'Microservice arasında iletişim nasıl gerçekleşir ?'***



![Ekran Alıntısı](https://user-images.githubusercontent.com/97520268/158466740-a7f51635-6d14-44e8-988d-e5a846b0c539.PNG)

![0OF7LMTroH8px9F2peT6skaskfark](https://user-images.githubusercontent.com/97520268/158466754-8fbaf130-4484-467c-8616-8106a315c812.png)



Bir istek diğer bir mikroservis ile iletişime geçtiğinde


```senkron = sonuç beklenir()```

```asenkron = sonuç beklenmez. (Best Practice)```


Seneryoya göre hareket edilir. ***Asenkron*** ile çözülüyorsa önce ***asenkron*** ile çöz eğer çözülmüyorsa ***senkron*** ile çözebilirsin.

Mikroservisler arası iletişimi daha güvenli hale getirmek için asenkron iletişim tercih edilir.

word dosyasını pdf dosyasına çevirmek

kullanıcının word dosyasını alsın kuyruğa göndersin pdf dosyasını 
dönüştürdükten sonra işlem bitince ```B => A``` ya haber versin. 
Birçok senaryoda asenkron daha avantajlı gözüküyor.
