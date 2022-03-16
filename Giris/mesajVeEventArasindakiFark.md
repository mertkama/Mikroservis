
![asfasfa](https://user-images.githubusercontent.com/97520268/158588786-2a0310c4-9c13-4a2e-a2c2-3bc43c164677.PNG)


 ***'Message'***


```Publisher()``` message broker'a mesaj gönderir. 
 ```Subscriber()```'da mesajı dinliyor.
eğer ```Publisher()``` gönderilmiş olan mesajı biliyorsa ve işlendikten sonra geri haberdar edilecekse biz buna mesaj diyoruz.
Kuyruğa gönderilecek olan data'nın genel ismi Mesaj olarak adlandırılır.

```Publisher()``` word dosyasını bir byte dizisi olarak message brokera gönderdiğinde bu mesajın nasıl işleneceğini biliyor word dosyası pdf e dönüştürülecek ve geri verilecek.Ve burada dikkat edilmesi gerekeren göndermiş olunan mesaj içinde gerekli datada mevcut bir byte dizisi içinde var.


 ***'Event'***

Bir notification bir bildiri sistemi sağlar. ***'Event'***'i fırlatan onun nasıl ele alınacağını bilmez. Yani ```Publisher()``` eventi üreten mesaj kuyruk sistemine ***'RabbitMQ'*** mesajı gönderen mesajın nasıl işleneceğinden habersizdir.

Mesajın dönüşü ile ilgilenmez.Mesajı kuyruğa gönderir ve gerisi ile ilgilenmez. Ama mesajda mutlaka geri dönüşü bekliyor.

***'Event'***'ler genellikle geçmiş ifadeyle temsil edilir. Yani bir kullanıcı oluşturulurken ```UserCreatedEvent()``` ve ya bir sipariş oluşturulurken ```OrderCreatedEvent()``` mesajlar kısmında geçmiş ifade kullanılmıyor.

Mesela ```Publisher()``` yeni bir kullanıcı kaydettiğinde bunu message broker'a göndersin ve  ```Subscriber()```'da bir tane  ```Subscriber()``` kullanıcı e-mail göndersin bir tane ```Subscriber((mikroservis)``` bu servis UserCreatedEvent aldığında bu eventin içerisinde sadece kullanıcının Id si var içinde bir data yok sadece gerekli olan Properity'ler var.Bu kullanıcının Id si alınıyor, alındıktan sonra sadece kullanıcının e-mail adresi olsun diyelim bu e-mail adresini gönderiyor. 1. ```Subscriber()```'ın haberi var mı artık, Yok başka bir mesajı dinleyen  ```Subscriber()``` ise UserCraetedEvent'i dinliyor. E-maili alıp o kullanıcıya bir indirim kodu tanımlıyor.Dikkat ederseniz publisher bir event fırlattığında artık onun nasıl ele alınacağı ile ilgilenmiyor, dönüşü ile de ilgilenmiyor. Ve içerisinde bulunan data mesaja göre daha azdır. Örneğin UserCreatedEvent'te sadece bir e-mail bulundurabilir. ```OrderCreatedEvent()```'te sipariş ile ilgili sadece gerekli properity'ler bulundurulur. Ama diğer tarafta dikkat ederseniz word'u bir byte dizini olarak message broker'a gönderiyorum yani datanın kendisi var işlenmesi gereken gerekli data burada o yüzden event'ler mesajlara göre daha hafiftir. Daha küçük boyutludur.

 ***'Message'*** ve  ***'Event'*** kavramında kuyruğa gönderdiğimiz ***'RabbitMQ'*** da kuyruğa gönderdiğimiz data da ben mesaj mı gönderiyorum event mi gönderiyorum ayrımını yapmanız için.

Kısaca kuyruğa gönderilen büyük bir data varsa bu mesajdır. ***'Event'***'in ise daha hafif ve  ```Subscriber()``` gerekli event'i aldıktan sonra bunu Publish eden eventi oluşturan arkadaş hafif bir data gönderiğinde ve eventi nasıl işleyeceğinden pek ilgilenmediğinden, eventi gönderdikten sonra dönüştürüp beklemediği umuluyorsa bir event gönderilmiş olunuyor.
