---
layout: post
title: "Php'de İnclude ve Require"
date: 2013-09-23 21:48
comments: true
categories: php
---

İnclude ve require, çalışmakta oldugumuz web sayfasına dışarıdan herhangi bir dosyayı veya sayfayı eklememizi saglar.
<p> Ekledigimiz sayfada sadece fonksiyonlar var ise biz fonksiyonu çagırıncaya kadar hiçbir işlem yapılmaz.Eger sınıf veya fonksiyon dışında 
kod varsa ekledigimiz satırdan itibaren eklenen sayfadaki kodlar çalıştırılır.Kodların çalıştırılması bittikten sonra ekleme yaptıgımız 
sayfadaki kodların çalıştırılmasına devam edilir.<br>

Her iki komutunda kullanım şekli aynıdır.

```php
<?php
include "includeettigimsayfa.php";
require "requireettigimsayfa.php";
?> 
``` 
Burada include veya require edecegimiz sayfa ekleme yapacagımız sayfa ile aynı dizinde olması gerekir.Eger aynı dizinde
degil ise(mesela fonksiyonlar adlı ayrı bir dizin altında olsun), 
aşagıda da gösterildigi gibi sayfanın tam yolunu yazmalıyız.<br>
<br>

```php
<?php
include "fonksiyonlar/includeettigimsayfa.php";
require "fonksiyonlar/requireettigimsayfa.php";
?>
``` 

İnclude ve require kullanırken yapılabilecek hatalardan biri, aynı sayfayı birçok kez eklemektir.
Eger ekledigimiz sayfada sınıf veya fonksiyon yer almıyorsa hata mesajı görmeyiz.Ama ekledigimiz sayfada sınıf veya 
fonksiyon yer alıyorsa hata mesajı görürüz.<br>
<br>
Gördügümüz hata mesajı sınıf veya fonksiyonun tekrar tanımlanmasıdır. 
Tabiki bunu da bir çözümü vardır.include_once ve require_once komutlarını kullanarak bu hatayı engelleyebiliriz.
Bu komutları kullandıgımızda aynı isimli sayfayı sadece bir defa ekleyebiliriz.<br>
<br>
{% blockquote %}
İnclude ile Require Arasındaki Fark
{% endblockquote %}

İnclude ve require arasındaki fark hataya karşı verdikleri tepkidir.Bu komutlar
ancak eklemek istedigimiz sayfa bulunamadıgı zaman hata verir.İnclude hata mesajı verir ve sayfanın kodlarını çalıştırmaya devam eder, 
Require ise hata mesajı verir ve sayfanın çalışmasını durdurur.<br>
<br>

Artık include ve require'ı da biliyoruz.İstedigimiz sayfayı nasıl ekleyebilecegimizi de biliyoruz.<br>
<br>
