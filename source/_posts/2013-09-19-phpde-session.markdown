---
layout: post
title: "Php'de Session"
date: 2013-09-19 21:32
comments: true
categories: php
---

İlk olarak Php'de Session oluşturmayı ögrenelim.Daha sonra oluşturdugumuz Sessionları kullanarak sessionlarla işlem yapmayı ögrenelim.
{% blockquote %}
Session Oluşturma
{% endblockquote %}

Php'de Session oluşturmak için 2 yol izlenebilir.

1.Yol :
Ön tanımlı degişken olan $*_*SESSION degişkenini kullanmaktan geçiyor.
$*_*SESSION degişkeni hem session oluşturabilir hemde okuyabilir.

$*_*SESSION degişkenini kullanmadan önce **session*_*start()** komutunu çalıştırmalıyız.
Çünkü bu komut sayfadaki session uygulamasını başlatır. Bu komut çalıştırılmadan session oluşturulamaz veya okunamaz.

Bu yol ile session'ı şu şekilde oluşturabiliriz :

```php
<?php
$_SESSION["username"] = "mctr";
?>

``` 

2.Yol :

session_register komutuyla yapabiliriz.Session da taşınmasını istedigimiz veriyi bir degişken halinde önceden tanımlıyoruz.
Daha sonra da degişkeni session_register ile tanımlıyoruz.

session_register kullanırken sayfanın başında session_start() komutunu kullanmamıza gerek yoktur.


```php
<?php
$foo = "bar";
session_register("foo");
?>
``` 

{% blockquote %}
Session Okuma
{% endblockquote %}

Oluşturulan Session'ı okumak için $_SESSION degişkenini kullanırız.Örnegin oluşturdugumuz sessionı okuyalım.


```php
<?php
session_start();
echo "username session'nın degeri".$_SESSION["username"];
?>
```
Bu sayfa açıldıgında ekranda "mctr" yazar.

{% blockquote %}
Session Silme
{% endblockquote %}

Session'ı sonlandırmak veya silmek için session_destroy komutunu kullanırız.Bu komut session'a ait degerleri siler.

Mesela oluşturdugumuz sessionları silelim :


```php
<?php
session_start();
session_destroy();
?>
``` 

İstadigimiz herhangi bir session'ı sonlandırmak için de session_unregister komutunu kullanırız.Mesela "foo" sessionını sonlandıralım.


```php
<?php
session_start();
session_unregister("foo");
?>
``` 

Session konusunda benden bu kadar.. 

Herkese bol php li günler..


