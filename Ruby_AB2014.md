#AB2014 - Ruby101
- [Ruby-lang](https://ruby-lang.org)
- [Nitrous](https://nitrous.io)

*Bu Notlar Akademik Bilişim eğitimlerinden* **Sıtkı Bağdat** *hocamızın notlarından düzenlenmiştir.* 
##Ruby bir programlama dilidir.

- Ruby, okunabilirliği yüksek bir dildir.
- 1993 yılında geliştirilmeye başlandı ve 1995 yılında yayınlandı.
- 2013 yılı en parlak yıl olarak belirlendi, nedeni ise 2.0 ve 2.1 sürümlerinin ortaya çıkmasıdır.
- Ruby dili, 2004 yılında Ruby on Rails ile entegre edilmiştir.
- Japon Yukihirato  Matsumoto (Matz) tarafından geliştirilmiştir.
- Tamamıyla nesne yönelimlidir. (Birkaç istisna hariç)
- Diğer dillerin aksine yorumlayıcı bir dildir. Yorumlayıcı satırlarda hata olan yere kadar çalışır.
- Dinamik tipleme içerir. Bunun anlamı, herhangi bir tipten diğer tipe kolaylıkla geçebiliyoruz, önceden tanımlanmıs olması gerekmiyor.
- Ruby paket yöneticileri içerir. ([RubyGems](https://rubygems.org))
- Ruby on Rails ve Sinatra  gelişimini sağlar.

**Ayrıca**

- Metaprogramming (Kodun kod yazması)
- DSL (Domain Specific Language) 
- DRY (Don't repeat yourself)
- TIMTOWTDI (There is more than one way to do it)

## Ruby.philosopy[]

- **Ruby.philosopy[1] **

Perl'den daha güçlü Phyton'dan daha fazla nesne yönelimli betik bir dildir.

> Perl + Smalltalk + Phyton + Lisp + Ada + ... = Ruby 
   
- **Ruby.philosopy[2]**
 
Ruby tıpkı insan vücudu gibi, görünüşte basit ama içinde komplex bir yapı vardır.

- **Ruby.philosopy[3]**

Amaç programlama yaparken, kendi düşüncelerini sade ve okunabilir bir şekilde ifade edebilmektir.

## Irb ve Repl İşlevleri

```bash 
irb
irb(main):001:0> 2+2
=> 4
exit
irb --simple -prompt
>> 12.class
=> Fixnum
>> exit
irb(main):003:0> 2*9/3+7
=> 13
irb(main):004:0> _ * 3
=>39
```

Yukarıda görüldüğü üzere *irb*, ruby terminalinin açılmasını; *exit* çıkmamızı sağlar. Bununla birlikte *irb --simple -prompt* ise terminalin daha düzgün görünmesini sağlar . Gözümüze çarpan diğer bir öge 
*_* işareti bir önceki işlemi alıp onunla işlem yapmamızı sağlıyor .

``` 
system('clear')
```
    
ile de terminalin temizlenmesini sağlayacaktır.

```bash 
irb(main):008:0> self
=> main
```

main classta yazdığımızı gösterir.

**Ayrıca**

```bash 
irb(main):010:0> a="Ruby"
=> "Ruby"
irb(main):011:0> a.reverse
=> "ybuR"
irb(main):012:0> "I love
irb(main):013:0" ruby"
=>  "I love\nruby
```
  

Yukarıdaki kodda görüldüğü üzere *.reverse* metodu girilen ifadeyi tersten yazdırmayı sağlar. Ayrıca Eğer açılan tırnak ifade yazıldıktan sonra kapatılmadı ise **>** yerine **"** ifadesi olmaktadır .

## Mantıksal ifadeler

- False veya nil, false kabul edilir.
- False ve nil dışındaki herşey true olarak kabul ediliyor. (0, [], ... gibi ifadeler true olarak kabul ediliyor.)
- Diger dillerde olduğu gibi karşılaştırma yaparken <,>, ==,! (küçük,büyük,eşit,değil) ifadeleri kullanılır.


``` 
irb(main):001:0 3 > 5
=> false
irb(main):002:0 3 < 5
=> true
irb(main):003:0 3 == 5
=> false
irb(main):004:0 !13
=> false
irb(main):005:0 true.class
=> TrueClass
irb(main):006:0 false.class
=> FalseClass
irb(main):007:0 nil.class
=> NilClass
```
    
Ruby dilinde herşeyin bir nesne olduğundan ve bir sınıftan türediğinden bahsetmiştik, burda gözümüze çarpan true, false, nil bile bir classtan türediğini görmekteyiz.

Ayrıca nil' den bahsedecek olursak nil diğer dillerdeki null, undefined, ...vs gibidir, yani *hiçbirşey* anlamına gelir.

Ruby de mantıksal değerlerle alakalı Boolean veya Bool gibi sınıflar bulunmaz, bunuda yukarıda görmekteyiz. Ayrıca mantıksal ifadeler kullanılırken *&&, ||, ! (and, or, not)* ifadelerde kullanılır.

##Metodlarla Tanışma

- Metodların tanımlanması **def** ile başlar , **end** ile biter.


``` 
def metod_adi
...
end
```
  
Eğer parametre alacaksa

``` 
def metod_adi(param1)
...
end
```
    
    
``` 
def metod_adi(param1, param2)
...
end
```
    
şeklindedir.

**Ayrıca** parantez kullanımı zorunlu değildir.

``` 
def metod_adi param1, param2, ...
...
end
```  


şeklindedir.

``` 
def topla sayi1, sayi2
    sayi1 + sayi2
end
puts "Toplam Sonucu: ", topla(3,5)
```
     
     
Yukarıdaki kodları bir bir dosyaya atıp orda calıstırınız, bunun içinde terminal üzerinden dosyanın bulunduğu dizine gidip


``` 
ruby proje_adi
```
    
komutlarını yazmalısınız.

Yukarıdaki topla metodu tanımlanmıs ve bu metod iki değişken alıp toplama işlemini yapıp ekrana yazdırmıştır.

- Metod isimleri **?, ! veya =** karakterlerinden biri ile bitiyorsa özel anlamları vardır. 
 
``` 
sorgulama?    #True veya false değeri döndürür.
```
    
``` 
deger_degisikligi = ...   #bir değiskenin degerini değiştirmeye yönelik kullanılır, atama operatördür.
```
    
``` 
tehlikeli!    #ifadesi kullandığımız metnin orjinalini değiştirir.
```


``` 
irb(main):001:0> a="Ruby"
=> "Ruby"
irb(main):002:0> a.reverse
=> "ybuR"
irb(main):003:0> a
=> "Ruby"
>> exit
irb(main):004:0> a.reverse!
=>  "ybuR"
irb(main):005:0> a
=>  "ybuR"
```


Yukarıdaki örnekte girilen a değerinin **!** karakteri kullanılarak orjinalini değiştirmiştir.

##İsimlendirme Kuralları

- Sınıf, module ve sabit isimler büyük harfle başlar.

``` 
class SinifAdi
...
end 
module ModulAd
...
end
PI_SABITI = 3,14156
```

seklinde tanımlanmalıdır, ayrıca sabitler bilindiği üzre değiştirilmezler, değiştirilmek istense hata verirler.


``` 
irb(main):001:0> PI_SABITI = 3,14156
=> [3,14156]
irb(main):002:0> PI_SABITI = 2
(irb):47: warning: already initialized constant PI_SABITI
(irb):46: warning: previous definition of PI_SABITI was here
=> 2
```

olacaktır.

- **Yerel değişkenler** küçük harfle veya '_' ile başlar.


```
yerel_degisken = "bu şekildedir."
plaka = 20 
```

gibidir.

- **Global değişkenler** $ ile başlar.


```
$global_degisken 
```

seklindedir.

- **Örnek(instance) değişkenleri** '@' ile sınıf değişkenleri '@@' ile başlar.

```
@örnek_degisken
```

```
@@sınıf_degisken 
```
 
seklindedir.

**Ayrıca** terminalde irb açmadanda ruby kodu yazılabilir.


```
ruby -e "puts 'Merhaba'" 
=> Merhaba
```
 
yapılabiilir. Ancak bu yöntem çok tercih edilen bir yöntem değildir.

***

``` 
def degistir(deger)
    degisken = deger
end
puts "Degiskenin degeri: #{degistir(20)}"
=> Degiskenin degeri: 20
```
    	

cıktıyı almaktayız.


 
##Baska bir dosyanın dahil edilmesi

**harici_dosya.rb** adlı ruby dosyamız olsun , ek olarak ta üzerinde çalışacagımız dosyamız olsun **calıstıgımız_dosya.rb** olsun.

Eger biz **harici_dosya.rb** içindekileri **calıstıgımız_dosya.rb** içine embed etmek istiyorsak *load* komutu kulanılarak yapılabilir.

``` 
harici_dosya.rb            

```
    
ise

```
calıstıgımız_dosya.rb
load 'harici-dosya.rb' 
```


seklinde olacaktır. 

*load* komutu yerine *require* komutu kullanılarakta yazılabilir. Ama *load* kullanılırken bir defadan fazla kullanılabilir, *require* ise sadece var olan dosyayı bir kere yükler. Ve genellikle *require* daha fazla tercih edilir.

Ek olarak eger ruby kutuphaneleri kullanılacaksa 

``` 
require 'kutuphane_adi'
```


seklinde kullanılır. Rails'te genellikle *autoload* kullanırız. *autoload* dosyayı otomatik olarak yukler.

**ENV** ile kullanılabileceğimiz tüm path ve metodları görebiliriz.

**Gem** ile ilgili bir kac komut yazmakta yarar var gibi ,

``` 
gem -v   	#alınan gem'in versiyonunu görmek amacıyla kullanılır
gem update --system  #system update etmeyi saglar, eger hata veriyorsa **update** yerine **upgrade** kullanılabilir.
gem list  	#paketlerin listesini gösterecektir.
gem list -r  	#yuklenebilecek gemleri gösterr.
gem install pry  	#terminale daha fazla renk gelmesini renkli yazımı saglar.
gem install pry --no-doc  	#denilerek pry'in sahip olduğu dokumantasyonu kurmamak için kullanıyoruz (ruby'nin son versiyonlarında **--no-ri**) dir.
gem uninstall paket_adi 	#paket kaldırmak için kullanılır.
```


Eger herhangi bir ruby paketi kullanılacaksa önce 	 

``` 
gem install paket_Adi
```

komutu kullanılarak paket indirilir, sonra onu calıstıgımız_dosya.rb içine embed etmek için 
	 
``` 
require 'paket_adi'
```

seklinde kullanabiliriz.

**Projemde herhangi 10 tane paket kullanmam gerekiyorsa hepsinin teker teker install edip require mı etmem gerekli ? **

Tabiki hayır bunu yerine, olusturduğumuz projede *GemFile* içine 

``` 
source ('http://ruby-gems.org')
gem 'paket_adi'
```

komutları ile dosyanın otomatik olarak otomatik olarak indirilmesini saglıyor.

**Ayrıca** Eger ben ruby dosyası olusturacaksam istedigim dizine gidip asagıdaki kodlar yazıldıgında otomatik olarak istediğim dizinde ruby dosyası olusturmayı saglar.

``` 
gem install bundler
cd Desktop   		#desktop dizinin içine yuklemek istiyorum
bundle gem proje_adi
```
    
denilerek Desktop üzerinde bir ruby dosyası olusturbiliriz.
Ayrıntılı incelemek için [Bundler](http://bundler.io/) inceleyebilirsiniz.

Dosyayı acıp , yapılacakları yaptıktan sonra  paketi push edip [RubyGems](http://rubygems.org) te görebiliyoruz.

**Dipnot :** 
- Ayrıca *Thor* ruby için bir pakettir.
- *ARGV* is argumentlerin saklandığı sabittir.
- Dokumantasyon kısmında *ri* komutu kullanılarak yazılmaktadır, genellikle method içinde ararken kullanılır.

``` 
ri Class#method
```
seklinde diyebiliriz.

# Girdi - Cıktı işlemleri

Çıktı işlemleri asağıdaki komutlar kullanılarak yapılır.

```ruby 
puts  	#satıra \n atarak cıktı almamızı saglar.
print 	#satırı olduğu gibi ekrana yazmayı sağlar.
p 		#'.inspect' metodu kullanmak gerektiğinde kullanılabilir.
printf  #Ekrana direk yazmamızı sağlar.
```

Girdi işlemleri için

```ruby 
gets  	#Direk kullanıcıdan girdi almamızı sağlar.
```

Yukarıda *p*  'nin kullanımında *.inspect* yerine kullanacak olursak

```ruby
puts "ruby".inspect 
puts 3.inspect   

```
   
*.inspect* metodu ile tam saklandığı halini veriyor.Yukarıda çıktı methodlarında "p" ; ".inspect"'in kısa halidir. Bunun anlamı eger ".inspect" metodu kullanacaksam bunun yerine "p" kullanmam yerinde olur.

- *chomp* sadece son karakterde "\n" varsa son karakteri temizlemeyi sağlar.
- *chom* ise sonda ne varsa onu temizler.


``` 
      		       Basic Object
      			        ||
      			      Object
      			        ||
      			      Numeric
      			        ||
      	Integer		float	Rational	Complex
      
	Fixnum  Bignum			        

```


Sınıfların gösterimini genel olarak bu şekilde gösterebiliriz.

- Ruby 2.0 sürümünde rasyonel sayı tanımlamak için 30/2r seklinde tanımlanabilir.
- Ruby para sistemlerinde **BigDecimal** kütüphanesini kullanmamız gerekmektedir.

``` 
1.0e7  		#10.000.000
3.methods   	#3 için geçerli metodları getiriyor.
__________________
require 'yaml'			#yaml dosyası ekleniyor.
puts 2.methods.to_yaml   #2'nin dahil oldugu yaml kutuphanesi ile birlikte olan methodları göstermektedir.

```

- sayi1 diye bir değiskenimiz olsun ve bu değişkenimizin değeri sayi1 = 1,39 olsun

``` 
sayi1.round  	#normal degerini veriyor. => 1
sayi1.ceil  		#bir üst sayiya yuvarlıyor.=> 2
sayi1.floor 		#bir asagıya yuvarlıyor 	=> 1
```

seklinde görmekteyiz.

- **<=>(space ship)** operatörü karşılaştırma operatörüdür.

``` 
a <=> b
a < b ; -1
a > b ; 1
a =b ; 0

```

 
ifadelerini döndürür.

***

``` 
a = 5 && b = 10
a <=> b 			#-1
```


çıktısı olacaktır.

- Kısaca times ve upto metodlarından bahsedecek olursak

``` 
10.times do |i|
...
end
```

veya

``` 
10.times {|i| ...}
```

seklinde kullanılabilir. Yukarıdaki işlemde *times* ile bir döngü yazılmıstır.  *times* kelime anlamındanda anlaşılacağı gibi *10 defa yazdır* anlamına gelmektedir.
	

``` 
irb(main):001:0> 10.times do |i|
irb(main):002:1* puts "ruby"+i.to_s
irb(main):013:1> end
ruby0
ruby1
ruby2
ruby3
ruby4
ruby5
ruby6
ruby7
ruby8
ruby9
=>10      
```

seklinde çıktısı olur.
 
- *1.upto(10){...}* ile de 'times' benzer bir kullanım sunar.

``` 
irb(main):001:0> 10.upto(10) {puts "ruby"}
ruby
ruby
ruby
ruby
ruby
ruby
ruby
ruby
ruby
ruby
=>1      
```
    	
veya

``` 
irb(main):001:0> 1.upt0(10) do |i|
irb(main):002:1* puts "Ruby"+i.to_s
irb(main):013:1> end
Ruby1
Ruby2
Ruby3
Ruby4
Ruby5
Ruby6
Ruby7
Ruby8
Ruby9
Ruby10
=> 1

```

##Metinler

- İçinde herhangi bir işlem yapılmıyorsa tek tırnak(' '); yapılıyorsa cift tırnak(" ") kullanılır.
- Metinleri birleştirirken stringleri içine gömerek yapabiliriz.


``` 
puts "#{'akademik'.capitalize} #{'bilisim'.upcase}"

=>	Akademik BILISIM     
```

   

 seklinde olacaktır.
 -Ayrıca metinlerde türkçe karakter desteği için de Unicode-Utils kutuphanesi vardır.Bunu da 

 
``` 
gem install unicode_utils	     
```

seklinde indirip, dosyanın içine

``` 
require 'unicode_utils'
```
seklinde diyebiliriz. Daha sonra

``` 
UnicodeUtils.upcase("ruby")
=> RUBY
```

şeklinde kullanabiliriz.
	    

-%q => tek tırnak için kullanılabilir.

``` 
metin = %q<Merhaba>
=> 'Merhaba'
```
seklinde olacaktır.


``` 
metin=%Q{Merhaba}
=> "Merhaba"
```
	    
seklindedir.

- Eger içinde cıktı ifadesinde tek tırnak, çift tırnak,...vs kullanılacaksa ozaman **'\' (backslash)** kullanılabilir. Tab için **\t** ; bir alt satıra inmek için **\n** seklindedir.

***
``` 
irb(main):002:0> ?a
=> "a"
``` 
olacaktır.

- Metnin içine herşey gömebiliriz.

``` 
puts "Metnin içine herşey gömebiliriz #{def isim 
$ad.capitalize + " "+$soyad.upcase
end} puts "benim adım #{isim}""
```

seklindedir.


***
``` 
ad="Ruby"
soyad="Rails"
metin = << FALAN
Ben uzun bir metinim
#{$ad} #{$soyad}
FALAN
p metin	
```
	    
şeklindede kullanabiliriz.

- Bir metnin uzunluğunu bulabilmek için **length** veya **count** metodları kullanılır.
- Method isimleri symbol olarak kullanılabiliyor, şimdilik symbollerin 

``` 
:symbol
``` 
seklinde tenımlandığını bilmeniz yeterlidir.
	    
*
``` 
swapcase
``` 
komutu ise büyük harfi küçüğe, küçük harfi büyüğe çevirir.
	    
*
``` 
puts metin.split.inspect
``` 
metodu ise metni istediğimiz karaktere göre ayırır. Yukarıda hiçbir karakter belirtilmediğinden bosluklara göre ayırma yapıyor.
	    


``` 
metin.sub 'm', 'a'  	#ilk gördüğü "m=>a" ceviriyor.
metin.gsub  'm',  'a' 		#tüm "m"leri "a" 'ya ceviriyor. 
```
	    

- Düzenli ifadeler **/.../** blokları arasına yazılır.
- Süslü parantezler sadece bloklarda kullanılır.
- Her zaman metodların sonunda **end** vardır.
- Ruby 1.9 süürmünden önce Ruby daha yavaştı, Ama 2.0'dan sonra performance artırıldı ve garbage collection yeniden inşa edildi, Bu da ruby deki sorunları ortadan kaldırdı.
- Herhangi bir degiskeni  Integer'a çevirmek için

``` 
.to_i
```
	    
- String'e çevirmek için

``` 
.to_s
```
	    
- Array'a çeirmek için

``` 
.to_a
```
	    
- Hash'a çevirmek için
 

``` 
.to_h
```

kullanılır.	


## Semboller

- Semboller oluşturulurken 

``` 
:sembol_isim
```   
şeklinde oluşturulur.
	    
- Eger metnin içeriği herzaman değiştiriliyorsa o zaman sembol kullanmama gerek yok, zorluk yaratır. Ama değişmeyecek olan işlemler de kullanılırç ve RAM'da tutulur.

``` 
object_id
```  
ile RAM'de tutulan yeri gösteriyor. 
  
- Eger string ifadeyi symbol'e cevireceksem o zaman 

``` 
.to_sym
```  
metodunu kullanırız. Ama symbol olanı 

``` 
.to_s
``` 
ile stringe çevirebiliriz.
	    
- Metinleri Symbol olarak tanımladıktan sonra değiştirmek için **freeze** metodu kullanılabilir.


``` 
.equal? 
```  

metodu ile aynı nesneye sahip olup olmadığını ve symbol olarak aynımı deilmi onu karşılaştırır.
   



##Düzenli ifadeler

- Düzenli ifadeler


``` 
/ ... /
``` 
tagları arasına yazılırlar.
  - Bir metnin düzenli ifade ile eşlenip eşlenmediğini anlamak için =~ veya **match** metodu kullanılır.
 

``` 
{2, 5} 		#en az 2  en fazla 5 demektir.
/.{2,5}/ =~  #"ali" girildiği zaman eşleşir. "ali"2 ile 5 arasındadır.   
```


> Eger metin içerinde **.** kullanmak istesem o zman noktayı düzenli ifadede 
"\." olarak kullanırım.   ```

``` 
^a$b => a ile başlayıp b ile biten demektir.İfadesi yerine 
\A\Z şeklinde kullanılabilir.
(+) => kaçtane geleceği
[^0-9] sayı olmayanları yaz demek. '^' değil demektir.
```  



``` 
[A-Za-z0-9_] = \w   	#word character
[Â-Za-z0-9_] = \W 		#not a word character
``` 
   	

   
``` 
ifade1 = /.*\.$/  		#seklinde nokta ile bitecek demek.
ifade2 = Regexp.new('^[a-z]+$')      #ifadesi a ile baslayıp z ile bitecek anlamına gelmektedir.
ifade3 = %r{^[a-z]+$} 		#a ile baslayacak ama z ile bitmeyecek demektir.
``` 
 
## Aralıklar

Başlangıç ve bitiş degerleri arasında kalan değerleri alır.

``` 
baslangıc..bitis
``` 

seklindedir.

``` 
1..10 			#1, 2, 3,...,10
(1..10).class   	#Range
1...10 			#1, 2, 3,..., 9 kadar olur.son degeri almaz.
``` 
   
- Aralıklar 


``` 
.to_a
``` 
   
ile diziye çevrilir.
   
``` 
("a".."f").to_a 		#["a", "b", "c", "d", "e", "f"]
``` 
	 
seklinde olacaktır.
   
- Aralıklarda Enumerable modülunu içerir.

``` 
irb(main):001:1> (1..10).step(4) {|i| puts i}	#1'den 10'a kadar 4'er 4'er artır. 
1			
5						
9
=>1..10	 
``` 
   seklinde olacaktır.
   
``` 
.include? 
``` 
   
metodu aralıkta olup olmadığını kontrol eder, genellikle sayılarda kullanılır.
   

``` 
aralik=(2 .. 8)
puts aralik.to_a.inspect    #{2,3,4, ...,8}
puts aralik.include? 7   	#true
aralik.each{|i| puts "Deger: #{i}" if i>4}	
``` 
seklinde kullanılır.
	   
veya

``` 
(1..10).each do |sayi|
puts sayi
end
``` 
seklindede kullanılır.

``` 
.reject
```  
metodu  geriye dizi döndürüyor ve diziden eleman çıkarıyor.

``` 
aralik2 = aralik.reject{|u| (u%2)==0}
puts aralik2.inspect
#[3,4,5]
```  
olacaktır.
   

``` 
.class  #Array
```
   seklinde olmaktadır.
   


***
``` 
harfler = ('a' .. 'z')
sesli = %w{a e i o u}
sessiz =harfler.reject{|letter| sesli.include?(letter)}
puts sessiz.inspect
#Sessiz harfleri verecektir.		
```
   

***
``` 
sessiz.each{|ch| puts ch, if (ch == 'c')..(ch=='m')}
#eger ch(karakter) c ve m arasında ise yazdır    
```
 
> **===** komutu ile include aynı anlama gelmektedir.**include** ile aynı mantıkta calısır.


## Diziler

Diziler, array sınıfı kullanılarak üretilir.

``` 
dizi = ["ali", 12, true, /\Aab\Z/, [1,2,3]]    
```
 seklinde tanımlanabilir.
``` 
dizi[-1]  	#son elemanı döndürür.
dizi[0 .. 2]	#0. indisten baslayıp iki tane eleman al diyor.  
```
 - Dizilerde metinler gibi 
 

``` 
+  
```

veya


``` 
<<   
```
kullanılarak birleştirilebilir.
   
``` 
dizi.flatten 	#[1,2,3,4,5,6]   #hepsini aynı hizada 	olusmasını saglar. 
``` 
 
- Array sınıfının objelerini görmek için 

``` 
Array.ancestors  
``` 

 kullanılabilir.
 
- Atama işlemlerini


``` 
a, b = 3, 5     		# a=3 ; b=5
```  
atıyor, eger yerlerin değiştirmek istersem,
 
``` 
a, b = b, a    		#a = 5; b = 3
``` 
 
 seklinde olacaktır.
 

``` 
a,b,c = [3,5]  	#[3,5]   
``` 

ifadesinde c'ye "nil " ataması
 yapar.
   
``` 
.splat   
``` 
 operatoru ile 
 
``` 
a, *b=[1,2,3,4,5] 	# a=1 ; b=[2,3,4,5]
```
 
 seklinde olur.
 
``` 
c = 1,[2,3,4]   =>#[1,[2,3,4]]
c = 1, *[2,3,4]  =>[1,2,3,4]
```
 seklinde tanımlanabilir.
 
``` 
dizi = Array.new(3, 'x')   
``` 
 
 ifadesi 3 elemanlı dizi oluşturur ve hepsine 'x' atar.
 
``` 
dizi = ["A", "B", "C", "D"]   
```

 ise
 
``` 
dizi[0] = 'A'
dizi[1]='B'
dizi[2]='C'
dizi[3]='D'
dizi[-1]='D'
dizi[-2]='C'
dizi[-3]='B'
dizi[-4]='A' 
``` 
 
 çagrılmaktadır.
 
- Eger diziye ekleme yapılacaksa 

``` 
dizi[4] = 'E'
dizi <<  'F'  
```
 
 seklinde,
 veya
``` 
dizi.push  'G'
```
 seklinde de eklenebilir.
 
``` 
dizi.pop  	#sondaki elemanı cıkarıyoruz. 
dizi.unshift " "	#başa ekleme
dizi.shift 		#bastan cıkarma 
```
 komutlardır.
 
``` 
renkler = %w/mavi, acık\mavi, sarı, acık\sarı 
renkler[1] 			#acık mavi
```
 ***
``` 
gunler = ["pzt","salı","çar","per", "cum","cumr","pazr"]
veya
gunler = %w("pzt", "sal", "çar", "per", "cum",  "cumr","pzr")     
```

seklindede tanımlanabilir.


``` 
dizi = %w(#{1+1}  #{2+2})		#=> ["2", "4"]


```
seklinde olur. Yukarıdaki özellik 2.0 ile gelen bir özelliktir.


``` 
sembol = %i*ali veli nuri* 		#semboller seklinde tanımlanabilir.
puts sembol.inspect   	#[:ali, :veli, :nuri]

```

> **yaml** özelliği ile tree seklinde bir görünüm sağlanır.

##Sözlükler(Hash)


``` 
ogrenci = {'ad'=> Ali', 'soyad'=> 'Kara'}   	
#ad, soyad => key
#Ali, Kara => value

```

Sözlükler iki parametreden oluşur, bunlar key ve value'dur. Key'ler herhangi bir türden  olabilir. 

> **eql?** metoduna göre eşit olan sadece bir anahtar bulunabilir.Kısaca aynı hash'a sahipse true dondurur.
- Sözlüklerde anahtar olarak genelliklesemboller kullanılır.
Bu durumda iki farkı yazım türü karsımıza çıkmaktadır.



``` 
#Ruby 1.9'dan önce
ogrenci={:ad =>'Ali', :soyad ='Kara'}     
```
yerine
	
``` 
ogrenci={ad: 'Ali', soyad: 'Kara'}	     
```
seklindedir.
	
- Anahtarlara erişebilmek için **keys**, değerlere ulaşabilmek için **values** metodları kulanılır.

``` 
ogrenci.keys   		#[:ad, :soyad]
ogrenci.values 		#["Ali", "Kara"]	     
```
olacaktır.

- Eger bos bir sözlğk tanımlayacak olursak


``` 
params={}     
```
seklinde tanımlanabilir.
	
- Anahtar kullanılarak erişim yapıldığında istediğimiz atama işlemini yapabiliyoruz.


``` 
"*" => tek dizi olarak atamayı saglar.
"**" => sözlük olarak atama yapmamızı saglar.	     
```


``` 
ogrenci.each do |anahtar, deger|  
#dizilerden farkli olarak 2 deger alıyor , nedeni hem key hemde value'ya sahip olması.	     
```
    
``` 
h1.merge h2   
``` 
dedigimizde h1 ve h2'yi birleştiriyor.
    veya
    
``` 
h3={ad: "Ayten"}
h1.merge h3  	#"Ayten", "Kara"	     		     	    
``` 

olacaktır.  Bir nevi üzerine yazıyor gibide düşünülebilir.
	     	
- Dizide sözlüğe çevirmek için 	 

``` 
.to_h    
``` 
metodu ile çevirebiliriz.
    
### Uygulama - 1

Palidrom kelime: Baştan veya sondan okunuşu aynı olan kelimelerdir.
ÖR : kazak, madam => palidrom kelimelerdir.

``` 
#palidrom.rb
print "Enter the sentences: "
str = gets.chomp
def palidrom?(str)
if str.reverse == str
return true
else
return false
end
puts palidrom?(str)	     
```
olacaktır.

##Uygulama - 2

Palidrom cümle: Baştan veya sondan okunuşu aynı olan cümlelerdir.

``` 
#palidrom.rb
print "Enter the sentences: "
str = gets.chomp
def palidrom?(str)
buyuk_harf=str.downcase
kelime_ayır=buyuk_harf.split
kelime_birlestir=kelime_ayır.join
#ifadesi yerine direk *str1=str.downcase.split.join* denilerekte yapılabilir.
if kelime_birlestir == kelime_birlestir.reverse
return true
else
return false
end
puts palidrom?(str)	     
#Traş niçin şart, Ey edip adanada pide ye gibi
```


seklinde girilen bir cümlenin palidron olup olmadıgını verecektir.


- Eger türkçe karakter kullanılacaksa calısılan dizine gidip calıstıgımız dosyanın içine 	 

``` 
require 'unicode-utils/upcase'  
``` 
    
ifadesi yazılarak bulunabilir.
    
##Uygulama - 3

- Kac adet Uygulamasında girilen cümlede aynı olan kelimeleri geri döndüren bir uygulama geliştiriniz.

``` 
puts "Cumleyi girin: "
str1=gets.chomp
puts "Aranacak kelime:"
str2=gets.chomp
def kac_adet(str1,str2)
str1.downcase.count(str2.downcase)
end
puts "Cumle: ", kac_adet(str1,str2)  
``` 
    
seklinde olacaktır.


##Kontrol Yapıları

#### if,else, elsif

``` 
if kosul
yapılacaklar
end    
```
     
yukarıda if kosul dogru ise yapılacakların yapılmasını sağlıyor.

Yukarıdaki ifadeyi
``` 
if kosul then yapilacak end
``` 
yazılabilir,  veya

``` 
yapilacak if kosul
``` 
seklinde de olabilir.
     
``` 
if kosul1  
...  #kosul1 dogru ise yapılacaklar.
elsif kosul2   
...   #kosul2 dogru ise yapılacaklar.
else
...   #yukarıdaki kosullar dogru deilse yapılacaklar
end 		
```

seklinde olacaktır.

#### unless
Unless, kosulun false oldugu durumlarda çalıstırılır.

``` 
unless kosul
yapılacaklar
end    
```

**Unless** ile else kullanmak pek akıllıca değildir, bunu nededi aslında "unless = !if "olmasıdır. unless ile else kullanmak gerekiyorsa onun yerine if-else kullanılması gerekmektedir.

#### Üçlü Operatör(?, : ) 	 

``` 
kosul ? kosul_true_ise_yapılacak : kosul_false_ise_yapılacak
```

seklindedir.

Yukarda anlatılanları kod dizininde görecek olusak : 

``` 
gun ='pazartesi'
puts (gun == 'pazartesi' ? "Sendrom" : "Yupppi :)")
end    
#Sendrom
```
    

ifadesinde *gun* degiskeninin degeri pazartesi oldugunda kontrol yapısına girdiginde degeri *true* olacağından cıktıyı *Sendrom* olarak verecektir.

#### case-when

- Çok sayıda dallanma kontrolu gerekliyse kullanılacaktır.

``` 
degisken = 12,5
puts case degisken
when String then "Bu bir metin"
when Integer then "Bu bir tamsayı"
when Float then  "Bu bir ondalık sayi"  
```
     seklinde olacaktır, veya yukarıdaki ifade yerine 	
``` 
String === degisken 
``` 
     
     kullanıldığında 	 
     
``` 
true   
``` 
     degerini döndürür. Bunun nedeni 
``` 
=== 
``` 
ifadesinin

``` 
.include?    
```
ifadesine eşdeğer olmasıdır.
     

## Enumerable Modülu

- Enumerable modülu klasik döngülerin yerine kullanacağımız metodlerı barındırır.

``` 
(1..10).each do |sayi|
print sayi
end 
# 1 2 3 4 5 6 7 8 9 10
```
     ifadesinde 1den 10'a kadar her sayiyi ekrana yazdırmayı sağlar.
     
> **all?** metodu verilen komutu içermesi gerekir. yani

``` 
d=[13,35,65]
d.all?{|x| x>20}    #false
```

```
B.instance_methods.size 	#56
Object.instance_methods.size 		#54	      
```
yukarıda ki *all?* metodunda tum *d* degerlerinin 20 den buyuk olması gereklidir, ama yukardaki ifade bu kurala uymadığı için *false* döndürecektir. Ama yukardaki ifade yerine

``` 
d=[13,35,65]
d.all?{|x| x>10}    #true
```

ifadesi olursa bu sefer tum degerler 10 'dan buyuk olacağından *true* döndürecektir.
     
> **any?** metodunda ise birinin verilen kurala uyması yeterlidir.


 
``` 
d=[13,35,65]
d.any?{|x| x>20}    #true
```
ifadesi **all?** farklı olarak *true* degerini döndürecektir.
     
> **select** metodu seçimi sağlıyor.

``` 
d.select{|x| x>50}    #65   
```
x'in 50'den buyuk olan degerlerini yazdırır.
     	
> **collect** metodu ifade içerisinde dogru degerlere *true* yanlıs degerler *false*	 

``` 
d=[13,35,65]
d.collect{|x| x>50}     #[false,false,true]
```
olacaktır.
     
> **find** metodu bulma işleminin yapılmasını sağlıyor.

``` 
d.find{|x| x>50}  #65    
``` 
     
ifadesi 50'den buyuk ilk elemanı geri döndürüyor.

     
> **find all** metodu *find* metodundan farklı olarak verilen kosula uyan tum degerleri geri donduruyor.

```
d=[13,35,65,85]
d.find all{|x| x>50}    #[]65, 85]   
```
olacaktır.

> **reduce** metodu ise
   
```
d=[13,35,65,85]
d.reduce{|sum,x| sum +=x} 
#198	 
```

ifadesinde her x elemanını *sum*'a ekleyip en son *sum* ifadesini döndürüyor.

```
d.reduce(10){|sum, x| sum *= x}    #25138750
```
ifadesi çarpma işlemini yapacaktır.


**Class Çagırma**

```
class Ogrenci
def sayi
end 
end
a=Ogrenci.new("ali","veli")	
a.sayi 	#class içindeki metoda ulaşmayı sağlar. 
```

```
Ogrenci.ancestors 
#Class'ın soyağacını göstermeye çalışır. 
```
     
```
p a 	#Adres ve bilgileri verir.
puts a 	#Sadece Adresi verir.
```
	      
- Bir üst sınıfı görmek için **super** komutunu kullanabiliriz.

- Sınıflarda **kalıtım**  

```
<
```
işareti ile yapılabilir.
	      
```
class A
end
class B < A
end	      
``` 

ifadesinde B'nin A'dan türediğini görmekteyiz. Ayrıca


	 	 
olur.Aslında B objenin instance methodlarından türemiş diyebiliriz.

```
class Dikdörtgen
 def initialize(uzunluk,yukseklik)
  @uzunluk,@yukseklik=uzunluk,yukseklik
end
 def cevre() 2*(@uzunluk+@yukseklik)end
end
class Kare < Dikdörtgen
 def initialize(uzunluk)
  @uzunluk =(@uzunluk)*(@uzunluk)
end
end
```
ifadesinde Dikdörtgen classından türetilen Kare sınıfı ve hesaplanan dikdörtgen cevresi ve kare alanıdır.

```ruby
class Ornek
	def initialize(params={})
		@ad=params[:ad] if params[:ad]
		@armut=params[:armut] if params[:armut]
	end
end

o=Ornek.new(ad: "Ali")
```

- Ruby çoğul kalıtımı desteklemez.
- *super* metodu sadece initialize metodu için geçerli değildir. Herhangi bir metodta da kullanılabilir.
- Direk class üzerinden erişmek istiyorsak **self** komutunu kullanabiliriz. Ama o zamanda nesne üzerinden çağıramayız.

```ruby
def self.sayac_goster
...
end
puts Ornek.sayac_goster
```
şeklinde direk çağırabilirim. Ama yukarıdaki metodu

```ruby
p=Ornek.new(" ")
puts p.sayac_goster
```
seklinde **kullanamayız** hata verecektir.

## Modüller

Modüller sınfların aksine sadece metodları ve sabitleri barındırmak için kullanılırlar.

```ruby
module Ornek
SABIT = 26
end
```

erişim içinde direk **::** kullanabiliriz.

```
Ornek::SABIT
```
veya

```
LyricsParts::FIRST[0]  #Modülu ile LyricsParts 'in içindeki FIRST adli değişkenin 0. elemanını döndürüyor. 
```

seklindedir.

> Ama Örnek modülunun içinden örnek metodu çağıramayız.

> **char** metod direk karakterlerine ayırıyor.

```ruby

"abc".char  #["a","b","c"] 
```

seklinde olacaktır.

> **.split** metodu kelimeliyi harflerine ayırmayı sağlıyor, *char* ile aynı işi görüyo diyebiliriz.


## Bloklar

- Bloklar isimsiz metodlardır.
- Metodları tek satırda yazabiliyoruz.

```ruby
def topla(a,b) a+b end
topla(3,5)
```
> Bloklar nesne değildir, ancak nesne haline **proc** ve **lambda** getirilebilirler.

- Bir blok oluşturmak için kullanabileceğimiz en kolay yöntem lambdadır.

```
topla = lambda{|a,b| a+b}
```
veya

```
topla = -> a,b {a+b}
```
ikiside aynı şekilde yazılabilir.
> lambda bir nesnedir.

- Bir blok nesnesini çalıştırmak istediğimizde **call** metodunu kullanabiliriz.

```
topla = lambda{|a,b| a+b}
topla.call(2,3)
```
veya 

```
def topla(a,b) a+b end
topla.to_proc
```
**Blogun parametre olarak gönderilmesi**

```ruby
def hesapla(s1,s2,islem) 
islem.call(s1,s2)
end
toplam=hesapla(3,5,lamba{|a,b| a+b})
fark=hesapla(3,5,lambda{|a,b| a-b})
çarpma=hesapla(3,5,lambda{|a,b| a*b})
```
seklinde hesaplanabilir.

- Eger lambda kelimesinin kullanmadan çagırmak istersek, metodu lambda kullandığımızdan haberdar etmek için 

aşagıdaki şekilde kullanılmalıdır.

```ruby
def hesapla(s1,s2,&islem)
islem.call(s1,s2)
toplam=hesapla(3,5){|a,b| a+b}
fark=hesapla(3,5){|a,b| a-b}
```
seklinde olmalıdır..

veya 

```
def hesapla(s1,s2,&islem)
block_given?islem.call(s1,s2); s1+s2
topla=hesapla(3,5)
```

seklindede çagrılabilir.

##### yield

Gönderilen isimsiz bloğu kullanabilmemizi sağlıyor.

```
def hesapla(s1,s2)
block_given? yield(s1,s2); s1+s2
end
toplam=hesapla(3,5)
fark=hesapla(3,5){|a,b| a-b}

```
şeklinde kullanılır.

- Ayrıca *proc* kullanımı performansın artmasınıda sağlıyor.


##### Proc

-Proc nesnesi oluşturmak için Proc.new kullanılır.
-lambda, proc'un özel halidir.  Aralarında cok küçük bir fark var.

**lambda ile proc arasındaki fark** bir metod içerisinde **return** kullanıldığında ortaya çıkmaktadır.lambda kendini metodun bir parçası olarak görmektedir. Ama proc ise metodun asıl kendisi olarak görmektedi, bu nedenle proc return gördüğü zaman direk metodtan çıkmaktadır. Eger metodun direk return den sonra cıkmasını istiyorsak Proc kullanılır. Kısacası *return* olmadığı sürece ikiside aynı şeylerdir.

```ruby
class Kisi
attr_accessor ad, soyad
def isim 
@ad +" "+@soyad
end
end
a=Kisi.new
a.ad = "Ali"
a.soyad = "Kara"
```
seklinde olur, yukarıda kullanılan **attr_accessor** komutu degiskenlerin encapsulation olmasını yani get ve set lerini olusturmaktadır.
 
 










    
	



 


