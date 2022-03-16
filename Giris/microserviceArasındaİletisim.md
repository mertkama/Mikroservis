Microservice arasında iletişim nasıl gerçekleşir ?

https://kodlamaklazim.com/images/blog_content_image/0OF7LMTroH8px9F2peT6skaskfark.png


-----fotoğraf---


Bir istek diğer bir mikroservis ile iletişime geçtiğinde


senkron = sonuç beklenir

asenkron = sonuç beklenmez. (Best Practice)


Seneryoya göre hareket edilir. Asenkron ile çözülüyorsa önce asenkron ile çöz eğer çözülmüyorsa senkron ile çözebilirsin.

Mikroservisler arası iletişimi daha güvenli hale getirmek için asenkron iletişim tercih edilir.

word dosyasını pdf dosyasına çevirmek

kullanıcının word dosyasını alsın kuyruğa göndersin pdf dosyasını 
dönüştürdükten sonra işlem bitince B => A ya haber versin. 
Birçok senaryoda asenkron daha avantajlı gözüküyor.
