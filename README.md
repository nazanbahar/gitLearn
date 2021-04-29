# gitLearn
Learning Github 
Git
Versiyon kontrol sistemi
Süreç işidir. Sürüm kontrolü yapılır.
--işbirliği
--takım halinde çalışmak
--değişikliklerin çalışmaması.
Neden Git?
3 temel özelik
--geliştirme süreçlerini izlemek
--eski versiyona dönmek
--hangi değişiklikler
--işbirliği
--proje belli dallara ayrılabilir
backend yada frontend branch

projenin tarihi kaydını alır. 
İki aşama vardır.
1) Local 
2) Remote
1) Local

localrepo: zaman makinası, farklı dallara geçebiliriz. Bunları repoda tutuyoruz. 
staging area: geçiş bölgesi değişiklikten vazgeçebilir.
git commit: yaptığımız değişiklikleri, kaydediyoruz.
2) Remote

Önemli not: önce kendi repository mize gönderiyoruz. Sonra ortak repository'e gönderiyoruz.

GITBASH CODELAR
cd Desktop/
cd repos
cd javacamp

git config --list
git config --global user.name = 'Nazan'

git init
git klasörü oluşturur.

git status
//git status nedir? 
git hangi dosyları takip edecek.

git add .

git status
//status bölgesine geçtik.

git -m 'lesson1: add,update,delete dosyaları gönderildi...'
// commit yaparken ne yaptığımı yazayım.

git status
--on branch master
--nothing to commit, working tree clean

clear
//satır temizler

--değişiklik yap
git status
modified

aslında bizim çalışma bölgemizden geçiş bölgesine göndermiş oluyoruz.

git commit -m 'index html'

gelen ekrana yorum yaz.
ekrandan çıkmak için esc bas, 




Git Bash: https://git-scm.com/​
VS Code: https://code.visualstudio.com/​
Bootstrap Tema: https://startbootstrap.com/themes/res...
Git, GitHub, & Workflow Fundamentals : https://dev.to/mollynem/git-github--workflow-fundamentals-5496
Github fundementals : https://dev.to/t/github
Konu Başlıkları:
Git Nedir?
Neden Git Kullanırız?
Git VSCode Entegrasyonu
Repository Nedir?
Çalışma Dizini Nedir?
Staging Area (Geçiş Bölgesi) Nedir?
Commit Nedir?
Branching Nedir?
Merging Nedir?
Gitignore Nedir?

Temel Git Komutları:
git add
git status
git log
git show
git diff
git rm
git mv
git checkout
git revert
git reset (hard, soft, mixed)
git restore
git reflog
git branch
git merge

Komut Satırı:
touch
rm - mv
cd - dir
ls -al

ArinSoft



## 1 - GIT Nedir?

GIT Kontrol Sistemi'nin ne olduğunu anlatmaya başlamadan önce biraz kültür mantarı moduna geçelim ve "git" kelimesinin anlamı ve bu sistemin kısa tarihsel gelişimi üzerine konulaşım. Peki bunu neden yapıyoruz?

Şu sebepten ötürü; Yazılım dehası Bill Gates çok kitap okuyan, okuduklarını iyi şekilde hatırlayan ve konuşmaları sırasında okuduğu kitaplardan alıntılar yapan bir şahsiyet. Bu kadar okuma yapıp da okuduklarını aklında detaylı şekilde nasıl tuttuğu sorulduğunda Bill Gates;

    Bir konuda okumaya başlamadan önce konu hakkında genel bilgi sahibi olmayı ve konunun tarihini incelemeyi öneriyor. *

Bu içeriğimizde biz de GIT Versiyon Kontrol Sistemi Nedir? sorusuna cevap ararken bu konu hakkında sadece kuru bilgi edinmek yerine bir miktar kültürel kazanım sağlayacağız ki konuyu içselleştirelim ve konu hakkında bir derinlik kazanalım. GIT ile ilgili bu sayfada ve devamındaki sayfalarda öğrendiklerimizi kolay kolay unutmayalım.
"git" Kelimesinin Anlamı

Cambridge Sözlüğe göre; aptal, hoş olmayan kişi anlamına geliyor. [2]

Bu isimlendirme Torvalds'a sorulduğunda kendisi espirili şekilde şu cevabı veriyor:

"Ben bir egoistim ve projelerime kendi ismimi veriyorum. Önceki Linux, şimdiki git."
Torvalds, alternatif olarak kelimenin ruh halinize göre aşağıdaki anlamlara da gelebileceğinden bahsediyor;

    Yaygın bir UNIX komutu tarafından kullanılmayan, telaffuz edilebilir, rastgele üç harfli bir kombinasyon.
    Sözlükteki argo anlamı ile; Aptal, Aşağılık ve Basit.
    "Küresel bilgi izleyici" (Global information Tracker).
    "Kahrolası aptal kamyon dolusu pislik" (Goddamn Idiotic Truckload of sh*t)."

Not: Alıntı, argo ve küfürden arındırılmıştır. Orjinal cevabına buradan ulaşabilirsiniz.)

Görüldüğü üzere aslında çok da kesin bir anlamı yok. Özgür yazılım dünyası sizi burada da özgür bırakmış.
GIT'in Tarihsel Gelişimi

Linux'un mimarı	Linus Torvalds, çok sayıda kişi ile birlikte Linux çekirdeğini geliştirirken projenin yönetimi için o dönem piyasada bulunan BitKeeper adındaki versiyon kontrol sistemini tercih etmiş. Fakat BitKeeper'in telif haklarını elinde bulunduran kişi ile yaşanan yasal sorunlardan ötürü bu kullanımdan vazgeçilmiş.

O günlerde piyasada bulunan versiyon kontrol sistemlerinin hiçbiri aslında Torvalds'ın beklentilerini karşılamıyormuş.

Bu sebeple ihtiyaçlarına çözüm için kolları sıvayan Torvalds, piyasadaki sistemleri inceleyerek kendi versiyon kontrol sistemini yazmaya başlamış. İlk sürüm 2005 yılında piyasaya sürülmüş.

Yayınlanmasından günümüze kadar geçen sürede ise GIT büyük bir pazar hacmine ulaştı.
GIT Versiyon Kontrol Sistemi Nedir?

GIT nedir? diye sorduğunuzda versiyon kontrol sistemi cevabını almışsınızdır. İyi de versiyon kontrol sistemi nedir?

Projemi geliştirirken "proje", "projee", "projee_son", "projee_son_5" şeklinde klasörlesem olmaz mı? GIT öğrenmeden olmaz mı? - OLMAZ!

Son sorudan başlayayım. Eğer profesyonel işler yapacaksanız GIT öğrenmek zorundasınız. Klasör isminin sonuna fazladan harfler, rakamlar ekleyerek proje geliştirmek ilerleyen süreçlerde başa çıkılabilecek bir yöntem değildir.

Versiyon Kontrol Sistemi Nedir? sorusuna gelirsek; Bir döküman (yazılım projesi, ofis belgesi vb.) üzerinde yaptığınız degişiklikleri adım adım izleyen, istediğinizde kayıt eden ve isterseniz bunu internet üzerindeki bir bilgisayarda veya yerel bir cihazda (respository / repo / depo) saklamanızı ve yönetmenizi sağlayan bir sistemdir. [3]

Versiyon Kontrol Sistemi yerine Kaynak Kod Yönetim Sistemi ifadesini de duymuş olabilirsiniz. İkisi de aynı şeyi ifade etmektedir.
GIT Bize Ne Sağlar?

    Birden fazla yerde (dağıtık olarak) dosyalarınızı ve versiyon kontrol bilgilerinizi depolayabilirsiniz. Böylelikle cihaz bağımsız olarak dosyalarınıza erişebilirsiniz.
    "commit" yaparak SnapShot (anlık görüntü) özelliği ile istediğiniz zaman proje veya dosyaların o anki halini kayıt altına alabilirsiniz. Böylelikle ileride bir hata ile karşılaşırsanız herhangi bir zamandaki herhangi bir versiyona dönüş yapabilirsiniz.
    SnapShot alındıktan sonra değişiklik yapılan dosyaları görebilirsiniz.
    Takımların aynı projede beraber çalışmasına imkan verir. Kim neyi düzenledi? Ne ekledi? Ne çıkarttı? Son değişiklik ne zaman yapıldı? gibi bilgilere erişebilirsiniz. Bu sayede topluluk ile proje geliştirme süreçlerini kolaylaştırabilirisiniz.
    Projede verisyonlanmasını istemediğiniz dosyaları belirtebilirsiniz. (node_modules, .mp4, .log, .env gibi)

GIT'i Anladım Fakat GitHub, GitLab, BitBucket Nedir?

En sade şekilde GIT versiyon kontrol sistemini kullanan depolama servisleri diyebiliriz.
GitHub

Yazılımcılar için bir kod kütüphanesi ve bir çeşit sosyal medya ortamıdır.

Yazılım geliştiriciler projelerini halka açık veya özel olarak saklayabilir. Ücretli ve ücretsiz paket seçenekleri mevcuttur.
GitLab

GitHub gibi bir GIT servisidir. Farklı olarak firmalara GitLab'ı kendi sunucularına kurma imkanı verildiği için genelde kurumsal tarafta kullanılır. GitLab ile firmalar kendi içerisinde GIT hizmetlerinden faydalanabilir.
BitBucket

Genelde kişisel kullanıma yöneliktir. GitHub tarafındaki açık kaynak projeler ve sosyal medya ortamı burada gelişmemiştir.

Yukarıda açıkladığımız servisler haricinde GitKraken, SourceTree gibi irili ufaklı farklı servisler de mevcuttur.

GIT sistemini kullanmaya başladığınızda karşınıza daha önce aşina olmadığınız bazı tanımlar çıkacaktır. Temel bazı terimleri kısaca açıklayarak içeriğimizi bitirelim.

    repository: Kısa ismi ile repo. Kodlarınızın saklandığı depodur.

    master: Depodaki kararlı sürüme master denir.

    branch: GIT ağaç mantığı ile çalışır. Bir projeyi versiyonladığımızda master branch'i oluşur. Ana dosya (master) üzerinde değişklik yapmak hem tehlikelidir hem de çok kişi ile yapılan geliştirmelerde karışıklığa sebep olur. Kimin neyi değiştirdiğini takip etmek zorlaşır. Bu sebeple geliştiriciler master'den açılan dallar (branch) üzerinde geliştirmelerini yapar. Kullanıcılar branch (dallar) üzerinde yaptıkları geliştirmeleri master'a birleştirmesi için proje sahibine gönderirler.

    merge: branch'larda yapılan değişikliklerin master branch'ı ile birleştirilmesidir.

    push: Dosyaları repo'ya (depo) göndermek için kullanılır.

    pull: Depodan dosyaları çekmek için kullanılır.

    .gitignore: GIT'in takip etmesini istemediğimiz dosya ve klasörleri belirttiğimiz dökümandır. Mesela node_module klasörünün izlenmesine gerek yoktur ve .gitignore dökümanı içinde bunu belirtiriz.

GIT sisteminde kullanılan komutlara diğer yazımızdan ulaşabilirsiniz.

## 2- GIT Bash ile GIT Temel Komutları

GIT temel komutlarını kullanabilmek için Mac OS X'de Terminal uygulamasını, Windows'da ise GIT Bash'i açarak aşağıdaki komutları çalıştırmanız gerekir.

Örnek Terminal görüntüsü
terminal

**Örnek  GIT Bash görüntüsü
git-bash
GIT Temel Komutları

GitHub-cheat-sheet-graphic

Başlıca bilmemiz gereken bazı terimler;

    untracked (izlenmeyen): GIT tarafından henüz takip edilmeyen, yani yeni oluşturulmuş dosyaları ifade eder.
    unstaged (hazırlanmamış): Güncellenmiş ancak commit’lenmek için hazırlanmamış dosyaları ifade eder.
    staged (hazırlanmış): Commit’lenmeye hazır olan dosyaları ifade eder.
    deleted (silinmiş): Projeden silinmiş ama GIT üzerinden kaldırılmamış dosyaları ifade eder.

git init

Henüz versiyon kontrolü altında olmayan bir projenin dizininde, boş bir git deposu oluşturmak için kullanılır.

$ git init

git-init
git config

GIT’in bir çok konfigürasyon ve ayarı vardır, bunlardan ikisi user.name ve user.email olanıdır. Bu ayarları yapılandırmak için aşağıdaki komutları kullanırız. GIT'i ilk kurduğumuzda genellikle aldığımız ilk hata bu configurasyon ayarlarını yapmadığımız için gelir. Burada yazdığınız isim ve email ileride GitHub benzeri bir plat forma commit attığınızda da görüneceği için bunu bilerek isimlendirme yapmak yararlı olur. Ayrıca görüldüğü gibi bu ayarlar --globalyani sistem genelinde geçerli ayarlardır. Proje bazlı bu ayarları değiştirebiliriz.

$ git config --global user.name "Name Surname"

$ git config --global user.email "test@email.com"

Bu ayarların bütününü görüntülemek için:

$ git config --list

Not:  Eğer windows işletim sistemi kullanıyorsanız, böyle bir hata ile karşılaşabilirsiniz.

    warning: LF will be replaced by CRLF in kaynak/dosya/yolu

Bu hatanın çözümü için aşağıdaki komutu kullanabilirsiniz.

$ git config core.autocrlf true

git add

Yeni eklenen veya üzerinde değişiklik yapılan dosyaları staged ortamına göndermek için kullanılır.

$ git add <dosya veya klasor_name>

Tek seferde bütün dosyaları eklemek için ise:

$ git add .  veya  $ git add *  veya   $ git add -A .

Buradaki -A (all) tümü anlamındadır. . ise tüm dosya uzantılarını ifade eder.
git rm

Staged ortamına eklenmiş bir dosyanın takibinin bırakılması yani untracked (izlenmeyen) hale getirilmesi sağlayan komuttur.

$ git rm  --cached <dosya veya klasor_name>

Dosyayı klasörden silmek istiyorsak eğer, aşağıdaki komutu kullanılırız.

$ git rm <dosya veya klasor_name>

git status

Üzerinde çalışılan projenin o anki durumu hakkında bilgi verir. Yapılan değişiklikler, eklenen ve silinen dosyalar gibi bilgiler listelenir.

$ git status

git-status-1

    On branch main -> Main branch'ınde olduğumuzu,
    Changes to be commited -> Commit'lenmeye hazır değişiklikler olduğunu,
    Modified: index.html -> Index.html dosyasında değişiklik yaptığımızı,
    Deleted: styles.css -> styles.css dosyasını sildiğimizi,

git-status-2

    Changes not staged for commit -> Üzerinde değişiklik yapılan ama staged ortamına gönderilmemiş dosyaları ifade eder.
    Untracked files -> takibi yapılmayan dosyaları ifade eder.

git commit

Commit, staged ortamına alınan dosyaların Local Repository’e gönderilmesidir.  En iyi uygulama yöntemi her kayıt sırasında yapılan değişiklikleri açıklayıcı bir mesaj eklemektir. Ayrıca her commit benzersiz bir kimliğe (unique ID) sahip olur. Bu sayede eski bir commit'e geri dönebilirsiniz ve herhangi bir kayıp yaşama ihtimaliniz kalmaz.

$ git commit -m "ilk commit mesajı"

    Buradaki -m (message) mesaj anlamındadır.

    Bir dili veya framework'ü yeni öğrendiğiniz zaman commit'leri akıllıca kullanmak işimizi oldukça kolaylaştırır. Çünkü eklediğiniz bir işlevsellik veya özelliği hatırlayacağınız bir commitmesajıyla kaydetmek, GIT'in doğası gereği hangi satırlarda değişiklik yaptığınızı gösterdiği için tekrar kullanmak istediğiniz zaman eklemeniz gereken komutları hatırlamanızı kolaylaştırır.

git log

Projedeki commit geçmişini görüntülememizi sağlar. Bütün commit'ler, id'si, yazarı, tarihi ve mesajı ile beraber listelenir.

$ git log

git-log
git branch

Local veya remote repository üzerinde yeni bir branch (dal) eklemek, silmek veya listelemek için kullanılır.

Projenize yeni bir branch eklemek için;

$ git branch <branch_name>

*Tüm uzak ve yerel branch'lari listelemek için;

$ git branch -a

Bir branch'ı silmek için;

$ git branch -d <branch_name>

git checkout

Branch’ler arası veya commit'ler arası geçiş yapmak istediğimizde kullanılır.

Mevcutta var olan branch'a geçiş yapmak için;

$ git checkout <branch_name>

Yeni bir branch oluşturup, bu branch'a geçiş yapmak için;

$ git checkout -b <branch_name>

Commitler arası geçiş yapmak için: (Eski bir versiyona dönmek istediğimiz zaman)

$ git checkout <commit_ID>

git merge

Başka bir branch'da olan değişiklikleri, bulunduğumuz branch ile birleştirmek istediğimizde kullanılır.

$ git merge <branch_name>

git clone

Mevcut bir Remote Repository'de bulunan dosyaların bilgisayarımızda bir kopyasının oluşturulmasını sağlar.

$ git clone <remote_URL>

git push

Projemizde aldığımız commit'leri, remote repository'e gönderir.

$ git push origin master

Burada bahsi geçen origin remote repository’nin kök dizinini belirtir ve sabit bir isimdir. master ise sizin çalıştığınız branch (dal)’ı belirtir.

Henüz remote repository’niz yoksa aşağıdaki komut ile local deponuzu uzak sunucudaki depoya bağlayabilirsiniz.

$ git remote add origin http://uzak_deponun_adresi.git

git diff

Repository üzerinde yapılan değişikliklerden sonra dosyalar arasında oluşan farklılıkları göterir.

Çalışma dizini ile repository (HEAD) arasındaki farklılıkları görmek için:

$ git diff HEAD

İki commit arasındaki farklılıkları görmek için:

$ git diff <commit_id_1>..<commit_id_2>

Çalışma dizini ve staged ortamı arasındaki farkları görmek için:

$ git diff --staged

Kaynaklar

    https://medium.com/fedeveloper/git-bash-ile-komut-komut-versiyonlama-a354efd3063f
    https://www.jrebel.com/blog/git-cheat-sheet
    http://guides.beanstalkapp.com/version-control/common-git-commands.html
    

## 3- VS Code içinde Terminal Kullanarak GIT Temel Komutları

GIT temel komutlarını VS Code içerisindeki terminalde kullanmak için menü barından **Terminal'i (1) **açarak New Terminal (2) seçeneğini seçmelisiniz.

## 4- .gitignore Dosyası Ne İşe Yarar? Nasıl Kullanırız?

.gitignore dosyası projemizin kök dizinine oluşturulan düz bir metin dosyasıdır. Adından anlaşıldığı gibi diyor ki beni göz ardı et. Daha doğrusu göz ardı etmek istediğin, local çalışma alanındaki takip edilmesini istemediğin, takım arkadaşların için gerekmeyen dosyaların varsa veya bu dosyaların boyutu reponuza atmanıza gerek olmayacak kadar büyük ölçekli ise buyur beni kullan diyor.

Gel bu dosyaları .gitignore dosyasına koy ki GIT de senin bu dosyalarını artık takip etmesin. Üstelik bu işlemler yapılırken senin halihazırdaki dosyalarını da hiç bir şekilde etkilemesin. Daha ne olsun!
Peki nedir bu tür dosyalar ?

    Paket yöneticisinden indirilen bağımlılıklar,
    image ve video dosyalarınız(dosya boyutları çok fazla olabilir)
    IDE eklentileri( örneğin .vscode)
    Sadece kendi çalışma alanınızda olması gereken başkaları tarafından görülmemesi gereken dosyalarınız (veritabanınıza ilişkin konfigurasyonlar)
    API anahtarları, kimlik bilgileri veya hassas bilgiler içeren dosyalar(.env)
    Çalışma dizinizdeki geçici dosyalar
    Log dosyaları
    Yararsız sistem dosyaları (örneğin MacOS işletim sisteminin .DS_Store dosyası )
    dist gibi oluşturulan dosyalar
    Veya herhangi bir dosyanız da olabilir.

Nasıl oluşturulur?

Reponuzu oluştururken verilen seçeneklerde add gitignore file dosyasına tıklayarak reponuzla beraber oluşturabilirsiniz. Aynı şekilde editörünüzde .gitignore şeklinde de oluşturabilirsiniz.

    .gitignore dosyası .ile başladığı için Mac ve Linux sistemlerde gizli dosya olarak aldılanır. . ile başlayan klasör ve dosyalar bu sistemlerde gizlenir. Dosyayı oluşturmanıza rağmen göremiyorsanız gizli dosya/klasörleri göster seçeneğini açın!

Yok ben terminal aşığıyım diyorsanız da buyrun :)

Proje dizininize cd komutu ile gelerek
**MacOS /Unix için; **

$ touch .gitignore 

Windows için;

$ echo some-text or nothing > .gitignore

şeklindeki komutlarla dosyanızı komut satırından oluşturabilirsiniz. Buradaki some-text or nothing kısmı .gitignore dosyasına yazılmasını istediğiniz metini ekler. Hiçbir şey de yazmayabilirsiniz.
Nasıl  çalışır, nasıl kullanılmalı?

.gitignore dosyasının her satırına takip edilmesini istemediğimiz dosyaları veya dizinleri yazarak göz ardı edebiliriz.

Tabii bu dosyaları yazarken bize kolaylık sağlayan bazı formatlar var.  İşte onlar:

    En basit haliyle dosyamızın ismini ekleyebiliriz. bu komut .envdosyasını göz ardı edecek.

.env

- Dizinleri ise klasörün sonuna `/` işareti ekleyerek  belirtiriz. 

node-modules/
dist/
logs/


- `*` yıldız karakteriyle ise belirtilen ilk örnekte `.log` uzantısına sahip dosyaların tümünü, ikinci örnekte ise `files` klasör içerisindeki bütün dosyaları izlemeyi bırakacaktır. 

.log
files/


- Eğer ki bir klasörümüzü içerisindeki bir dosya haricinde izlenmesini istemiyorsak `!` işareti ile bunu sağlayabiliriz. Bu örnekte `files` klasörü içerisindeki `example.txt` haricindeki dosyalar izlenmeyecektir. Files klasörü içerisindeki sadece **example.txt** git akışında görülecektir.

!files/example.txt


- Yukarıdaki örnekte dikkat edilmesi gereken önemli bir ayrıntıyı açıklayacak olursak eğer ki daha öncesinde `files` klasörü `.gitignore` dosyasına eklenmişse sonrasında ise `!`  içerisindeki dosya ile işlem yapmak işe **yaramayacaktır.**

files/
!files/example.txt


- `.gitignore` dosyasında yorum satırı oluşturmak için ise `#` karakteri kullanılır.

production

/build
dependencies

/node_modules


Kullanımından da bahsettiğimize göre gelelim dikkat edilmesi gereken hususlara...

## Neye dikkat etmeliyim?

- Eğer projenizi `git add .` veya `git commit ` etmişseniz sonrasında  `.gitignore`  dosyasına eklemek istediğiniz dosyayı ekleseniz de bu işlem gerçekleşmeyecektir ve o dosyanız reponuzda hala GIT ile takip edilecektir. Tabi her şeyin bir çözümü olduğu gibi bu sorunu da çözmenin bir yolu var. İşte o çözüm .

```bash
$ git rm --cached FILENAME

    Hani olur da derseniz ben belli dosyalarımı her seferinde .gitignore dosyasına eklemek istemiyorum bunu tek seferde halledebilir miyim ? Tabii ki buna da bir çözüm bulmuş GIT babamız :)

Burada kastımız başka başka projeler için her seferinde eklememek.

    Windows kullanıcısı iseniz  C:\Users\{myusername}\ adresine giderek  .gitignore_global dosyası oluşturup içerisine global olmasını istediğiniz dosyaları ekledikten sonra git bash terminalinizi açarak aşağıdakı komut ile konfigürasyon sağlayabilirsiniz.

$ git config --global core.excludesfile "%USERPROFILE%\.gitignore"

    Dosyanızın doğru çalıştığını kontrol etmek için ise aşağıdaki komutu çalıştırarak aşağıdaki çıktıyı aldığınızda sorunsuz çalıştırabilmişsinizdir. (Aşağıdaki kodu kopyala yapıştır yapmadan önce kullanıcı adını değiştirin.)

$ git config --global core.excludesfile
> C:/Users/user-name/.gitignore_global  

    Son olarak hangi .gitignore dosyalarını eklemeliyim derseniz buradan hangi dil, framework vs kullanıyorsanız ona ait .gitignore dosyalarını bulabilirsiniz. Global olarak düzenlemek istediğiniz .gitignore dosyalarına da buradan erişebilirsiniz.

Kaynaklar:

    https://docs.github.com/en/free-pro-team@latest/github/using-git/ignoring-files
    https://www.pluralsight.com/guides/how-to-use-gitignore-file
    http://git-scm.com/docs/gitignore
    https://sebastiandedeyne.com/setting-up-a-global-gitignore-file/ 
    
5- GIT - Proje İçindeki Birden Fazla Dosyanın Versiyon Kontrol Sistemine Eklenebilmesi

Bu yazımızda projelerimizde bulunan birden fazla dosyanın versiyon kontrol sistemine gönderilmesi ve nasıl kontrol edebileceğimiz ile ilgili komutları inceliyor olacağız.

    .gitignore dosyamız varsa ve bunu düzenli olarak kontrol edebiliyorsak tüm dosyalarımızı teker teker GIT Versiyon Kontrol Sistemi'ne göndermek zorunda değiliz, tek komut ile bunu yapabiliriz.

git add

Bu komut belirttiğimiz dosyaları veya tüm proje dosyalarını versiyon kontrol sistemine göndermemize yardımcı olur.
Aşağıdaki kullanım index.js dosyamızı versiyon kontrol sistemine göndermiş oluruz.

git add index.js

git add komutumuzun sonuna . ifadesini kullanarak versiyon kontrol sistemine tüm dosyalarımızı göndermiş oluruz.

git add .

git commit

git commit -m "ilk commit" komutu çalıştırdığımızda “ilk commit” başlığıyla o anki çalışma dizinindeki dosyaları .gitklasörü içindeki özel bir bölüme(head) ekler.

test foto
git push

Commit’lediğimiz dosyaları versiyon kontrol sistemimize gönderir.

test foto

GitHub hesabımızı kontrol ettiğimizde tüm dosyaların ve commit işlemlerimizin ulaştığını görmüş oluruz.

## 6- GitHub'a Projemizin Eklenmesi ve Diğer Repo Hosting Web Platformları

GitHub'da repo oluşturabilmek için hesap oluşturma aşamalarından sonra profilimizde bulunan "Repositories" menüsünden sağ kısımda bulunan "New" butonu ile repo oluşturma kısmına erişebiliriz.

test foto

    Owner: Reponun sahibinin seçiyoruz.
    Repository name: Oluşturduğumuz reponun adını belirliyoruz.
    Description: Repomuz için bir açıklama girebiliriz.
    Public: Repomuzun tüm herkesin erişimini sağlar.
    Private: Bu seçenek sayesinde repomuzu gizli bir şekilde oluşturabiliriz.
    Add a README file: Repomuza öncesinde README dosyası oluşturmuş oluruz, dilersek daha sonrasında kendimiz ekleyebilir ve güncelleyebiliriz.
    Add .gitignore: Repomuza öncesinde .gitignore dosyası oluşturabilir ve göndermek istemediğimiz dosyaları seçebiliriz, daha sonrasında aynı işlemi yapabilir ve .gitignore dosyamızı güncelleyebiliriz.
    Choose a license: Reponuz için bir lisans seçimi yapabilmenizi sağlar.

Gerekli işlemleri tamamladıktan sonra "Create repository" diyerek repomuzu oluşturmuş oluruz.

test foto

Oluşturmuş olduğumuz repomuza bilgisayarımızdan erişebilmek için gerekli işlemleri yapmaya başlayalım.

Bilgisayarımızda oluşturmuş olduğumuz klasörümüze konsol ekranımızdan veya kullandığımız IDE yardımı ile erişim sağladıktan sonra git init komutumuzu çalıştıralım.

test foto

Klasörümüz hazır, öncelikle README.md dosyamızı oluşturalım ve repomuza ilk push işlemini yapabilmek için adımları tamamlayalım.

test foto

Eklemiş olduğumuz README dosyasını repomuza gönderebilmek için git add README.md komutumuzu ile README dosyasının GitHub repomuza göndermek üzere hazırlayalım.

test foto

Repomuza son yapılan değişikleri göndermeden önce git commit -m "ilk yorum" komutu ile neler yaptığımızı yazalım.

test foto

Bize belirtilen şekilde git branch -M main komutunu konsol ekranımızda çalıştıralım ve main branch oluşturalım.

test foto

Son aşamaya gelmeden önce ise git remote add origin 'repo-link' komutu ile remote bağlantımızı ekleyelim.

test foto

Son aşama olarak git push -u origin main komutu ile repomuza dosyalarımızı gönderelim.

test foto

Ve ilk push işlemimiz ile birlikte tüm değişikliklerimizi GitHub repomuza göndermiş olduk. GitHub sayfasını yeniden yüklediğimizde böyle bir ekran ile karşılaşmış olacağız.

test foto

Böylece README dosyamızı repomuza göndermiş olduk. Sağ tarafta bulunan "1 commit" yazısının üstüne tıklayarak ise commit ile ilgili detayları görmüş oluruz.

test foto

Daha fazla detay görmek için ise sağ tarafta görünen mavi renk ile belirtilmiş commit işlemimiz için özel olarak random şekilde atanmış benzersiz yazı kısmının üstüne gelerek tıklamanız yeterli olacaktır.

test foto

Bu kısımda ise commit hakkında yorum yazabilir ve detaylı olarak değişiklikleri gözden geçirebilirsiniz.

## 7 - Markdown Nedir ?

Markdown, John Gruber ve Aaron Swartz tarafından geliştirilen ve 2004 yılından bu yana kullanılan metinden HTML'e (text-to-HTML) dönüşüm için kullanılan hafif bir işaretleme dilidir.

GitHub gibi platformları kullananların aşina olduğu Markdown formatı, yaygın kanının aksine sadece README dosyaları oluşturmak kullanılmaz. Temel amaç okunabilirliği ve kullanılabilirliği arttırmaktır. Basitliği ve sadeliği sayesinde forumlarda ileti yazmaktan, kitap yazmaya kadar pek çok yerde kullanılabilir. Asıl güçlü olduğu kısım klavyeden elinizi kaldırmadan tablolardan, matematiksel ifadelere kadar ihtiyaç duyduğunuz her şeyi oluşturabilmeniz ve sonrasında biçimlendirebilmenizdir.

Sözü fazla uzatmadan dilerseniz örnekler üzerinden ilerleyelim. Başta da dediğim gibi zaten oldukça basit bir yapısı var, çok seveceğinizi düşünüyorum.
Başlıklar

HTML'de <h1>, <h2>, <h3> etiketleri ile aç-kapat yaparak oluşturduğumuz başlıkları, Markdown ile sadece # karakteri kullanarak oluşturabiliyoruz. Burada önemli olan nokta # karakterinden sonra boşluk bırakmaktır.
Markdown	HTML	Çıktı
# h1 Başlık	<h1> h1 Başlık </h1>	<h1> h1 Başlık </h1>
## h2 Başlık	<h2> h2 Başlık </h2>	<h2> h2 Başlık </h2>
### h3 Başlık	<h3> h3 Başlık </h3>	<h3> h3 Başlık </h3>
#### h4 Başlık	<h4> h4 Başlık </h4>	<h4> h4 Başlık </h4>
##### h5 Başlık	<h5> h5 Başlık </h5>	<h5> h5 Başlık </h5>
###### h6 Başlık	<h6> h6 Başlık </h6>	<h6> h6 Başlık </h6>

h1 ve h2 başlıklar yazarken alternatif olarak bir yöntem daha mevcut. h1 için = ve h2 için - kullanabilirsiniz.
Markdown	HTML	Çıktı
# h1 Başlık ========	<h1> h1 Başlık </h1>	<h1> h1 Başlık </h1>
## h2 Başlık --------------	<h2> h2 Başlık </h2>	<h2> h2 Başlık </h2>

Not: h1 ve h2 başlıklarda GitHub'ın yaptığı özelleştirme sebebiyle otomatik olarak gri bir çizgi geliyor.
Paragraf

Paragraf oluşturmak için haricen bir işlem yapmak gerekmiyor. Markdown formatında yazıyorsanız yeni bir satır oluşturmak paragraf için yeterli. Bir paragraf tek satırdan oluşabileceği gibi, arada boşluk bırakmadan alt satırdan devam etmek de mümkün.
Kalın, Eğik ve Üstü Çizili İfadeler

    Bir ifadeyi;
        Kalın yapmak için ifadenin başına ve sonuna 2 adet ** yıldız karakteri veya __ 2 adet alt tire,
        Eğik yapmak için ifadenin başına ve sonuna 1 adet * yıldız karakteri veya _ 1 adet alt tire,
        Hem kalın hem de eğik yapmak için ise ifadenin başına ve sonuna *** veya ___ veya **_ veya __*,
        Üstü çizili yazmak için ise ifadeni başına ve sonuna 2adet ~~ karakteri ekleyebilirsiniz.

Yaygın kullanımda kalın yazmak için **, eğik yazmak için *, hem kalın hem eğik yazmak için *** kullanılmaktadır.
Tek ve Çok Satırlı Kod Blokları

    Tek satır kod bloğu için kodun başına ve sonuna ` (backtick) karakteri eklenir.

`console.log("Hello, World!");`

Çıktı:
console.log("Hello, World!");

    Çok satır kod bloğu için kodun başına ve sonuna 3 adet  ``` backtick karakteri eklenir.

Çıktı:

function (){
console.log("Hello, World!);
}

    Yazılım diline göre kod bloğundaki ifadelerin stillendirilmesini isterseniz, kod bloğunun başındaki 3 adet backtick ifadesinden sonra javascript, python, css gibi etiket ekleybilirsiniz.

Çıktı:

    function (){
      console.log("Hello, World!);
    }

Yatay Çizgi

İçerikte bölümleme yapmak için --- kullanabilirsiniz. HTML'deki karşılığı <hr> olan bu ifade;

Çıktı:

Size yukarıdaki gibi bir çizgi üretir.
Listeler

HTML'de <ul> </ul> ve <li> </li> etiketleri ile oluşturulan listeler Markdown formatında - ve * ile oluşturulur.

    - Liste Elemanı 1
    - Liste Elemanı 2
    - Liste Elemanı 3

Size aşağıdaki çıktıyı üretir;

    Liste Elemanı 1
    Liste Elemanı 2
    Liste Elemanı 3

Sıralı liste elde etmek için tek yapmanız gereken liste elemanlarının başına sıra numarası ve . nokta eklemek.

1. Liste Elemanı
2. Liste Elemanı
3. Liste Elemanı

Çıktı:

    Liste Elemanı
    Liste Elemanı
    Liste Elemanı

Buradaki önemli nokta şu: Siz farklı sıra numaraları vermek isteseniz de Markdown sıra numaralarını otomatik olarak biçimlendirmektedir. Aşağıdaki örnek üzerinden inceleyelim;

1. Liste Elemanı
8. Liste Elemanı
13. Liste Elemanı

Çıktı:

    Liste Elemanı
    Liste Elemanı
    Liste Elemanı

Gördüldüğü üzere biz 1, 8 ve 13 olarak numaralandırdık fakat çıktı sıralı olarak üretildi.

Markdown ile iç içe listeler yapmak da oldukça kolay. Alt listelere tab ile girinti verdiğinizde otomatik olarak nested list yapısına dönüşmekte.

1. Liste Elemanı
    1. Alt Liste Elemanı
    2. Alt Liste Elemanı
2. Liste Elemanı
3. Liste Elemanı

Çıktı:

    Liste Elemanı
        Alt Liste Elemanı
        Alt Liste Elemanı
    Liste Elemanı
    Liste Elemanı

Tablolar

Tablo oluşturmak için aşağıdaki yapı kullanılır. Satır çizgisi için kullanılan - karaterine, : işareti eklenerek tabloda sola, sağa veya ortaya hizalama yapılabilir.

| Ürünlerin Numaraları| Ürün Açıklaması| Ürünlerin Fiyatı|
| :--- | :---: | ---: |
| 1 | Açıklama | Fiyatı |

Çıktı:
Ürün Numaraları	Ürün Açıklaması	Ürünlerin Fiyatı
1	Açıklama	Fiyatı
Bağlantı ve Resim Eklemek

HTML'den aşina olduğumuz <a> etiketi yerine Markdown'da []() karakterleri ile;

[Kodluyoruz Sayfamız](https://www.kodluyoruz.org/)

yapısı kullanılır. Köşeli parantez bağlantı açıklamasını, küme parantezi ise linki barındırır.

Çıktı ise şöyledir;
Kodluyoruz Sayfamız

Bağlantı resimleri de aynı şekilde eklenir. Sadece köşeli parantezden önce bir tane ! ünlem işareti eklenmelidir.

![Kodluyoruz Logo](https://raw.githubusercontent.com/Kodluyoruz/taskforce/git/git/markdown-nedir-nasil-kullaniriz-/figures/kodluyoruz_logo.jpg)

Yapısı kullanılır. Köşeli parantezin için doldurmak zorunlu değildir. Boş da kalabilir. Çıktı aşağıdaki gibi olacaktır;

Kodluyoruz Logo
Alıntı

Yazınız içinde alıntı kullanmak isterseniz yapmanız gereken, metinin başına > karakteri koymaktır.

> Alıntı yapılan metin.

Elde ettiğimiz çıktı:

    Alıntı yapılan metin.

https://www.patika.dev/egitimler/java-ile-backend-web-development-patikasi/git/markdown-nedir-nasil-kullaniriz-









