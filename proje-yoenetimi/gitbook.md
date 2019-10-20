---
description: >-
  GitBook, GitHub dokümantasyonlarımızı daha güzel bir arayüz ve hızlı arama
  özelliği ile sunan yardımcı bir platformdur
---

# 📖 GitBook

## 📌 Önemli Notlar

GitBook'a 🚙 geçiş yapmadan önce bilinmesi gerekenler

* Kaynakları \(resim, PDF vs\) GitHub üzerinden çekebilmekte
* GitHub ile 💫 senkronize çalışır

> GitBookta gömülü içerikler için [GitBook Embeds](https://docs.gitbook.com/content-editing/embeds) sayfasına bakabilirsin.

### 💔 Desteklemedikleri

* `###`'ten fazla markdown headerı
* Açılır menü yapısı olan `<detail>` formatı
* Buton yapısı olan `<kdb>` formatı
* GitHub submodule'leri
* Markdown \(`md`\) dışındaki dosyalar

### 💞 Ek Olarak Destekledikleri

* Harici bağlantılar için önizleme desteği
* 🔗 Anchor Link'ler için url değiştirme
* `SUMMARY.md` ile sol kenarda gösterilen dizin yapısını düzenleme
* `README.md`'yi otomatik olarak algılama
* Matematiksel formül formatı olarak bilinen `latex` formatını `$$a=1$$`
  * `$$$$ a $$$$` yapısını da destekler
  * Özetle `$` yerine `$$` kullanmanız gerekmekte
* `.bookignore` ile GitHub'dan aktarılmayacak dosyaları belirleme
* Kendi linkleri **.gitbook/assets** dizinindeki dosyalara yapılmakta
  * URL: `{% embed url="https://www.google.com/glass/start/" %}`
    * 2 dizin içeride olan bir dosya için yazılmıştır
  * Dosya: `{% file src="../../.gitbook/assets/örnek.pdf" %}` şeklindedir
  * İpucu: `{% hint style="info" %} İpucu {% endhint %}`
  * Sayfa: `{% page-ref page="ozel-karakterli-sayfa/" %}`

## 💫 Entagrasyon Yönetimi

### 🙋‍ Karşılama Ekranı

Markdown dosyasının en tepesine `description` alanı oluşturulur.

```text
---
description: İçeriği açıklayan kısa not
---

# İçerik Başlığı
...
```

### 🗂 `Summary.md` Dosyası

Temel amacı githubdaki dosyalarımızın sitenin sol kısmında \(navigation\):

* Hangi isimle gösterileceği
* Hangi dosyaların veya klasörlerin görünür olacağı
* Hangi sırada gözükeceği

gibi sorulara çözüm bulmaktır.

**Basit Örnek:**

```text
# Summary

* [Part I](part1/README.md)
    * [Writing is nice](part1/writing.md)
    * [GitBook is nice](part1/gitbook.md)
* [Part II](part2/README.md)
    * [We love feedback](part2/feedback_please.md)
    * [Better tools for authors](part2/better_tools.md)
```

**Linkleri parçalara ayırma:**

```text
# Summary

### Part I

* [Part I](part1/README.md)
    * [Writing is nice](part1/README.md#writing)
    * [GitBook is nice](part1/README.md#gitbook)
* [Part II](part2/README.md)
    * [We love feedback](part2/README.md#feedback)
    * [Better tools for authors](part2/README.md#tools)
```

**Çok fazla parçalı örnek:**

```text
# Summary

### Part I

* [Writing is nice](part1/writing.md)
* [GitBook is nice](part1/gitbook.md)

### Part II

* [We love feedback](part2/feedback_please.md)
* [Better tools for authors](part2/better_tools.md)

----

* [Last part without title](part3/title.md)
```

## 👨‍💻 GitBook Scriptlerim

[YGitBookIntegration](https://github.com/yedhrab/YGitBookIntegration) repom ile 🐙 GitHub - GitBook 📖 entegrasyonunu sağlayabilirsin.

* `SUMMARY.md` oluşturma
* Markdown olmayan dosyalar için GitHub linkleri oluşturma
  * Markdown olmayan dosyalar GitBook'da gözükmez

> ⚙ Kişiselleştirmek istersen, [YPackage](https://pypi.org/project/ypackage/) üzerinde GitBook scriptlerim mevcuttur.

## 🐞 Hata Çözümleri

### Github Export Sorunları

Aşağıdakı durumlarda bu tarz hatalar gelmektedir:

* `SUMMARY.md` yapısının düzgün olmaması
* Markdown formatında sorun oluşması

### Linklerin Güncel Olmama Sorunu

Sayfalardaki linkler veya içerikler, o sayfada değişiklik olmadığı sürece değişmez

* Sayfa linkleri eski commit'lere bağlı kalır
* Bunu engellemek için o sayfada bir değişiklik yapılması gerekir
* Değişiklik sonunda güncel commit'e bağlı linkler oluşacaktır

## 🔗 Harici Bağlantılar

* [Proje Dizin Yapısı](https://github.com/GitbookIO/gitbook/blob/master/docs/structure.md)
* [Sayfa ve İndeksleme](https://github.com/GitbookIO/gitbook/blob/master/docs/pages.md)
* [Değişkenler](https://github.com/GitbookIO/gitbook/blob/master/docs/templating/variables.md)
