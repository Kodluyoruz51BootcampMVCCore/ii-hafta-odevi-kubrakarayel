## Razor Pages Nedir?
Razor Pages, asp.net core 2 ile birlikte gelen yeni bir özellik. Daha önce kullandığımız asp.net web forms çatısına yaklaşım olarak benzemekle birlikte klasik asp.net webforms’u kullanmadan asp.net mvc üzerine geliştirilmiştir. Razor Pages, sayfa bazlı senaryolar için bildiğimiz mvc (model view controller)’a göre daha kolay uygulama geliştirmeyi sağlayan bir platformdur. Frontend çatılarda kullanılan yaklaşım olan mvvm (model view view model) yapısına benzeşen çift yönlü bağlantı (two way binding) özelliğini desteklemektedir.

Razor Pages’in tek sorumluluk prensibine (single responsibility) uygun bir yaklaşımı var. Öncelikle basit bir html sayfa geliştirmek için daha az dosya kullanılıyor ve dosya hiyerarşisi daha basit. Bildiğiniz gibi genel olarak dotnet web uygulaması geliştirmek için kullandığımız asp.net mvc çatısında controller’in içerisinde pek çok sayfa ile ilgili actionlar vardı. Controller’a bağlı tüm sayfaların actionlarını tek bir dosyada tutuyorduk. Bu durumda controller dosyası büyüyor böylece kodun okunurluğu azalıyor ve mental bir karmaşa yaratıyordu. Çok sayfalı web uygulamaları için bu bir handikap aslında.

Razor Pages bu yönüyle bir avantaj sağlıyor. Mvc yapısı üzerinde geliştirildiği için, mvc de var olan herşeyi destekliyor. (Routing, ModelState vs…). Sözkonusu yapı bize daha önce webforms’ta olup ta istemediğimiz viewstate gibi yapılardan arındırılmış, kompakt bir dosya hiyerarşisi ile birlikte hızlı ve pratik uygulama geliştirmeye yönelik bir çatı sunuyor.

Razor Pages’i mvc ile karşılaştıracak olursak, sayfa ile ilgili olmak kaydıyla controller ve model (viewmodel) objesinin PageModel’e dönüşmüş hali diyebiliriz. 

## Ayarlardaki Output kısmındaki Console Application nedir? diğerleri arasında fark nedir?

### Console application
Konsol uygulamaları, komut istemi (DOS) penceresinde çalışan hafif programlardır. Test uygulamaları için yaygın olarak kullanılırlar.
Konsol tabanlı uygulamalar arasında Alpine (e-posta istemcisi), cmus (ses çalar), Irssi (IRC istemcisi), Lynx (web tarayıcısı), Midnight Commander (dosya yöneticisi), Konsolda Müzik (ses çalar) ), Mutt (bir e-posta istemcisi), nano (bir metin düzenleyici), ne (bir metin düzenleyici), haber bülteni (bir RSS okuyucu) ve ranger (bir dosya yöneticisi).

### Windows Application
Windows Uygulamaları, genel günlük görevler için form tabanlı standart Windows masaüstü uygulamalarıdır. Microsoft word, Windows uygulamasına bir örnektir.

### Class Library
Yazılım projelerinde Dll oluşturmak veya projelerde katmanlı mimari yapmak için kullanılan kütüphanelerdir. .Net yapısında da kütüphanelerden yararlanılarak kodlamalar yapılmaktadır. 

### Web application
Web uygulamaları, http üzerinden kullanıcı isteklerini yerine getirmek için bazı web sunucularının (ör. IIS) içinde çalışan programlardır. Web uygulamasının tipik bir örneği Hotmail ve Google'dır.

### Web service
Web servisleri, internet üzerindeki diğer uygulamalara servis sağlayan web uygulamalarıdır. Google arama motorunun web hizmeti, diğer uygulamaların İnternet üzerinden Google web hizmetine arama yapma görevini devretmesine ve ürettiği sonucu kendi uygulamalarında kullanmasına olanak tanır.

### Static Library
Bu, bir uygulama tarafından kullanılan kodun o uygulamanın yürütülebilir dosyasına kopyalandığı bir tür kütüphanedir.

### DLL
Dinamik olarak bağlı kütüphane. Bu, kodu yürütülebilir dosya kullanılarak her birine kopyalanmayan bir tür kütüphanedir. Bunun yerine kod, çalışan her örneğin belleğine dinamik olarak yerleştirilir. Bu özellik nedeniyle tek bir DLL dosyası birçok program arasında paylaşılabilir. Başka bir özellik, bir DLL'deki kodun gerçekten özel olabilmesi ve kendi çalışma zamanı kitaplığını kullanmasıdır.

## JSON İle Serialize ve Deserialize İşlemi
Objcet bir veriyi json’a çevirebilmek için o veriyi serialize etmemiz gerekir. **Serialize** terimi seri hale getirme olarak dilimize çevirebiliriz.

Bir Json veriyi ise istenilen bir object tipine çevirmek için ise json veriyi **Deserialize** etmemiz gerekir. Deserialize terimini de seriyi kaldırma olarak dilimize çevirebiliriz.
 
Programımızda tanımladığımız bir sınıfın-varlığın(entity) içeriği ile birlikte Json bir veri yapısına dönüştürürken serialize işlemi uygulayacağız. Tam tersi bir veri yapısını json yapıya dönüştürmek için ise deserialize işlemi uygulayacağız.
 
Verilerimizi test edeceğimiz bir proje açalım. Ben Console Application açıyorum ve breakpoint ile verilerimi inceleyeceğim.

Convert işlemimizi kolay bir şekilde sağlayan aşağıda görünen Newtonsoft.Json nuget paketini projemize dahil ediyorum.

![nugetpaketi](https://user-images.githubusercontent.com/61011022/85322274-bcadf080-b4ce-11ea-9755-d3126e494f0a.png)


Bir sonraki adım da ise test amaçlı kullanacağım Person class ‘ımı tanımlıyorum.

```
    public class Person

    {
        public string FirstName { get; set; }
        public string LastName { get; set; }
    }
```


Object veriyi Json veriye çevirebileceğim ve Json veriyi object bir veriye çevirebileceğim yapıyı Helper adında bir class açarak extension metot şeklinde kullanacağım.

```
   public static class Helper
    {
        public static string ToJson(this object obj)
        {
            var item = JsonConvert.SerializeObject(obj);
            return item;
        }
 
        public static T ToObject(this string item)
        {
            var obj = JsonConvert.DeserializeObject(item);
            return obj;
        }
    }
```


Program.cs  class’ıma gelip burada bir listenin içine test amaçlı 3 adet veri atıyorum. Bu 3 veriyi ilk önce serialize ediyorum ve sonrasında deserialize ederek List tipindeki veriyi json veriye çevirip tekrar bu json veriyi List tipine çevirerek serialize ve desirealize işlemlerimi gerçekleştirmiş olduyorum.

```
    class Program
    {
        static void Main(string[] args)
        {
            var lstPerson = new List();
            for (int i = 1; i < 4; i++)
            {
                lstPerson.Add(new Person
                {
                    FirstName = i+".Ad",
                    LastName = i+".Soyad"
                });
            }
 
            var serialize = lstPerson.ToJson();
            var deserialize = serialize.ToObject>();
        }
    }
```

+ Verinin serialize olmuş hali;

![serializeprocess](https://user-images.githubusercontent.com/61011022/85322706-6ee5b800-b4cf-11ea-882c-ab7efd21ae1e.png)



+ Json verinin istenilen objeye deserialize olmuş hali;

![deserializeprocess](https://user-images.githubusercontent.com/61011022/85322781-8886ff80-b4cf-11ea-8ce0-ee9073629598.png)


## MVC vs MVVM vs MVP vs MVW vs MVU Pattern arasındaki fark
 

### MVC 
MVC, web uygulamaları için özel olarak tasarlanmış ve 1970'lerde tanıtılan ilk ve en önemli mimari modeldir. MVC, SoC ile bir uygulama oluşturmanıza izin verir - sırayla, uygulamayı test etme, sürdürme ve genişletme çabalarını kolaylaştıran endişelerin ayrılması. Geleneksel bir yazılım geliştirme prosedüründe, ilgili kodu yazarız veya görünümü tanım sınıfının bir parçası yapmak için kullanıcı kontrolünü kullanırız. Bu yordam, ticari işlemler, veri bağlama mantığı ve kullanıcı arabirimi arasındaki görünüm sınıfının boyutunu artırır. Böylece, MVC mimari desen kod boyutunu azaltmak ve iyi bir kod yapmak için tasarlanmıştır. Daha temiz ve kolayca yönetilebilir.

![01-1](https://user-images.githubusercontent.com/61011022/85326511-136af880-b4d6-11ea-843c-6fccf2e4b6b9.jpg)


### MVP
MVP paterni, MVC paternine çok benzerlik gösterir. Bu mimari modelde “P” sunucu anlamına gelir. Görünüm, sayfa denetimlerini yönetir ve görüntüler. Sunucu, görünüm adına tüm kullanıcı arayüzü olaylarını ele almaktan sorumludur. Kullanıcılardan girdi toplar ve ardından verileri tekrar Görünüme dönüştüren Model'i bir yandan diğerine ilerletir.

Presenter esas olarak bir düğmeye basma gibi hareketler için mantıksal uçtan itibaren performans gösterir veya navigasyon yoluyla yolları yönlendirir. MVP uygulamak için bileşik bir modeldir, ancak gerçekten iyi tasarlanmış bir çözüm olarak uygulandığında faydalı ve büyük faydalar sağlar. MVP deseni genellikle windows form uygulamaları ve ASP.NET Web Formları ile gerçekleştirilir.

![MVP-1](https://user-images.githubusercontent.com/61011022/85326556-2978b900-b4d6-11ea-8d96-da6a6456821d.jpg)

### MVVM
MVVM, MVC'den tanımlanmıştır. MVVM deseni, Görünüm ve Görünüm Modeli arasında iki yönlü veri bağlanmasını destekler. Görünüm Modeli içindeki değişikliklerin Görünüme otomatik olarak yayılmasını sağlar. Genellikle görünüm modeli, Görünüm modelinde Modda değişiklik yapmak için gözlemci desenini kullanır.

![MVVM-1](https://user-images.githubusercontent.com/61011022/85326889-aefc6900-b4d6-11ea-8ed7-836005ee7f3f.jpg)

### MVVM ile MVP Arasındaki Farklar
+ Presenter yerine ViewModel kullanılıyor
+ Presenter View’ı klasik yollar ile güncelliyordu lakin MVVM’de Data Binding adında bir olay var aşağıda değineceğiz.
+ ViewModel hangi View’ın kendisini dinlediğini bilmez

### MVU 
MVU kendisini farklı teknoloji yığınlarında giderek daha fazla kabul görürken, kökenleri fonksiyonel programlama dili Elm topluluğuna sahiptir:

![MVU](https://user-images.githubusercontent.com/61011022/85329005-634bbe80-b4da-11ea-86c1-1aea06c929a6.png)

Karaağaç Mimarisi, webapps ve oyunlar gibi etkileşimli programları tasarlamak için bir modeldir. Bu mimari Elm’de doğal olarak ortaya çıkıyor gibi görünüyor. İlk Elm programcıları, icat eden birinden ziyade, kodlarında aynı temel kalıpları keşfetmeye devam ettiler. Önceden planlama yapmadan iyi tasarlanmış bir kodla biten insanları görmek biraz ürkütücü!

Ama yeterli tarih, bu yazı bunun yerine mevcut favori programlama dillerimden birine dayanan hızlı bir girişe odaklanıyor F#. Temel temelleri kendi bakış açımdan ve mevcut anlayışımı açıklamaya çalışıyorum. Eminim, okuduktan sonra daha fazla soru ile karşılaşırsınız, örneğin, nasıl ölçeklendirilir.



## Kaynakça
* https://www.onbirkod.com/webformsun-yeniden-dogusu-razor-pages/
* https://www.mshowto.org/class-library-nedir-nasil-kullanilir.html
* https://answers.microsoft.com/en-us/ie/forum/all/what-is-difference-between-console-application/f8bd3d4f-7c2c-4c86-a64b-41a046a38be4
* https://stackoverflow.com/questions/22795115/console-application-vs-dll-vs-windows-application-etc
* http://seyyidozturk.com/makale/json-ile-serialize-ve-deserialize-islemi
* https://www.bacancytechnology.com/blog/mvc-vs-mvp-vs-mvvm
* https://academy.realm.io/posts/mvc-vs-mvp-vs-mvvm-vs-mvi-mobilization-moskala/
* https://medium.com/@hsmnzaydn/android-mvvm-kullan%C4%B1m%C4%B1-1-99eb6e48a64f
* https://elifboncuk.dev/2018/03/01/mvc-mvp-mvvm/
