---
layout: post
title:  "Design Patterns’a Giriş"
date:   2015-11-18 16:16:01 -0600
categories: Yazilim_Muhendisligi
tags: Yazilim_Muhendisligi
---

Merhaba arkadaslar bugun temel olarak yazilim tasarimlari nelerdir nerelerde kullanilir bunlari anlaticam.Ogrendikce burada sizlerle paylasmaya devam edicegim.Yazılım tasarımları yazılım projelerinde sıklıklarla karşılaşılan problemleri benzer sorunlar üzerinden yola çıkarak Code Optimization’ı en iyi şekilde yapılabilmesini sağlayan yapıdır ve okunabilirliği arttırır diye biliriz kisaca :).Genel olarak islevleri bakimindan 3'e ayrilir.

* **Creational Patterns** ( Olusturucu Kaliplar )
  * Builder : Constructorlari ayirmamizi saglar.
  * Singleton : Bir classtan bir obje olusturmamiza olanak verir.
    * Ulkemizin devlet baskani tektir.
    * Java.lang.system
    * Javadaki enumlar.
  * Prototype : Butun olusturulmus degiskenlerimizin kopyalarini olusturur. ( Chess game - initial setup )
  * Factory :
    * Mesela bir insan olustumam gerekiyor gelen parametereye gore erkek yada kiz olarak kendisi olusturur.

* **Structural Patterns** ( Yapisal Kaliplar )
  * Proxy : Bir objenin baska bir objeyi temsil ettigi durumlarda kullanilir.
    * Mesela kredi karti bir banka hesabinin kartidir.
  * Decorator : Dinamik bir sekilde sorumluluk kazandirma amaci ile kullanilir.
    * Calisma zamaninda davranis ekleme.(Kalitim ile alakali)
    * Java IO
  * Facade : Bir sinif butun alt sistemleri sunar.
      * -EVENT
        * Dekorasyon
        * Food
        * Invitarions
        * Music Troop
      * Manager classi gibi.   
  * Adapter : Farkli siniflarin interfacelerinin eslesmesi olayi.
    * Power Adapter gibi. US,India,Europa..
    * WEb servisten JSON veya XML cektin objeye dokmek icin falan adapter patterni kullanilabilir.
  * Flyweight : Acik telefon agi.Satir sayilarindaki kisaltma vs.

* **Behavioral Patterns** ( Davranissal Kaliplar )
  * Iterator
  * State
  * Strategy
  * Command
  * Mediator
  * Chain of Responsibility
