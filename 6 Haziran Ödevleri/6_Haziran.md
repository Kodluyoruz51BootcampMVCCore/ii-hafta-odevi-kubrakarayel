## Github'ın Gitflow'u ile diğer yaklaşımları arasındaki fark nedir? ( gitflow vs ..)

## GitHub Nedir?
Github.com adresinden ulaşabileceğiniz github yazılımcılar için bir sosyal medya ortamıdır. Aynı zamanda yazılımcılar için bir kod kütüphanesidir. Burada yazılımcılar kendi projelerini halka açık yada özel olarak saklayabilirler. Bu platformun en büyük özelliği çok sayıda open-source projeyi barındırıyor olmasıdır. Yazılımcılar tek başlarına ya da bir ekip halinde geliştirdikleri büyük, küçük bir çok projeyi burada diğer yazılımcılarla paylaşmaktadır. Burada bulunan open-source projelere katkı sağlayıp geliştirilmesini sağlayabilirsiniz yada kendi ihtiyacınız için değiştirip kullanabilirsiniz. Ücretli ya da ücretsiz olarak faydalanabileceğiniz seçenekler mevcut olmakla birlikte eskiden ücretli olan private(özel) proje geliştirme özelliğine artık ücret ödemenize gerek yok. 

## GitFlow Nedir?
Git versiyon kontrol sistemlerinden bir tanesidir. Git Flow ise bir Git eklentisidir. Git Akış ile projelerinizi geliştirirken daha Düzenli Bir Şube mantığıyla geliştirebilirsiniz.

## Bitbucket Nedir?
Bitbucket.org adresinden ulaşabilirsiniz. Bitbucket size halka açık ve özel projelerinizi saklamanız için imkan sağlıyor  ancak Github’dan farkıysa burası bir sosyal medya ortamı yada open-source projeler için bir kütüphane şeklinde kullanılmamaktadır. Kişisel kullanım için ücret ödemeye gerek yoktur.

## GitLab Nedir?
GitLab, github ve bitbucket gibi bir git servisidir ve bu adresten ulaşabilirsiniz.  Open-soure projelerin barındırılmasını sağlar ancak genelde firmalar tarafından kullanılır. Çünkü firmaların gitlab’ı kendi sunucularına kurmalarına imkan tanır ve kurum içi olarak git hizmetlerinden faydalanılmasını sağlar. Kişisel kullanım için ücret ödemeye gerek yoktur.

## GitKraken Nedir?
Axosoft’un ürünü olan git projelerin yönetilmesinin kolaylaştıran ve branch’ların görsel olarak görünmesini sağlayan masaüstü uygulamasıdır. www.gitkraken.com adresinden yazılıma ulaşılabilir. Yazılımı kişisel projelerde ve open-source projelerde kullanmak ücretsizdir.

## SourceTree Nedir?
Atlassian’ın git projelerinin yönetilmesini sağlayan masaüstü uygulamasıdır. GitKrakenden farkı ücretsizdir. www.sourcetreeapp.com adresinden indirip kullanmaya başlayabilirsiniz.

## GitHub, Bitbucket ve GitLab Karşılaştırması
Aşağıdaki internetten alıntı olan ve 2018 yılında oluşturulan grafikte git hizmeti sağlayan github, bitbucket ve gitlab’ın özellik ve karşılaştırmaları mevcut.


![version_control_comparison ](https://user-images.githubusercontent.com/61011022/85026144-fc986f00-b180-11ea-85e1-e1438bfbd718.jpg)
##


## Sourcetree,  Github ve  GitKraken Karşılaştırması

![1_bkV4LPaXcxG15oK4K0nGzA](https://user-images.githubusercontent.com/61011022/85024070-3caa2280-b17e-11ea-86b4-d2b0b85d886b.png)

## Git and GitHub with Briana Swift Youtube Listesi incelensin. (11 Video)
> Youtube Listesi incelenmeye başlanmıştır. 

 ## Merge pull request
 
   ### Create a merge commit 
 **Git merge**  ile yaptığımız birleştirmede yeni bir commit yaratacak ve yeni branch’deki tüm history tarafını kaybetmeden birleştirme    işlemi gerçekleşmiş olcaktır.
 ![merge](https://user-images.githubusercontent.com/61011022/85030849-9e6e8a80-b186-11ea-9c13-5a54561d3400.png)
 
  ### Rebase and merge 
**Git rebase** ile birleştirdiğimizde ise branch deki commit’lerimizi tek tek alıp istediğmiz branch üzerine ekleyecektir. Böylelikle tek bir history oluşturacak ve istenmeyen history ortadan kalkacaktır.
Bu iki komutun farkına baktığımız noktada, aslında benzer işi yaptıklarını ve fark olarak ise **git rebase** kullanımında history’nin temizlendiğini ve **git merge** kullandığımızda ise tüm geçmişin korunduğunu görüyoruz.

  ![rebase](https://user-images.githubusercontent.com/61011022/85031069-e7beda00-b186-11ea-81ba-2d7449991327.png)

  ### Squash and merge
  Öncelikle **git squash** nedir buradan başlayalım, git squash komutu aslında farklı bir rebase kullanımı olarak değerlendirmek daha doğru olacaktır. Geçmişte atılan commit’leri yeniden düzenlemek, isimlendirmek veya birleştirmek için kullanıyoruz.
Bu geçmişte atılan commit’ler, local’de veya uzak bir git sunucusunda olabilir. Unutmamamız gereken bir nokta da, git squash işlemi yaptıktan sonra ‘force push’ kullanmamız gerektiğidir. İstenilen commit aralığını geri gidip yeniden düzenleme yaptıgımız için ‘force push’ kullanımı zorunludur.

![squash](https://user-images.githubusercontent.com/61011022/85030943-bcd48600-b186-11ea-95a0-c7e7ef626459.png)

## issue ve #pull request de id ler neden artıyor farklı sekmeler olmasına rağmen?
>Bir issue açıldığında github onu pull request olarak algılıyor ve aynı ikisine de aynı ID yi veriyor.


  

## Ramp up on Git and GitHub 
> Başlandı.

## Aspnetboilerplate ve yan ürünler araştırması. AspNet Boilerplate - Web Application Framework
ASP.NET Boilerplate, özellikle yeni modern web uygulamaları için tasarlanmış genel amaçlı bir uygulama çerçevesidir. Zaten tanıdık araçlar kullanır ve size bir SOLID geliştirme deneyimi sağlamak için etraflarındaki en iyi uygulamaları uygular.

>Detaylı bilgi için göz atabilirsiniz : https://aspnetboilerplate.com/Pages/Documents



## hackerRank.com --> 30 Days Of Code 
>Başlandı.

## Kaynakça

* https://www.tolgacibikci.com/git-nedir-nasil-kurulur/
* https://medium.com/@thejengo/15-dakikada-sourcetree-i%CC%87le-gitleyin-1cb55c2a8efb
* https://medium.com/neyasistechnology/git-rebase-squash-ile-ge%C3%A7mi%C5%9Fi-yeniden-d%C3%BCzenlemek-9de36441f947
* https://stackoverflow.com/questions/2427238/in-git-what-is-the-difference-between-merge-squash-and-rebase#:~:text=Merge%20squash%20merges%20a%20tree,commits%20into%20a%20single%20commit.&text=When%20doing%20an%20interactive%20rebase,you%20are%20going%20to%20rebase.
* https://github.blog/2016-04-01-squash-your-commits/



