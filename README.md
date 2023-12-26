Büyük Ünlü Uyumu Testi
==============

**Tanım:** Büyük ünlü uyumu (BUU) ya da kalınlık-incelik kuralı, Türkçedeki iki ses uyumundan birisi olup, Türkçe kökenli sözcüklerin ayırt edilmesinde kullanılmaktadır.

**Kurallar:** Bir sözcüğün birinci hecesinde kalın bir ünlü (a, ı, o, u) bulunuyorsa diğer hecelerdeki ünlüler de kalın olur:
adım, ağız, ayak, boyunduruk, burun, dalga, kırlangıç.
Bir sözcüğün birinci hecesinde ince bir ünlü (e, i, ö, ü) bulunuyorsa diğer hecelerdeki ünlüler de ince olur:
beşik, bilezik, gelincik, gözlük, üzengi, vergi, yüzük.

Kullanıcıdan dizi halinde girilen kelimeleri 4 ayrı kategoride ifade etmeniz beklenmektedir.
1. Büyük ünlü uyumuna uygun olanlar : `UYGN`
2. Büyük ünlü uyumuna uygun olmayanlar : `UYGNDGL`
3. İstisna kapsamında büyük ünlü uyumuna uygun olanlar : `ISTSN`
4. Büyük ünlü uyumu aranmayanlar : `ARNMZ`

İstisna ve aranmayan kelimeler listesi main.rb içerisinde mevcuttur. Listeleri değiştirmeden kullanınız. Koda eklenmiş olan karşılaştırma listesileri:

1. BUU uygun olan istisna kelimeler listesi

 `exception_words = %w[anne dahi elma hangi hani inanmak]`

2. BUU aranmayan kelimeler listesi

 `not_required_words = %w[ahenk badem ceylan fidan gazete hamsi kestane limon model otomatik pehlivan selam tiyatro viraj ziyaret]`

**Örnek 1:** Kullanıcı `elma orta telefon` girdiğinde:
- elma : ISTSN --> Sesli harfleri uygun olmadığı halde istisna kapsamında uyumludur.
- orta : UYGUN --> Tüm sesli harfler kalın olduğu için uygundur. "a" ve "o"
- telefon : UYGNDGL --> Hem kalın hem de ince sesli harfler bulunduğu için uygun değildir. "e" ince, "o" kalın sesli harf

```sh
echo "elma orta telefon" | ruby main.rb
elma : ISTSN
orta : UYGUN
telefon : UYGNDGL
```
**Örnek 2:** Kullanıcı `lisan tabure matematik alet kitap insan kelime` girdiğinde:

```sh
echo lisan tabure matematik alet kitap insan kelime | ruby deneme.rb
lisan : UYGNDGL
tabure : UYGNDGL
matematik : UYGNDGL
alet : UYGNDGL
kitap : UYGNDGL
insan : UYGNDGL
kelime : UYGUN

```

**Örnek 3:** Kullanıcı `hangi otomatik heybe orman urla limon` girdiğinde:

```sh
echo hangi otomatik heybe orman urla limon | ruby deneme.rb

hangi : ISTSN
otomatik : ARANMZ
heybe : UYGUN
orman : UYGUN
urla : UYGUN
limon : ARANMZ
```

**Örnek 4:** Kullanıcı `yenimahalle samsun bafra terme` girdiğinde:

```sh
echo yenimahalle samsun bafra terme | ruby deneme.rb
yenimahalle : UYGNDGL
samsun : UYGUN
bafra : UYGUN
terme : UYGUN

```

**NOT** : Kullanıcıdan girdi alma satırı `main.rb` içerisinde verilmiştir. Ayrıca girdi almayınız. İlgili değişkene eklendiğini varsayarak işlemlerinizi devam ettiriniz.


**DİKKAT!  AŞAĞIDAKİ AÇIKLAMALARI OKUMADAN ÖDEVE BAŞLAMAYIN!**

1. Birden fazla Github hesabınız varsa ödevde tutarlı olarak sadece bir hesap kullanın.  Birden fazla Github hesabı
   üzerinden ödevin birden fazla kopyasını oluşturmayın.  Bu durumda olan depoları "Settings"e girerek "Delete this
   repository" butonuyla silmelisiniz.  **Aksi halde ödeviniz geçersiz kabul edilecektir.**

2. Programda istenen çıktıların büyük/küçük harf farkları ve varsa boşluklarla birlikte tam olarak açıklandığı gibi
   yazıldığına emin olun.

3. Dizinde bulacağınız [`main.rb`](./main.rb) isimli şablon kodda **sadece** `=== WRITE CODE ===` yazan bölgeyi
   düzenleyin. **Dosyanın adını değiştirmeyin veya (aksi belirtilmedikçe) başka bir dosya açarak düzenleme yapmayın.**

4. Şablon kodda kullanıcıdan veri girişi yapan satırlar (ör. `a, b = gets.chomp.split`) verilmişse **bu satırları olduğu
   gibi koruyun ve kendiniz veri girişi yapan bir kod yazmaya çalışmayın.**  Aksi halde programınız testlerde hata
   verecektir.

5. Yazdığınız kodda Rubocop ile basitleştirilmiş düzeyde [kod denetimi](https://ruby.style/) yapılmakta ve denetimden
   geçemeyen ödevlerden puan kırılmaktadır.  Denetleme sırasında ortaya çıkan hataları düzeltmek amacıyla puanınızı
   görmek için girdiğiniz sayfadaki hata iletilerinde görülen doküman bağlantılarına tıklayarak bilgi alabilirsiniz.

6. Depoyu açtığınızda ödev dosyalarını tarayıcıda veya (bu satırları okurken) `.` (nokta) tuşuna basarak Web üzerinde
   Visual Studio Code ile düzenleyebilirsiniz.

7. Depoda nokta ile başlayan dosya ve dizinlerde (ör. `.github`, `.vscode`) **düzenleme yapmayın**.  Bu dosyalara
   yapılan müdahaleler izlenmekte olup kurala uymayanların ödevleri geçersiz sayılacaktır.
