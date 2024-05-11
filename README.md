## git config
Yapılan değişikliklerin hangi kullanıcı tarafından gerçekleştirildiğini görmeni sağlar. Git'in yapılandırma ayarlarını yapılandırmak veya görüntülemek için kullanılan bir komuttur. Bu komut, Git'in davranışlarını, kullanıcı bilgilerini ve diğer çeşitli ayarları yapılandırmak için kullanılır. Örneğin, kullanıcı adı, e-posta adresi, renk tercihleri, dış gereç yapılandırmaları gibi birçok ayarı yapılandırmak için kullanılabilir. git config komutu, sistem düzeyinde, global düzeyde (tüm kullanıcılar için) ve yerel düzeyde (belirli bir depo için) yapılandırma yapma yeteneğine sahiptir.

*`git config --global user.name "muhammed cetin"`* > Versiyonlamada görünecek isim bölümü. Git'in global yapılandırma ayarlarından biri olan kullanıcı adını belirlemek için kullanılır.

*`git config --global user.email "muhammed.cetinnm@gmail.com"`* > Versiyonlamada görünecek email bölümü. Git'in global yapılandırma ayarlarından biri olan kullanıcı e-posta adresini belirlemek için kullanılır. 

*`git config --global -l`* > Git'in global düzeydeki yapılandırma ayarlarını listeler. Global düzeydeki yapılandırma, bir kullanıcının tüm Git depoları için geçerlidir. Örneğin, kullanıcı adı ve e-posta adresi gibi bilgileri içerebilir.

*`git config --list`* > Git yapılandırma ayarlarını listelemek için kullanılan bir komuttur. Bu komut, sistem, global ve yerel düzeydeki Git yapılandırma ayarlarını gösterir. Bu ayarlar, kullanıcı adı, e-posta adresi, renk tercihleri, dış gereç yapılandırmaları gibi birçok ayarı içerebilir. 
##
## git init
Git deposu oluşturmak için kullanılan bir komuttur. Bu komut, mevcut bir dizini Git deposuna dönüştürür ve proje dosyalarını izlemeye başlar. 

*`git init [repository adı]`* > Eğer [repository adı] belirtilirse, Git bu adla bir klasör oluşturur ve bu klasörü Git deposu olarak başlatır.
##
## git status
Çalışma dizininin ve Git deposunun durumunu gösterir. Bu komut, değişiklik yapılan dosyaları, yeni eklenen dosyaları, silinen dosyaları, işlenmeyi bekleyen değişiklikleri ve mevcut dalın durumunu gösterir.

*`git status`* > Git deposuyla çalışırken hangi değişikliklerin yapıldığını izlemek ve bu değişikliklerin durumunu anlamak için sıkça kullanılır.
##
## git add
Çalışma dizinindeki dosyaları Git tarafından izlenen (staged) dosyalara eklemek için kullanılan bir komuttur. Bu komut, bir sonraki commit'e dahil etmek istediğiniz dosyaları belirtmenize olanak tanır.

*`git add [dosya adı]`* > Belirli bir dosyanın adı. Bu, sadece belirli bir dosyayı staged yapmak için kullanılır.

*`git add .`* > Çalışma dizinindeki tüm değişiklikleri staged yapar. Yani, bu komut, tüm dosyaları sonraki commit'e dahil etmek için hazırlar.
##
## git commit
Git deposunda yapılan değişiklikleri kaydetmek için kullanılan bir komuttur. Yapılan değişikliklerin kalıcı bir anlam kazanması için kullanılır. Bu komut, yapılan değişikliklerin bir "commit" olarak adlandırılan bir kayıt altında saklanmasını sağlar.

*`git commit -a -m "commit_mesajı"`* > *`-a`* Tüm değiştirilmiş veya silinmiş dosyaları otomatik olarak staged yapar. Bu komut, yeni eklenen dosyaları veya tamamen silinen dosyaları dikkate almaz. Bu yüzden yeni eklenen dosyaları commit'e dahil etmek için ayrıca git add komutu kullanılmalıdır.

*`git commit -m "commit_mesajı"`* > *`-m`* Commit işlemini açıklayan bir mesaj ekler. Bu mesaj, yapılan değişikliklerin ne hakkında olduğunu açıklamak için kullanılır.
##
## git log
Git deposundaki commit geçmişini göstermek için kullanılan bir komuttur. Bu komut, yapılan commitlerin listesini, her commitin kim tarafından yapıldığını, ne zaman yapıldığını ve commit'e eklendiği mesajı içeren bir çıktı olarak sunar.

*`git log`* > Bu komut, en yeni commit'ten başlayarak en eskiye doğru tüm commitleri gösterir.

*`git log --follow [dosya_adı]`* > Belirli bir dosyanın geçmişini takip etmek için kullanılır. Bu komut, dosyanın adını belirtir ve bu dosyanın geçmişindeki tüm commitleri gösterir, dosya adı değiştiği takdirde bile. Normal git log komutu dosyanın geçmişini takip etmez. Dosya adı değişirse veya taşınırsa, git log sadece dosyanın o andaki konumunu gösterir. Ancak --follow parametresi, dosya adı değişse bile bu dosyanın geçmişini takip etmek için kullanılır.
##
## git diff
Bu komut, en son commit ile çalışma dizinizdeki dosyalar arasındaki farkları gösterir. Yani, son commit'ten sonra yapılan değişiklikleri sizin gözünüzde canlandırır. Bir dosyayı açtığınızda neyin değiştiğini, eklenip silinen veya düzeltilen satırları size gösterir. Bu dosyalar henüz staged (izlenen) olmayan değişikliklerdir, yani henüz bir sonraki commit'e dahil edilmemişlerdir.

*`git diff [kaynak] [hedef]`* > *`kaynak`* Karşılaştırma yapılacak olan kaynak commit, branch veya etiket.
                                *`hedef`*  Karşılaştırma yapılacak olan hedef commit, branch veya etiket.

*`git diff --staged`* > Bu komut, son commit ile staged (izlenen) dosyalar arasındaki farkları gösterir. Staged dosyalar, yani git add komutu ile işaretlenmiş dosyalar, bir sonraki commit'e dahil edilmek üzere hazır bekleyen dosyalardır. Bu komut, hangi değişikliklerin bir sonraki commit'e ekleneceğini görmek için kullanılır.
##
## git reset
Git deposundaki HEAD konumunu, çalışma dizinindeki dosyaları ve staged (izlenen) değişiklikleri geri almak veya değiştirmek için kullanılan bir komuttur. Başka bir deyişle, bir önceki commit'e, belirli bir commit'e veya belirli bir noktaya geri dönmek için kullanılır.

*`git reset --soft [commit]`* > HEAD konumunu belirtilen commit'e ayarlar, ancak değişiklikleri ve staged (izlenen) dosyaları değiştirmez. Bu mod, sadece HEAD konumunu geri almak için kullanılır ve dosyaları geri almak istemezseniz kullanışlıdır.

*`git reset --mixed [commit]`* *`git reset [commit]`* > HEAD konumunu belirtilen commit'e ayarlar ve staged (izlenen) dosyaları geri alır, ancak çalışma dizinindeki dosyaları etkilemez. Yani, staged (izlenen) dosyalar geri alınır, ancak değişiklikleriniz dosyalarda kalır ve çalışma dizinindeki dosyaların durumu değişmez.

*`git reset --hard [commit]`* > HEAD konumunu belirtilen commit'e ayarlar ve hem staged (izlenen) dosyaları hem de çalışma dizinindeki dosyaları geri alır. Yani, hem staged (izlenen) dosyaların hem de çalışma dizinindeki dosyaların durumu belirtilen commit'e geri döner ve bu noktadan itibaren tüm değişiklikler kaybolur. Bu mod, tüm değişiklikleri geri almak ve başlangıç ​​noktasına geri dönmek istediğinizde kullanılır, ancak dikkatli kullanılmalıdır çünkü geri alınamayan değişikliklere neden olabilir.

*`git reset [dosya]`* > Komutu dosya içeriğini değiştirmez. Bu komut sadece belirtilen dosyanın staged (izlenen) değişikliklerini geri alır. Yani, dosyanın son commit'teki durumuna geri döner.

##
## git rm
Git deposundan bir dosyayı silmek için kullanılan bir komuttur. Bu komut, belirtilen dosyayı çalışma dizininden siler ve aynı zamanda bu silme işlemini Git deposuna da bildirir.

*`git rm [dosya_adı]`* > *`dosya_adı`* Silmek istediğiniz dosyanın adı veya yolu.
##
## git show
Belirli bir commit'in değişikliklerini ve metadata bilgilerini göstermek için kullanılan bir Git komutudur.

*`git show [commit_id]`* > *`commit_id`* Göstermek istediğiniz commit'in benzersiz kimlik numarası veya başka bir referansı.
##
## git tag
Belirli bir commit'e ad vermek veya etiketlemek için kullanılan bir Git komutudur. Bu etiketler, belirli bir noktayı işaret etmek veya belirli bir sürümü belirtmek için kullanılır.

*`git tag [etiket_adı]`* > *`etiket_adı`* Verilmek istenen etiketin adı.
##
## git mv
Git deposunda dosya taşıma işlemi için kullanılan bir komuttur. Bu komut, bir dosyayı bir dizinden başka bir dizine taşırken, aynı zamanda Git'in dosya takip sistemini günceller.

*`git mv [eski_dosya_yolu_yada_adı] [yeni_dosya_yolu_yada_adı]`* > *`eski_dosya_yolu_yada_adı`* Taşınacak olan mevcut dosyanın yolu veya adı.
                                                                   *`eski_dosya_yolu_yada_adı`* Dosyanın taşınacağı yeni yol veya yeni ad.
##
## git alias
Git komutlarını kısaltmak veya özelleştirmek için kullanılan bir özelliktir. Bu özellik, sık kullanılan veya karmaşık Git komutlarını daha kısa veya daha anlaşılır isimlerle çağırmak için kullanılır.

*`git config --global alias.alias_adı 'git_komutu'`* > *`alias_adı`* Tanımlamak istediğiniz alias'ın adı.
                                                       *`git_komutu`* Alias'ın temsil etmesini istediğiniz Git komutu veya komut dizisi.

*`git config --global alias.co checkout'`* > Bu komut, git co komutunu git checkout komutuna eşitler. Artık git co komutunu çağırdığınızda, aslında git checkout komutu çalıştırılmış olur.
##
## git branch
Git deposunda dalları oluşturmak, listelemek veya silmek için kullanılan bir komuttur. Bir "dal", projenin belirli bir noktasını temsil eden bir referanstır. Projenin farklı özelliklerini veya değişikliklerini izlemek için dallar oluşturulur.

*`git branch'`* > Dalları Listeleme: Tüm mevcut dalları listelemek için kullanılır.

*`git branch yeni_dal_adı'`* > Yeni Dal Oluşturma: Yeni bir dal oluşturmak için kullanılır.

*`git branch -d dal_adı`* > Dal Silme: Bir dalı silmek için kullanılır.
##
## git checkout
Git deposundaki dalları değiştirmek, dosyalar arasında geçiş yapmak veya belirli bir commit'e geri dönmek için kullanılan çok yönlü bir komuttur.

*`git checkout dal_adı'`* > Dal Değiştirme: Bir dalı çalışma dali yapmak için kullanılır.

*`git checkout -b yeni_dal_adı'`* > Yeni Dal Oluşturma ve Değiştirme: Yeni bir dal oluşturup ona geçmek için kullanılır.

*`git checkout -- dosya_adı`* > Dosya Geri Yükleme: Çalışma dizinindeki dosyaları belirli bir commit'in durumuna geri yüklemek için kullanılır.

*`git checkout commit_id`* > Belirli bir commit'e geçiş yapmak için kullanılır.

*`git checkout başka_dal_adı -- dosya_adı`* > Kapsayıcı Dallardan Dosya Alma: Başka bir dalda yapılan değişiklikleri almak için kullanılır.
##
## git fetch
uzak bir depodaki (genellikle GitHub veya GitLab gibi) değişiklikleri yerel depoya getirmek için kullanılan bir Git komutudur. Bu komut, uzak depodaki değişiklikleri indirir ancak yerel çalışma alanınızı güncellemez. Bunun yerine, indirilen değişiklikleri yerel depoda bir "uzak dal" olarak saklar.

*`git checkout başka_dal_adı -- dosya_adı`* > *`<uzak_depo_adı>`* Değişikliklerin alınacağı uzak depo adı (genellikle origin olarak adlandırılır).
##
## git merge
Farklı dallardaki değişiklikleri birleştirmek için kullanılan bir Git komutudur. Bu komut, iki veya daha fazla dalın değişikliklerini tek bir dalda birleştirir.

*`git merge daldaki_değişikliklerin_alınacağı_dal`* > Bu komut, belirtilen daki_değişikliklerin_alınacağı_dal'daki değişiklikleri mevcut çalışma dalına birleştirir. Örneğin, master dalında çalışıyorsanız ve feature adında başka bir dalda yeni bir özellik geliştirdiyseniz, git merge feature komutunu kullanarak bu yeni özelliği master dala birleştirebilirsiniz. Bu, feature daki_değişikliklerin_alınacağı_dal'daki değişiklikleri master daki_değişikliklerin_alınacağı_dal'ya ekler.
##
## git rebase
Git'te iki farklı dalı birleştirme yöntemlerinden biridir. Bu komut, belirli bir dalın son commit'ini alır, onu başka bir dala ekler ve sonrasında belirtilen daldaki commit'leri tekrar uygular. Yani, rebase işlemi, iki dala ait commit geçmişlerini birleştirirken, daha düzgün ve lineer bir geçmiş oluşturmayı amaçlar.

*`git rebase <hedef_dal>`* > *`<hedef_dal>`* Rebase işlemi uygulanacak hedef dalın adı veya referansı.

*`git rebase [branch adı]`* > Bu komutu yeniden temellendirme ya da belirtilen işlem demetlerini birleştirme için kullanabilirsin.
##
## git remote
Uzak depoların (remote repository) listesini gösterir. Uzak depo eklemek, silmek veya adını değiştirmek gibi uzak depo yönetimi işlemlerini gerçekleştirir.

*`git remote`* > Uzak depoların listesini göstermek için kullanılır.

*`git remote add remote_adı remote_url`* > Uzak depo eklemek için kullanılır.

*`git remote remove remote_adı`* > Uzak depo silmek için kullanılır.

*`git remote rename eski_ad yeni_ad`* > Uzak depo adını değiştirmek için kullanılır.
##
## git push
Yerel Git deposundaki değişiklikleri uzak bir depoya (örneğin GitHub veya GitLab gibi) göndermek için kullanılan bir Git komutudur. Yerel çalışma alanınızdaki commit'leri uzak bir depoya yüklemenizi sağlar, böylece diğer ekip üyeleriyle veya projenin diğer kopyalarıyla değişiklikleri paylaşabilirsiniz.

*`git push <uzak_depo_adı> <uzak_dal_adı>`* > *`<uzak_depo_adı>`* Değişikliklerin gönderileceği uzak depo adı (örneğin origin).
                                              *`uzak_dal_adı`*  Değişikliklerin gönderileceği uzak dal adı (örneğin main veya master).

*`git push origin main`* > Bu komut, yerel çalışma alanındaki commit'leri origin adlı uzak depodaki main dalına gönderir.

*`git push [değişken adı] master`* > Belirli bir değişken adını (örneğin, origin) ve bir dalı (örneğin, master) belirterek, yerel master dalındaki değişiklikleri uzak sunucuya (origin olarak tanımlanmış olan) gönderir. Bu, yerel master dalındaki değişiklikleri uzak sunucunun master dalına itmek için kullanılır.

*`git push [variable name] [branch]`* > Belirtilen değişken adını ve dalı kullanarak, yerel bir dalı uzak bir depoya gönderir. Bu, belirli bir değişken adını ve dalı kullanarak değişiklikleri uzak sunucuya göndermek için kullanılır.

*`git push --all [değişken adı]`* > Tüm yerel dalları ve değişiklikleri belirtilen değişken adındaki uzak sunucuya gönderir. Bu, tüm yerel dalları ve değişiklikleri uzak sunucuya göndermek için kullanılır.

*`git push [değişken adı] :[branch name]`* > Belirtilen değişken adı ve dal adını kullanarak, uzak sunucudan belirtilen dalı siler. Bu, uzak sunucudan belirli bir dalı silmek için kullanılır.
##
## git pull
Uzak bir depodaki (genellikle GitHub veya GitLab gibi) değişiklikleri almak ve yerel çalışma alanınızla güncellemek için kullanılan bir Git komutudur. Bu komut, git fetch ve ardından git merge komutlarını tek bir adımda birleştirir.

*`git pull <uzak_depo_adı> <uzak_dal_adı>`* > *`<uzak_depo_adı>`* Değişikliklerin alınacağı uzak depo adı (genellikle origin olarak adlandırılır).
                                              *`uzak_dal_adı`*  Değişikliklerin alınacağı uzak dal adı.

*`git pull [Depo Bağlantı Linki]`* > Bu komut uzak sunucuda yapılan değişiklikleri çalışma dizinine getirir ve birleştirir.
##
## git stash
Mevcut çalışma dizininizdeki değişiklikleri geçici olarak saklamak için kullanılan bir Git komutudur. Bu komut, henüz tamamlanmamış veya commit edilmemiş değişiklikleri bir saklama alanına (stash) geçici olarak kaydeder. Bu, mevcut çalışma dizininizde üzerinde çalıştığınız ancak henüz bitirmediniz veya commit etmek istemediğiniz değişiklikleri geçici olarak kaldırmak için kullanışlıdır.

*`git stash save`* > Bu komut, mevcut çalışma dizinindeki tüm değişiklikleri bir stash'e kaydeder. Değiştirilen tüm dosyaları geçici olarak saklar.

*`git stash pop`* > Bu komut, en son saklanan değişiklikleri alır ve mevcut çalışma dizinine uygular. En son saklanan dosyaları geri yükler.

*`git stash list`* > Bu komut, saklanmış değişikliklerin bir listesini görüntüler. Her bir saklanmış değişiklik bir indeks numarasıyla (stash@{index}) belirtilir. Saklanan tüm değişiklik kümelerini listeler. 

*`git stash drop`* > Saklanmış (stashed) değişikliklerden birini silmek için kullanılan bir Git komutudur. Bu komut, belirli bir saklanmış değişikliği kalıcı olarak kaldırır. En son saklanan değişikliği listeden siler.
#
#
#
## *`.gitignore dosyası`*
Git deposunda takip edilmemesi gereken dosyaları veya dizinleri belirtmek için kullanılan bir dosyadır. Projede yer almasını istemediğiniz dosyaları veya dizinleri bu dosyaya ekleyerek, Git'in bu dosyaları veya dizinleri izlemesini engelleyebilirsiniz.

.gitignore dosyasında her bir satır bir dosya veya dizin adını belirtir. Bu dosyalar veya dizinler, Git tarafından izlenmeyecek ve değişiklik geçmişine eklenmeyeceklerdir. Özellikle proje dosyaları içinde geçici dosyalar, derleme sonucu oluşan dosyalar, yerel yapılandırma dosyaları gibi versiyon kontrolüne tabi tutulmayacak veya izlenmeyecek dosyaların listesi .gitignore dosyasında belirtilir.

### Örnek bir *`.gitignore dosyası`* şu şekilde olabilir:
#### Derleme sonucu oluşan dosyaları ignore et
*.exe
*.o
*.obj

#### IDE'lerin veya editörlerin ayar dosyalarını ignore et
.vscode/
.idea/

#### API anahtarları veya hassas bilgileri ignore et
config.ini
credentials.json

*`.gitignore dosyası`*, projenin düzenini korumak ve gereksiz dosyaların commit geçmişini temizlemek için önemlidir. Bu dosya sayesinde gereksiz dosyaların depoya eklenmesi önlenir ve proje daha düzenli hale gelir.
#
