# Git Cheatsheet - Kapsamlı Git Referans Rehberi

Bu rehber Git'in temel ve ileri seviye komutlarını kapsar. Her komutun Türkçe açıklaması ve ne işe yaradığı belirtilmiştir.

## İçindekiler

1. [Git Kurulumu ve Yapılandırma](#1-git-kurulumu-ve-yapılandırma)
2. [Repository İşlemleri](#2-repository-işlemleri)
3. [Temel Git Komutları](#3-temel-git-komutları)
4. [Branch İşlemleri](#4-branch-işlemleri)
5. [Commit İşlemleri](#5-commit-işlemleri)
6. [Merge ve Rebase](#6-merge-ve-rebase)
7. [Remote Repository İşlemleri](#7-remote-repository-işlemleri)
8. [Stash İşlemleri](#8-stash-işlemleri)
9. [Tag İşlemleri](#9-tag-işlemleri)
10. [Log ve Geçmiş](#10-log-ve-geçmiş)
11. [Reset ve Revert](#11-reset-ve-revert)
12. [Cherry-pick](#12-cherry-pick)
13. [Git Hooks](#13-git-hooks)
14. [Git Submodules](#14-git-submodules)
15. [Git Workflow](#15-git-workflow)
16. [Git Best Practices](#16-git-best-practices)
17. [Git Troubleshooting](#17-git-troubleshooting)
18. [Git Aliases](#18-git-aliases)
19. [Git GUI Araçları](#19-git-gui-araçları)
20. [Git LFS (Large File Storage)](#20-git-lfs-large-file-storage)
21. [Git Security](#21-git-security)
22. [Git Performance](#22-git-performance)
23. [Git Advanced Features](#23-git-advanced-features)
24. [Git Integration](#24-git-integration)
25. [Git Automation](#25-git-automation)

---

## 1. Git Kurulumu ve Yapılandırma

### Git Kurulumu
```bash
# macOS (Homebrew ile)
brew install git

# Ubuntu/Debian
sudo apt-get install git

# Windows
# Git for Windows indir ve kur
```

**Ne İşe Yarar:** Git'i sisteminize kurar
**Ne Yapar:** Git komutlarını kullanabilmenizi sağlar

### Git Versiyonunu Kontrol Etme
```bash
git --version
```

**Ne İşe Yarar:** Kurulu Git versiyonunu gösterir
**Ne Yapar:** Git'in düzgün kurulup kurulmadığını kontrol eder

### Global Kullanıcı Bilgilerini Ayarlama
```bash
git config --global user.name "Adınız Soyadınız"
git config --global user.email "email@example.com"
```

**Ne İşe Yarar:** Git commit'lerinde kullanılacak kullanıcı bilgilerini ayarlar
**Ne Yapar:** Her commit'te kimin yaptığını belirtir

### Git Konfigürasyonunu Görüntüleme
```bash
git config --list
git config --global --list
```

**Ne İşe Yarar:** Mevcut Git ayarlarını gösterir
**Ne Yapar:** Tüm konfigürasyon değerlerini listeler

### Default Branch Adını Ayarlama
```bash
git config --global init.defaultBranch main
```

**Ne İşe Yarar:** Yeni repository'lerde varsayılan branch adını ayarlar
**Ne Yapar:** Artık `main` branch'i varsayılan olarak kullanılır

### Git Editor Ayarlama
```bash
git config --global core.editor "code --wait"
git config --global core.editor "vim"
git config --global core.editor "nano"
```

**Ne İşe Yarar:** Git commit mesajları için kullanılacak editörü ayarlar
**Ne Yapar:** Commit mesajı yazarken hangi editörün açılacağını belirler

---

## 2. Repository İşlemleri

### Yeni Repository Oluşturma
```bash
git init
git init proje_adi
```

**Ne İşe Yarar:** Yeni bir Git repository'si oluşturur
**Ne Yapar:** `.git` klasörü oluşturarak Git tracking'i başlatır

### Mevcut Repository'yi Klonlama
```bash
git clone https://github.com/kullanici/repo.git
git clone https://github.com/kullanici/repo.git proje_adi
git clone -b branch_adi https://github.com/kullanici/repo.git
```

**Ne İşe Yarar:** Uzak repository'yi yerel bilgisayara kopyalar
**Ne Yapar:** Tüm dosyaları ve Git geçmişini indirir

### Repository Durumunu Kontrol Etme
```bash
git status
git status --short
git status -s
```

**Ne İşe Yarar:** Repository'nin mevcut durumunu gösterir
**Ne Yapar:** Hangi dosyaların değiştiğini, eklendiğini veya silindiğini listeler

### Repository'yi Temizleme
```bash
git clean -n  # Önizleme (dry run)
git clean -f  # Zorla temizle
git clean -fd # Klasörleri de sil
```

**Ne İşe Yarar:** Takip edilmeyen dosyaları siler
**Ne Yapar:** Git tarafından izlenmeyen dosyaları kaldırır

### Repository Boyutunu Kontrol Etme
```bash
du -sh .git
git count-objects -vH
```

**Ne İşe Yarar:** Repository'nin disk kullanımını gösterir
**Ne Yapar:** Git veritabanının ne kadar yer kapladığını hesaplar

---

## 3. Temel Git Komutları

### Dosyaları Staging Area'ya Ekleme
```bash
git add dosya.txt
git add .  # Tüm değişiklikleri ekle
git add *.js  # Belirli uzantılı dosyaları ekle
git add -p  # Etkileşimli ekleme
```

**Ne İşe Yarar:** Değişiklikleri commit için hazırlar
**Ne Yapar:** Dosyaları staging area'ya ekler

### Değişiklikleri Commit Etme
```bash
git commit -m "Commit mesajı"
git commit -am "Mesaj"  # Add + commit birleşik
git commit --no-verify  # Hook'ları atla
```

**Ne İşe Yarar:** Değişiklikleri kalıcı olarak kaydeder
**Ne Yapar:** Staging area'daki değişiklikleri Git geçmişine ekler

### Değişiklikleri Görüntüleme
```bash
git diff  # Working directory vs staging
git diff --staged  # Staging vs last commit
git diff HEAD  # Working directory vs last commit
```

**Ne İşe Yarar:** Değişiklikleri detaylı olarak gösterir
**Ne Yapar:** Dosyalardaki ekleme/çıkarma işlemlerini gösterir

### Dosyaları Silme
```bash
git rm dosya.txt  # Dosyayı sil ve Git'ten kaldır
git rm --cached dosya.txt  # Git'ten kaldır ama dosyayı silme
git mv eski.txt yeni.txt  # Dosya adını değiştir
```

**Ne İşe Yarar:** Dosyaları Git tracking'den kaldırır
**Ne Yapar:** Dosyayı siler ve Git geçmişinden de kaldırır

### Değişiklikleri Geri Alma
```bash
git checkout -- dosya.txt  # Dosyayı son commit'e geri döndür
git restore dosya.txt  # Modern Git'te checkout yerine
git restore --staged dosya.txt  # Staging'den kaldır
```

**Ne İşe Yarar:** Değişiklikleri geri alır
**Ne Yapar:** Dosyayı son commit'teki haline döndürür

---

## 4. Branch İşlemleri

### Branch Listesini Görüntüleme
```bash
git branch  # Yerel branch'ler
git branch -r  # Uzak branch'ler
git branch -a  # Tüm branch'ler
git branch -v  # Son commit bilgisi ile
```

**Ne İşe Yarar:** Mevcut branch'leri listeler
**Ne Yapar:** Hangi branch'lerin olduğunu ve hangisinde olduğunuzu gösterir

### Yeni Branch Oluşturma
```bash
git branch yeni_branch  # Branch oluştur ama geçme
git checkout -b yeni_branch  # Oluştur ve geç
git switch -c yeni_branch  # Modern Git'te
```

**Ne İşe Yarar:** Yeni bir branch oluşturur
**Ne Yapar:** Mevcut commit'ten yeni bir dal oluşturur

### Branch Değiştirme
```bash
git checkout branch_adi
git switch branch_adi  # Modern Git'te
```

**Ne İşe Yarar:** Farklı bir branch'e geçer
**Ne Yapar:** Working directory'yi o branch'teki dosyalarla günceller

### Branch Silme
```bash
git branch -d branch_adi  # Güvenli silme
git branch -D branch_adi  # Zorla silme
git branch -dr origin/branch_adi  # Uzak branch referansını sil
```

**Ne İşe Yarar:** Artık kullanılmayan branch'leri siler
**Ne Yapar:** Branch'i ve referansını kaldırır

### Branch Yeniden Adlandırma
```bash
git branch -m eski_adi yeni_adi
git branch -m yeni_adi  # Mevcut branch'i yeniden adlandır
```

**Ne İşe Yarar:** Branch adını değiştirir
**Ne Yapar:** Branch'in adını günceller

### Branch Geçmişini Görüntüleme
```bash
git log --oneline --graph --all
git log --oneline --graph --decorate
```

**Ne İşe Yarar:** Branch geçmişini görsel olarak gösterir
**Ne Yapar:** Branch'lerin nasıl ayrıldığını ve birleştiğini gösterir

---

## 5. Commit İşlemleri

### Commit Geçmişini Görüntüleme
```bash
git log  # Tüm geçmiş
git log --oneline  # Kısa format
git log -n 5  # Son 5 commit
git log --since="2023-01-01"  # Tarih filtresi
git log --author="kullanici"  # Yazar filtresi
```

**Ne İşe Yarar:** Commit geçmişini gösterir
**Ne Yapar:** Projenin değişim geçmişini listeler

### Commit Detaylarını Görüntüleme
```bash
git show commit_hash
git show HEAD  # Son commit
git show --stat commit_hash  # İstatistiklerle
```

**Ne İşe Yarar:** Belirli bir commit'in detaylarını gösterir
**Ne Yapar:** Commit'teki değişiklikleri ve mesajı gösterir

### Commit Mesajını Düzenleme
```bash
git commit --amend  # Son commit'i düzenle
git commit --amend -m "Yeni mesaj"
```

**Ne İşe Yarar:** Son commit'i değiştirir
**Ne Yapar:** Commit mesajını veya içeriğini günceller

### Commit'i Geri Alma
```bash
git revert commit_hash  # Yeni commit ile geri al
git revert HEAD  # Son commit'i geri al
git revert --no-commit commit_hash  # Commit oluşturma
```

**Ne İşe Yarar:** Commit'i güvenli şekilde geri alır
**Ne Yapar:** Yeni bir commit oluşturarak değişiklikleri geri alır

### Commit'i Sıfırlama
```bash
git reset --soft commit_hash  # Staging'de bırak
git reset --mixed commit_hash  # Working directory'de bırak
git reset --hard commit_hash  # Tamamen sil
```

**Ne İşe Yarar:** Repository'yi belirli bir commit'e döndürür
**Ne Yapar:** Commit geçmişini değiştirir (dikkatli kullanın)

### Commit Arama
```bash
git log --grep="arama_terimi"
git log -S "kod_parcasi"  # Kod içinde arama
git log -G "regex_pattern"  # Regex ile arama
```

**Ne İşe Yarar:** Commit'lerde arama yapar
**Ne Yapar:** Belirli kriterlere uyan commit'leri bulur

---

## 6. Merge ve Rebase

### Branch'leri Birleştirme (Merge)
```bash
git merge branch_adi  # Fast-forward merge
git merge --no-ff branch_adi  # No fast-forward
git merge --squash branch_adi  # Tek commit olarak birleştir
```

**Ne İşe Yarar:** İki branch'i birleştirir
**Ne Yapar:** Bir branch'teki değişiklikleri diğerine ekler

### Merge Conflict Çözümü
```bash
git status  # Conflict'leri gör
git diff  # Conflict detaylarını gör
# Manuel olarak dosyaları düzenle
git add dosya.txt  # Çözülen dosyayı ekle
git commit  # Merge'i tamamla
```

**Ne İşe Yarar:** Merge conflict'lerini çözer
**Ne Yapar:** Çakışan değişiklikleri manuel olarak birleştirir

### Rebase İşlemi
```bash
git rebase branch_adi  # Branch'i rebase et
git rebase -i HEAD~3  # Etkileşimli rebase
git rebase --abort  # Rebase'i iptal et
git rebase --continue  # Rebase'e devam et
```

**Ne İşe Yarar:** Commit geçmişini düzenler
**Ne Yapar:** Commit'leri başka bir branch'in üzerine yeniden uygular

### Etkileşimli Rebase
```bash
git rebase -i HEAD~5
# pick, reword, edit, squash, fixup, drop
```

**Ne İşe Yarar:** Commit geçmişini düzenler
**Ne Yapar:** Commit'leri yeniden düzenleme, birleştirme veya silme imkanı verir

### Merge Stratejileri
```bash
git merge -X ours  # Bizim değişikliklerimizi tercih et
git merge -X theirs  # Onların değişikliklerini tercih et
git merge -X ignore-space-change  # Boşluk değişikliklerini yok say
```

**Ne İşe Yarar:** Merge stratejisini belirler
**Ne Yapar:** Conflict çözümünde hangi değişikliklerin tercih edileceğini belirler

### Rebase vs Merge
```bash
# Rebase: Temiz geçmiş, doğrusal
git rebase main

# Merge: Tam geçmiş, branch bilgisi korunur
git merge main
```

**Ne İşe Yarar:** İki farklı birleştirme stratejisi
**Ne Yapar:** Rebase temiz geçmiş, merge tam geçmiş sağlar 

---

## 7. Remote Repository İşlemleri

### Remote Repository Ekleme
```bash
git remote add origin https://github.com/kullanici/repo.git
git remote add upstream https://github.com/original/repo.git
```

**Ne İşe Yarar:** Uzak repository bağlantısı ekler
**Ne Yapar:** Yerel repository'yi uzak repository ile bağlar

### Remote Repository Listesi
```bash
git remote  # Remote'ları listele
git remote -v  # URL'lerle birlikte
git remote show origin  # Detaylı bilgi
```

**Ne İşe Yarar:** Bağlı remote repository'leri gösterir
**Ne Yapar:** Hangi uzak repository'lere bağlı olduğunuzu listeler

### Remote'dan Veri Çekme
```bash
git fetch origin  # Veri çek ama birleştirme
git fetch --all  # Tüm remote'lardan çek
git fetch origin branch_adi  # Belirli branch'i çek
```

**Ne İşe Yarar:** Uzak repository'den güncellemeleri alır
**Ne Yapar:** Değişiklikleri yerel repository'ye indirir ama birleştirmez

### Pull İşlemi
```bash
git pull origin main  # Fetch + merge
git pull --rebase origin main  # Fetch + rebase
git pull --ff-only origin main  # Sadece fast-forward
```

**Ne İşe Yarar:** Uzak değişiklikleri yerel repository'ye alır
**Ne Yapar:** Fetch ve merge işlemlerini birleştirir

### Push İşlemi
```bash
git push origin main  # Branch'i push et
git push -u origin main  # Upstream ayarla
git push --force  # Zorla push (dikkatli kullan)
git push --force-with-lease  # Güvenli force push
```

**Ne İşe Yarar:** Yerel değişiklikleri uzak repository'ye gönderir
**Ne Yapar:** Commit'leri uzak repository'ye yükler

### Remote Repository Güncelleme
```bash
git remote set-url origin yeni_url
git remote rename origin upstream
git remote remove upstream
```

**Ne İşe Yarar:** Remote repository ayarlarını değiştirir
**Ne Yapar:** URL'leri, isimleri günceller veya remote'ları kaldırır 

---

## 8. Stash İşlemleri

### Değişiklikleri Stash Etme
```bash
git stash  # Değişiklikleri geçici olarak sakla
git stash push -m "Stash mesajı"  # Mesaj ile stash
git stash -u  # Untracked dosyaları da dahil et
```

**Ne İşe Yarar:** Çalışma alanını temizler
**Ne Yapar:** Değişiklikleri geçici olarak saklar

### Stash Listesini Görüntüleme
```bash
git stash list  # Tüm stash'leri listele
git stash show  # Son stash'in detaylarını göster
git stash show -p  # Diff ile göster
```

**Ne İşe Yarar:** Mevcut stash'leri gösterir
**Ne Yapar:** Hangi stash'lerin olduğunu ve içeriklerini listeler

### Stash'i Uygulama
```bash
git stash pop  # Son stash'i uygula ve sil
git stash apply  # Son stash'i uygula ama silme
git stash apply stash@{1}  # Belirli stash'i uygula
```

**Ne İşe Yarar:** Stash'teki değişiklikleri geri getirir
**Ne Yapar:** Saklanan değişiklikleri working directory'ye uygular

### Stash'i Silme
```bash
git stash drop  # Son stash'i sil
git stash drop stash@{1}  # Belirli stash'i sil
git stash clear  # Tüm stash'leri sil
```

**Ne İşe Yarar:** Artık gerekli olmayan stash'leri temizler
**Ne Yapar:** Stash'leri kalıcı olarak kaldırır

### Stash'ten Branch Oluşturma
```bash
git stash branch yeni_branch  # Stash'ten branch oluştur
```

**Ne İşe Yarar:** Stash'teki değişikliklerden yeni branch oluşturur
**Ne Yapar:** Stash'i uygular ve yeni branch'e geçer

### Stash Diff Görüntüleme
```bash
git stash show -p stash@{0}  # Belirli stash'in diff'i
git stash show -p  # Son stash'in diff'i
```

**Ne İşe Yarar:** Stash'teki değişiklikleri detaylı gösterir
**Ne Yapar:** Hangi dosyaların nasıl değiştiğini gösterir 

---

## 9. Tag İşlemleri

### Tag Oluşturma
```bash
git tag v1.0.0  # Lightweight tag
git tag -a v1.0.0 -m "Version 1.0.0"  # Annotated tag
git tag -a v1.0.0 commit_hash -m "Mesaj"  # Belirli commit'e tag
```

**Ne İşe Yarar:** Belirli commit'leri işaretler
**Ne Yapar:** Versiyonları veya önemli noktaları etiketler

### Tag Listesini Görüntüleme
```bash
git tag  # Tüm tag'leri listele
git tag -l "v1.*"  # Pattern ile filtrele
git tag -n  # Tag mesajları ile birlikte
```

**Ne İşe Yarar:** Mevcut tag'leri gösterir
**Ne Yapar:** Hangi tag'lerin olduğunu ve mesajlarını listeler

### Tag Detaylarını Görüntüleme
```bash
git show v1.0.0  # Tag detaylarını göster
git tag -v v1.0.0  # GPG imzasını doğrula
```

**Ne İşe Yarar:** Tag'in detaylarını gösterir
**Ne Yapar:** Tag'in hangi commit'e işaret ettiğini ve mesajını gösterir

### Tag'i Silme
```bash
git tag -d v1.0.0  # Yerel tag'i sil
git push origin --delete v1.0.0  # Uzak tag'i sil
```

**Ne İşe Yarar:** Artık gerekli olmayan tag'leri kaldırır
**Ne Yapar:** Tag'i hem yerel hem uzak repository'den siler

### Tag'i Push Etme
```bash
git push origin v1.0.0  # Belirli tag'i push et
git push origin --tags  # Tüm tag'leri push et
```

**Ne İşe Yarar:** Tag'leri uzak repository'ye gönderir
**Ne Yapar:** Tag'leri diğer geliştiricilerle paylaşır

### Tag'e Checkout
```bash
git checkout v1.0.0  # Tag'e geç
git checkout -b branch_adi v1.0.0  # Tag'den branch oluştur
```

**Ne İşe Yarar:** Belirli bir tag'e geçer
**Ne Yapar:** O tag'deki kod durumuna döner 

---

## 10. Log ve Geçmiş

### Temel Log Komutları
```bash
git log  # Tüm geçmiş
git log --oneline  # Kısa format
git log --graph  # Grafik görünümü
git log --decorate  # Branch ve tag bilgileri
```

**Ne İşe Yarar:** Commit geçmişini gösterir
**Ne Yapar:** Projenin değişim geçmişini listeler

### Log Filtreleme
```bash
git log --author="kullanici"  # Yazar filtresi
git log --since="2023-01-01"  # Tarih filtresi
git log --until="2023-12-31"  # Bitiş tarihi
git log -n 10  # Son 10 commit
```

**Ne İşe Yarar:** Belirli kriterlere göre commit'leri filtreler
**Ne Yapar:** İstediğiniz commit'leri bulmanızı sağlar

### Log Formatları
```bash
git log --pretty=format:"%h - %an, %ar : %s"
git log --pretty=format:"%C(yellow)%h%Creset - %C(blue)%an%Creset, %C(green)%ar%Creset : %s"
git log --stat  # İstatistiklerle
git log --patch  # Diff ile
```

**Ne İşe Yarar:** Log çıktısını özelleştirir
**Ne Yapar:** Commit bilgilerini istediğiniz formatta gösterir

### Belirli Dosya Geçmişi
```bash
git log dosya.txt  # Dosya geçmişi
git log --follow dosya.txt  # Dosya yeniden adlandırma geçmişi
git log -p dosya.txt  # Diff ile dosya geçmişi
```

**Ne İşe Yarar:** Belirli dosyanın değişim geçmişini gösterir
**Ne Yapar:** Dosyanın hangi commit'lerde değiştiğini listeler

### Commit Arama
```bash
git log --grep="arama_terimi"  # Commit mesajında arama
git log -S "kod_parcasi"  # Kod içinde arama
git log -G "regex_pattern"  # Regex ile arama
```

**Ne İşe Yarar:** Commit'lerde arama yapar
**Ne Yapar:** Belirli kriterlere uyan commit'leri bulur

### Geçmiş Karşılaştırma
```bash
git log branch1..branch2  # İki branch arasındaki fark
git log --left-right branch1...branch2  # Ortak olmayan commit'ler
```

**Ne İşe Yarar:** Branch'ler arasındaki farkları gösterir
**Ne Yapar:** Hangi commit'lerin hangi branch'te olduğunu gösterir 

---

## 11. Reset ve Revert

### Git Reset Türleri
```bash
git reset --soft commit_hash  # Staging'de bırak
git reset --mixed commit_hash  # Working directory'de bırak (varsayılan)
git reset --hard commit_hash  # Tamamen sil
```

**Ne İşe Yarar:** Repository'yi belirli bir commit'e döndürür
**Ne Yapar:** Commit geçmişini değiştirir (dikkatli kullanın)

### Reset Örnekleri
```bash
git reset HEAD~1  # Son commit'i geri al
git reset --soft HEAD~1  # Son commit'i staging'e geri al
git reset --hard HEAD~1  # Son commit'i tamamen sil
```

**Ne İşe Yarar:** Son commit'leri geri alır
**Ne Yapar:** Commit geçmişini düzenler

### Git Revert
```bash
git revert commit_hash  # Yeni commit ile geri al
git revert HEAD  # Son commit'i geri al
git revert --no-commit commit_hash  # Commit oluşturma
```

**Ne İşe Yarar:** Commit'i güvenli şekilde geri alır
**Ne Yapar:** Yeni bir commit oluşturarak değişiklikleri geri alır

### Revert vs Reset
```bash
# Revert: Güvenli, geçmişi korur
git revert HEAD

# Reset: Tehlikeli, geçmişi değiştirir
git reset --hard HEAD~1
```

**Ne İşe Yarar:** İki farklı geri alma stratejisi
**Ne Yapar:** Revert güvenli, reset tehlikeli

### Belirli Dosyayı Reset Etme
```bash
git reset HEAD dosya.txt  # Staging'den kaldır
git checkout -- dosya.txt  # Working directory'den kaldır
git restore dosya.txt  # Modern Git'te
```

**Ne İşe Yarar:** Belirli dosyayı geri alır
**Ne Yapar:** Dosyayı son commit'teki haline döndürür

### Reset Sonrası Kurtarma
```bash
git reflog  # Git geçmişini göster
git reset --hard HEAD@{1}  # Önceki duruma dön
```

**Ne İşe Yarar:** Reset sonrası veri kaybını önler
**Ne Yapar:** Git'in tüm işlem geçmişini gösterir 

---

## 12. Cherry-pick

### Tek Commit'i Uygulama
```bash
git cherry-pick commit_hash  # Tek commit'i uygula
git cherry-pick -x commit_hash  # Kaynak bilgisi ekle
git cherry-pick --no-commit commit_hash  # Commit oluşturma
```

**Ne İşe Yarar:** Belirli commit'i mevcut branch'e uygular
**Ne Yapar:** Başka bir branch'teki commit'i bu branch'e kopyalar

### Birden Fazla Commit'i Uygulama
```bash
git cherry-pick commit1 commit2 commit3  # Sırayla uygula
git cherry-pick commit1..commit3  # Aralık uygula (commit1 hariç)
git cherry-pick commit1^..commit3  # Aralık uygula (commit1 dahil)
```

**Ne İşe Yarar:** Birden fazla commit'i seçerek uygular
**Ne Yapar:** İstediğiniz commit'leri sırayla kopyalar

### Cherry-pick Conflict Çözümü
```bash
git cherry-pick commit_hash  # Conflict oluşursa
# Manuel olarak conflict'leri çöz
git add dosya.txt  # Çözülen dosyayı ekle
git cherry-pick --continue  # Devam et
git cherry-pick --abort  # İptal et
```

**Ne İşe Yarar:** Cherry-pick sırasında oluşan conflict'leri çözer
**Ne Yapar:** Çakışan değişiklikleri manuel olarak birleştirir

### Cherry-pick Stratejileri
```bash
git cherry-pick -X theirs commit_hash  # Onların değişikliklerini tercih et
git cherry-pick -X ours commit_hash  # Bizim değişikliklerimizi tercih et
git cherry-pick -X ignore-space-change commit_hash  # Boşluk değişikliklerini yok say
```

**Ne İşe Yarar:** Cherry-pick stratejisini belirler
**Ne Yapar:** Conflict çözümünde hangi değişikliklerin tercih edileceğini belirler

### Cherry-pick Geçmişini Görüntüleme
```bash
git log --oneline --graph --all  # Cherry-pick'leri gör
git show commit_hash  # Cherry-pick edilen commit'i incele
```

**Ne İşe Yarar:** Cherry-pick işlemlerini takip eder
**Ne Yapar:** Hangi commit'lerin cherry-pick edildiğini gösterir 

---

## 13. Git Hooks

### Hook Türleri
```bash
# Pre-commit hooks
.git/hooks/pre-commit  # Commit öncesi çalışır
.git/hooks/prepare-commit-msg  # Commit mesajı hazırlanırken
.git/hooks/commit-msg  # Commit mesajı yazılırken

# Post-commit hooks
.git/hooks/post-commit  # Commit sonrası çalışır
.git/hooks/post-merge  # Merge sonrası çalışır
.git/hooks/post-checkout  # Checkout sonrası çalışır
```

**Ne İşe Yarar:** Git işlemlerini otomatikleştirir
**Ne Yapar:** Belirli Git işlemleri öncesi/sonrası script'ler çalıştırır

### Pre-commit Hook Örneği
```bash
#!/bin/sh
# .git/hooks/pre-commit
echo "Pre-commit hook çalışıyor..."
npm test  # Test'leri çalıştır
if [ $? -ne 0 ]; then
    echo "Test'ler başarısız! Commit iptal edildi."
    exit 1
fi
```

**Ne İşe Yarar:** Commit öncesi kontroller yapar
**Ne Yapar:** Test'leri çalıştırır, başarısızsa commit'i engeller

### Commit-msg Hook Örneği
```bash
#!/bin/sh
# .git/hooks/commit-msg
commit_msg=$(cat $1)
if ! echo "$commit_msg" | grep -qE "^(feat|fix|docs|style|refactor|test|chore):"; then
    echo "Commit mesajı formatı yanlış!"
    echo "Format: type: description"
    exit 1
fi
```

**Ne İşe Yarar:** Commit mesajı formatını kontrol eder
**Ne Yapar:** Conventional commits formatını zorlar

### Hook'ları Etkinleştirme
```bash
chmod +x .git/hooks/pre-commit
chmod +x .git/hooks/commit-msg
```

**Ne İşe Yarar:** Hook script'lerini çalıştırılabilir yapar
**Ne Yapar:** Git'in hook'ları çalıştırmasını sağlar

### Hook'ları Atlama
```bash
git commit --no-verify  # Tüm hook'ları atla
git commit -m "Mesaj" --no-verify
```

**Ne İşe Yarar:** Hook'ları geçici olarak devre dışı bırakır
**Ne Yapar:** Acil durumlarda hook kontrollerini atlar

### Husky ile Hook Yönetimi
```bash
npm install --save-dev husky
npx husky install
npx husky add .husky/pre-commit "npm test"
```

**Ne İşe Yarar:** Node.js projelerinde hook'ları yönetir
**Ne Yapar:** Hook'ları package.json üzerinden yönetmeyi sağlar 

---

## 14. Git Submodules

### Submodule Ekleme
```bash
git submodule add https://github.com/kullanici/repo.git path/to/submodule
git submodule add --branch branch_adi https://github.com/kullanici/repo.git path/to/submodule
```

**Ne İşe Yarar:** Başka bir repository'yi alt modül olarak ekler
**Ne Yapar:** Ana proje içinde başka bir projeyi referans olarak tutar

### Submodule'leri Klonlama
```bash
git clone --recursive https://github.com/kullanici/repo.git
git clone https://github.com/kullanici/repo.git
cd repo
git submodule init
git submodule update
```

**Ne İşe Yarar:** Submodule'leri olan projeyi klonlar
**Ne Yapar:** Ana proje ile birlikte submodule'leri de indirir

### Submodule Durumunu Kontrol Etme
```bash
git submodule status  # Submodule durumları
git submodule foreach 'git status'  # Her submodule'de komut çalıştır
```

**Ne İşe Yarar:** Submodule'lerin durumunu gösterir
**Ne Yapar:** Hangi submodule'lerin güncel olduğunu listeler

### Submodule Güncelleme
```bash
git submodule update --remote  # Tüm submodule'leri güncelle
git submodule update --remote submodule_adi  # Belirli submodule'ü güncelle
```

**Ne İşe Yarar:** Submodule'leri en son versiyona günceller
**Ne Yapar:** Submodule'lerdeki değişiklikleri ana projeye alır

### Submodule'de Değişiklik Yapma
```bash
cd path/to/submodule
git checkout -b feature_branch
# Değişiklikler yap
git add .
git commit -m "Değişiklik"
git push origin feature_branch
cd ../..
git add path/to/submodule
git commit -m "Submodule güncellendi"
```

**Ne İşe Yarar:** Submodule'de değişiklik yapar
**Ne Yapar:** Submodule'deki değişiklikleri commit eder ve ana projeye yansıtır

### Submodule Silme
```bash
git submodule deinit path/to/submodule
git rm path/to/submodule
git commit -m "Submodule kaldırıldı"
rm -rf .git/modules/path/to/submodule
```

**Ne İşe Yarar:** Submodule'ü projeden kaldırır
**Ne Yapar:** Submodule referansını ve dosyalarını temizler 

---

## 15. Git Workflow

### Git Flow Workflow
```bash
# Ana branch'ler
main/master  # Production kodu
develop  # Development kodu
feature/*  # Yeni özellikler
release/*  # Release hazırlığı
hotfix/*  # Acil düzeltmeler

# Feature branch oluşturma
git checkout -b feature/yeni-ozellik develop

# Release branch oluşturma
git checkout -b release/v1.0.0 develop

# Hotfix branch oluşturma
git checkout -b hotfix/acil-duzeltme main
```

**Ne İşe Yarar:** Büyük projeler için yapılandırılmış workflow
**Ne Yapar:** Branch stratejisini ve release sürecini standartlaştırır

### GitHub Flow
```bash
# Basit workflow
main  # Production kodu
feature/*  # Yeni özellikler

# Feature branch oluşturma
git checkout -b feature/yeni-ozellik

# Pull Request oluşturma
git push origin feature/yeni-ozellik
# GitHub'da PR aç

# Merge sonrası
git checkout main
git pull origin main
git branch -d feature/yeni-ozellik
```

**Ne İşe Yarar:** Basit ve hızlı workflow
**Ne Yapar:** Sürekli deployment için optimize edilmiş süreç

### GitLab Flow
```bash
# Branch stratejisi
main  # Production kodu
pre-production  # Test ortamı
staging  # Staging ortamı
feature/*  # Yeni özellikler

# Environment-based deployment
git checkout -b feature/yeni-ozellik
# Geliştirme
git checkout staging
git merge feature/yeni-ozellik
# Staging test
git checkout pre-production
git merge staging
# Pre-production test
git checkout main
git merge pre-production
```

**Ne İşe Yarar:** Environment-based deployment
**Ne Yapar:** Farklı ortamlar için ayrı branch'ler kullanır

### Trunk-Based Development
```bash
# Tek main branch
main  # Tüm geliştirme burada

# Kısa süreli feature branch'ler
git checkout -b feature/kisa-ozellik
# Hızlı geliştirme
git checkout main
git merge feature/kisa-ozellik
git branch -d feature/kisa-ozellik
```

**Ne İşe Yarar:** Sürekli integration için optimize
**Ne Yapar:** Kısa süreli branch'ler ve sık merge

### Conventional Commits
```bash
# Commit mesaj formatı
feat: yeni özellik eklendi
fix: hata düzeltildi
docs: dokümantasyon güncellendi
style: kod formatı düzeltildi
refactor: kod yeniden düzenlendi
test: test eklendi
chore: bakım işlemleri
```

**Ne İşe Yarar:** Standart commit mesaj formatı
**Ne Yapar:** Otomatik changelog ve versioning sağlar 

---

## 16. Git Best Practices

### Commit Mesajları
```bash
# İyi commit mesajları
feat: kullanıcı girişi eklendi
fix: login sayfasındaki hata düzeltildi
docs: README dosyası güncellendi
style: kod formatı düzeltildi

# Kötü commit mesajları
düzeltme
bug fix
update
```

**Ne İşe Yarar:** Anlaşılır commit geçmişi oluşturur
**Ne Yapar:** Proje geçmişini takip etmeyi kolaylaştırır

### Branch İsimlendirme
```bash
# İyi branch isimleri
feature/user-authentication
bugfix/login-error
hotfix/security-patch
release/v2.1.0

# Kötü branch isimleri
new-feature
fix
test
```

**Ne İşe Yarar:** Branch'lerin amacını net şekilde belirtir
**Ne Yapar:** Takım içi iletişimi kolaylaştırır

### Dosya Yönetimi
```bash
# .gitignore dosyası
node_modules/
*.log
.env
.DS_Store
build/
dist/

# Büyük dosyalar için Git LFS
*.psd
*.zip
*.mp4
```

**Ne İşe Yarar:** Gereksiz dosyaları repository'den uzak tutar
**Ne Yapar:** Repository boyutunu küçük tutar

### Güvenlik
```bash
# Hassas bilgileri commit etme
# .env dosyası
API_KEY=secret_key
DATABASE_PASSWORD=password

# Bunun yerine .env.example kullan
API_KEY=your_api_key_here
DATABASE_PASSWORD=your_password_here
```

**Ne İşe Yarar:** Hassas bilgileri korur
**Ne Yapar:** Güvenlik açıklarını önler

### Code Review
```bash
# Pull Request süreci
1. Feature branch oluştur
2. Değişiklikleri yap
3. Test'leri çalıştır
4. Pull Request aç
5. Code review bekle
6. Merge et
```

**Ne İşe Yarar:** Kod kalitesini artırır
**Ne Yapar:** Hataları erken yakalar

### Backup ve Recovery
```bash
# Düzenli backup
git push origin main  # Uzak repository'ye push
git push --all origin  # Tüm branch'leri push

# Recovery
git reflog  # Geçmişi gör
git reset --hard HEAD@{1}  # Önceki duruma dön
```

**Ne İşe Yarar:** Veri kaybını önler
**Ne Yapar:** Güvenli geliştirme ortamı sağlar 

---

## 17. Git Troubleshooting

### Yaygın Hatalar ve Çözümleri

#### "Permission Denied" Hatası
```bash
# SSH key sorunu
ssh -T git@github.com  # SSH bağlantısını test et
ssh-keygen -t rsa -b 4096 -C "email@example.com"  # Yeni SSH key oluştur

# Dosya izinleri
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```

**Ne İşe Yarar:** SSH bağlantı sorunlarını çözer
**Ne Yapar:** GitHub ile güvenli bağlantı sağlar

#### "Merge Conflict" Hatası
```bash
# Conflict'leri gör
git status
git diff

# Conflict'leri çöz
# Manuel olarak dosyaları düzenle
git add dosya.txt
git commit -m "Conflict çözüldü"
```

**Ne İşe Yarar:** Merge conflict'lerini çözer
**Ne Yapar:** Çakışan değişiklikleri birleştirir

#### "Detached HEAD" Durumu
```bash
# Detached HEAD'den çık
git checkout main  # Ana branch'e dön
git checkout -b yeni_branch  # Yeni branch oluştur

# Değişiklikleri kaydet
git stash
git checkout main
git stash pop
```

**Ne İşe Yarar:** Detached HEAD durumundan çıkar
**Ne Yapar:** Güvenli branch'e geçer

#### "Large File" Hatası
```bash
# Büyük dosyayı kaldır
git rm --cached buyuk_dosya.zip
git commit -m "Büyük dosya kaldırıldı"

# Git LFS kullan
git lfs track "*.zip"
git add .gitattributes
git add buyuk_dosya.zip
```

**Ne İşe Yarar:** Büyük dosya sorunlarını çözer
**Ne Yapar:** Repository boyutunu kontrol altında tutar

#### "Authentication Failed" Hatası
```bash
# Credential'ları temizle
git config --global --unset user.name
git config --global --unset user.email

# Yeni credential'ları ayarla
git config --global user.name "Adınız"
git config --global user.email "email@example.com"

# Personal Access Token kullan (GitHub)
git remote set-url origin https://token@github.com/kullanici/repo.git
```

**Ne İşe Yarar:** Kimlik doğrulama sorunlarını çözer
**Ne Yapar:** Güvenli erişim sağlar

#### "Repository Not Found" Hatası
```bash
# Remote URL'yi kontrol et
git remote -v

# URL'yi düzelt
git remote set-url origin https://github.com/dogru_kullanici/repo.git

# Repository erişimini kontrol et
git ls-remote origin
```

**Ne İşe Yarar:** Repository erişim sorunlarını çözer
**Ne Yapar:** Doğru repository'ye bağlanır 

---

## 18. Git Aliases

### Temel Alias'lar
```bash
# Kısa komutlar
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'

# Kullanım
git st  # git status
git co main  # git checkout main
git br  # git branch
git ci -m "mesaj"  # git commit -m "mesaj"
```

**Ne İşe Yarar:** Git komutlarını kısaltır
**Ne Yapar:** Daha hızlı Git kullanımı sağlar

### Gelişmiş Alias'lar
```bash
# Log alias'ları
git config --global alias.lg "log --oneline --graph --decorate"
git config --global alias.lga "log --oneline --graph --decorate --all"
git config --global alias.lg1 "log --oneline --graph --decorate -1"

# Diff alias'ları
git config --global alias.df "diff"
git config --global alias.dfs "diff --staged"
git config --global alias.dfh "diff HEAD"

# Branch alias'ları
git config --global alias.new "checkout -b"
git config --global alias.delete "branch -d"
git config --global alias.force-delete "branch -D"
```

**Ne İşe Yarar:** Karmaşık komutları basitleştirir
**Ne Yapar:** Sık kullanılan komutları kısaltır

### Özel Alias'lar
```bash
# Commit alias'ları
git config --global alias.amend "commit --amend"
git config --global alias.undo "reset HEAD~1"
git config --global alias.undo-soft "reset --soft HEAD~1"

# Stash alias'ları
git config --global alias.stash-list "stash list"
git config --global alias.stash-pop "stash pop"
git config --global alias.stash-drop "stash drop"

# Remote alias'ları
git config --global alias.remote-list "remote -v"
git config --global alias.remote-show "remote show"
```

**Ne İşe Yarar:** Özel işlemler için alias'lar oluşturur
**Ne Yapar:** Kişiselleştirilmiş Git deneyimi sağlar

### Alias'ları Görüntüleme
```bash
# Tüm alias'ları listele
git config --global --get-regexp alias

# Belirli alias'ı görüntüle
git config --global alias.stash-list

# Alias'ı sil
git config --global --unset alias.stash-list
```

**Ne İşe Yarar:** Mevcut alias'ları yönetir
**Ne Yapar:** Alias'ları görüntüleme ve silme imkanı verir

### Alias Dosyası
```bash
# ~/.gitconfig dosyası
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    lg = log --oneline --graph --decorate
    df = diff
    dfs = diff --staged
    new = checkout -b
    delete = branch -d
    amend = commit --amend
    undo = reset HEAD~1
```

**Ne İşe Yarar:** Alias'ları kalıcı olarak saklar
**Ne Yapar:** Tüm Git projelerinde kullanılabilir 

---

## 19. Git GUI Araçları

### Popüler Git GUI'leri

#### GitKraken
```bash
# Özellikler
- Görsel branch yönetimi
- Merge conflict çözümü
- Git Flow desteği
- GitHub/GitLab entegrasyonu
- Cross-platform

# Kurulum
# https://www.gitkraken.com/ adresinden indir
```

**Ne İşe Yarar:** Görsel Git arayüzü sağlar
**Ne Yapar:** Git işlemlerini mouse ile yapmayı kolaylaştırır

#### SourceTree
```bash
# Özellikler
- Atlassian tarafından geliştirilmiş
- Ücretsiz
- Git Flow desteği
- Mercurial desteği
- Windows/Mac

# Kurulum
# https://www.sourcetreeapp.com/ adresinden indir
```

**Ne İşe Yarar:** Profesyonel Git yönetimi
**Ne Yapar:** Karmaşık Git işlemlerini basitleştirir

#### GitHub Desktop
```bash
# Özellikler
- GitHub tarafından geliştirilmiş
- Basit ve kullanıcı dostu
- GitHub entegrasyonu
- Windows/Mac

# Kurulum
# https://desktop.github.com/ adresinden indir
```

**Ne İşe Yarar:** GitHub odaklı Git yönetimi
**Ne Yapar:** GitHub işlemlerini kolaylaştırır

#### Git GUI (Git'in kendi GUI'si)
```bash
# Git GUI'yi başlat
git gui

# Özellikler
- Git ile birlikte gelir
- Basit arayüz
- Cross-platform
- Ücretsiz
```

**Ne İşe Yarar:** Git'in yerleşik GUI'sini kullanır
**Ne Yapar:** Temel Git işlemlerini görsel olarak yapar

#### Visual Studio Code Git Entegrasyonu
```bash
# VS Code'da Git
- Source Control paneli
- Diff görüntüleme
- Commit işlemleri
- Branch yönetimi
- Git Lens eklentisi

# Git Lens eklentisi
# VS Code marketplace'den yükle
```

**Ne İşe Yarar:** Kod editöründe Git entegrasyonu
**Ne Yapar:** Kod yazarken Git işlemlerini yapmayı sağlar

#### JetBrains IDE'leri
```bash
# IntelliJ IDEA, WebStorm, PyCharm vb.
- Gelişmiş Git entegrasyonu
- Merge conflict çözümü
- Git log görüntüleme
- Branch yönetimi
- Git blame

# Özellikler
- IDE içinde tam Git desteği
- Görsel diff araçları
- Git history
```

**Ne İşe Yarar:** IDE içinde Git yönetimi
**Ne Yapar:** Geliştirme ortamında Git işlemlerini yapar 

---

## 20. Git LFS (Large File Storage)

### Git LFS Kurulumu
```bash
# Git LFS'i kur
git lfs install

# Global olarak kur
git lfs install --system
```

**Ne İşe Yarar:** Git LFS'i sisteminize kurar
**Ne Yapar:** Büyük dosyaları Git ile yönetmeyi sağlar

### Dosya Türlerini Takip Etme
```bash
# Belirli dosya türlerini takip et
git lfs track "*.psd"
git lfs track "*.zip"
git lfs track "*.mp4"
git lfs track "*.pdf"

# .gitattributes dosyasını commit et
git add .gitattributes
git commit -m "LFS tracking eklendi"
```

**Ne İşe Yarar:** Büyük dosya türlerini LFS ile yönetir
**Ne Yapar:** Bu dosyaları Git repository'sinde pointer olarak saklar

### Mevcut Dosyaları LFS'e Taşıma
```bash
# Mevcut dosyaları LFS'e taşı
git lfs migrate import --include="*.psd,*.zip"

# Tüm geçmişi taşı
git lfs migrate import --include="*.psd,*.zip" --everything
```

**Ne İşe Yarar:** Mevcut büyük dosyaları LFS'e taşır
**Ne Yapar:** Repository geçmişini LFS'e uygun hale getirir

### LFS Durumunu Kontrol Etme
```bash
# LFS dosyalarını listele
git lfs ls-files

# LFS durumunu kontrol et
git lfs status

# LFS dosyalarını pull et
git lfs pull
```

**Ne İşe Yarar:** LFS dosyalarının durumunu gösterir
**Ne Yapar:** Hangi dosyaların LFS ile yönetildiğini listeler

### LFS Konfigürasyonu
```bash
# LFS endpoint'ini ayarla
git lfs endpoint add "https://git-lfs.github.com/"

# LFS konfigürasyonunu görüntüle
git lfs env

# LFS cache'ini temizle
git lfs prune
```

**Ne İşe Yarar:** LFS ayarlarını yönetir
**Ne Yapar:** LFS'in nasıl çalışacağını belirler

### LFS Best Practices
```bash
# Hangi dosyaları LFS'e koymalı
*.psd, *.ai, *.sketch  # Tasarım dosyaları
*.zip, *.tar.gz, *.rar  # Arşiv dosyaları
*.mp4, *.avi, *.mov  # Video dosyaları
*.pdf, *.doc, *.docx  # Doküman dosyaları

# Hangi dosyaları LFS'e koymamalı
*.js, *.css, *.html  # Kod dosyaları
*.json, *.xml, *.yaml  # Konfigürasyon dosyaları
*.md, *.txt  # Metin dosyaları
```

**Ne İşe Yarar:** LFS kullanım stratejisini belirler
**Ne Yapar:** Hangi dosyaların LFS ile yönetileceğini gösterir 

---

## 21. Git Security

### SSH Key Yönetimi
```bash
# SSH key oluşturma
ssh-keygen -t rsa -b 4096 -C "email@example.com"

# SSH key'i GitHub'a ekleme
cat ~/.ssh/id_rsa.pub
# GitHub Settings > SSH and GPG keys > New SSH key

# SSH bağlantısını test etme
ssh -T git@github.com
```

**Ne İşe Yarar:** Güvenli Git erişimi sağlar
**Ne Yapar:** Şifre girmeden Git işlemleri yapmayı sağlar

### GPG İmzalama
```bash
# GPG key oluşturma
gpg --full-generate-key

# GPG key'i Git'e ekleme
gpg --list-secret-keys --keyid-format LONG
git config --global user.signingkey YOUR_GPG_KEY_ID

# Commit'leri imzalama
git commit -S -m "İmzalı commit"
git config --global commit.gpgsign true
```

**Ne İşe Yarar:** Commit'lerin gerçekten sizden geldiğini doğrular
**Ne Yapar:** Commit'leri dijital olarak imzalar

### Personal Access Token
```bash
# GitHub'da token oluşturma
# GitHub Settings > Developer settings > Personal access tokens

# Token ile push
git remote set-url origin https://token@github.com/kullanici/repo.git

# Token'ı environment variable olarak saklama
export GITHUB_TOKEN=your_token_here
git remote set-url origin https://$GITHUB_TOKEN@github.com/kullanici/repo.git
```

**Ne İşe Yarar:** Güvenli API erişimi sağlar
**Ne Yapar:** Şifre yerine token kullanmayı sağlar

### Güvenlik Best Practices
```bash
# Hassas bilgileri commit etmeme
echo "*.env" >> .gitignore
echo "secrets/" >> .gitignore
echo "*.key" >> .gitignore

# Commit geçmişinden hassas bilgileri temizleme
git filter-branch --force --index-filter \
  'git rm --cached --ignore-unmatch dosya_adi' \
  --prune-empty --tag-name-filter cat -- --all
```

**Ne İşe Yarar:** Güvenlik açıklarını önler
**Ne Yapar:** Hassas bilgilerin yanlışlıkla paylaşılmasını engeller

### Repository Güvenliği
```bash
# Branch protection kuralları
# GitHub repository settings > Branches > Add rule

# Required status checks
# Require pull request reviews
# Restrict pushes that create files

# Git hooks ile güvenlik kontrolleri
#!/bin/sh
# .git/hooks/pre-commit
if grep -q "password\|secret\|key" $(git diff --cached --name-only); then
    echo "Hassas bilgi tespit edildi!"
    exit 1
fi
```

**Ne İşe Yarar:** Repository güvenliğini artırır
**Ne Yapar:** Güvenlik kontrollerini otomatikleştirir 

---

## 22. Git Performance

### Repository Optimizasyonu
```bash
# Repository'yi temizle
git gc  # Garbage collection
git prune  # Eski objeleri temizle
git repack -a -d  # Objeleri paketle

# Büyük dosyaları bul
git rev-list --objects --all | git cat-file --batch-check='%(objecttype) %(objectname) %(objectsize) %(rest)' | sed -n 's/^blob //p' | sort --numeric-sort --key=2 | tail -10
```

**Ne İşe Yarar:** Repository performansını artırır
**Ne Yapar:** Gereksiz dosyaları temizler ve boyutu küçültür

### Shallow Clone
```bash
# Sadece son commit'leri klonla
git clone --depth 1 https://github.com/kullanici/repo.git

# Belirli sayıda commit klonla
git clone --depth 10 https://github.com/kullanici/repo.git

# Shallow clone'u tam clone'a çevir
git fetch --unshallow
```

**Ne İşe Yarar:** Büyük repository'leri hızlı klonlar
**Ne Yapar:** Sadece gerekli commit'leri indirir

### Partial Clone
```bash
# Blob'ları indirme
git clone --filter=blob:none https://github.com/kullanici/repo.git

# Belirli boyuttan büyük blob'ları indirme
git clone --filter=blob:limit=1m https://github.com/kullanici/repo.git

# Gerekli blob'ları indir
git fetch origin
```

**Ne İşe Yarar:** Büyük dosyaları gerektiğinde indirir
**Ne Yapar:** İlk klonlama süresini kısaltır

### Git Konfigürasyonu Optimizasyonu
```bash
# Git performans ayarları
git config --global core.preloadindex true
git config --global core.fscache true
git config --global gc.auto 256

# Windows için
git config --global core.autocrlf true
git config --global core.safecrlf warn
```

**Ne İşe Yarar:** Git performansını artırır
**Ne Yapar:** Sistem kaynaklarını daha verimli kullanır

### Index Optimizasyonu
```bash
# Index'i yeniden oluştur
git update-index --refresh

# Index'i temizle
git rm -r --cached .
git add .

# Index boyutunu kontrol et
du -sh .git/index
```

**Ne İşe Yarar:** Index performansını artırır
**Ne Yapar:** Git işlemlerini hızlandırır

### Network Optimizasyonu
```bash
# HTTP/2 desteği
git config --global http.version HTTP/1.1

# Compression
git config --global core.compression 9

# Buffer size
git config --global http.postBuffer 524288000
```

**Ne İşe Yarar:** Network performansını artırır
**Ne Yapar:** Push/pull işlemlerini hızlandırır 

---

## 23. Git Advanced Features

### Git Worktree
```bash
# Yeni worktree oluştur
git worktree add ../path/to/worktree branch_name

# Worktree listesi
git worktree list

# Worktree'yi kaldır
git worktree remove path/to/worktree

# Prune worktree'ler
git worktree prune
```

**Ne İşe Yarar:** Aynı repository'de birden fazla branch çalıştırır
**Ne Yapar:** Farklı branch'lerde aynı anda çalışmayı sağlar

### Git Bisect
```bash
# Bisect başlat
git bisect start

# Kötü commit'i işaretle
git bisect bad

# İyi commit'i işaretle
git bisect good v1.0.0

# Test et ve sonucu bildir
git bisect bad  # veya git bisect good

# Bisect'i sıfırla
git bisect reset
```

**Ne İşe Yarar:** Hangi commit'te hata oluştuğunu bulur
**Ne Yapar:** Binary search ile hata kaynağını tespit eder

### Git Notes
```bash
# Note ekle
git notes add -m "Bu commit hakkında not"

# Note'ları görüntüle
git notes show

# Note'ları listele
git notes list

# Note'ları düzenle
git notes edit
```

**Ne İşe Yarar:** Commit'lere ek bilgi ekler
**Ne Yapar:** Commit geçmişini bozmadan notlar ekler

### Git Subtree
```bash
# Subtree ekle
git subtree add --prefix=lib/example https://github.com/kullanici/lib.git main --squash

# Subtree'yi güncelle
git subtree pull --prefix=lib/example https://github.com/kullanici/lib.git main --squash

# Subtree'yi push et
git subtree push --prefix=lib/example https://github.com/kullanici/lib.git main
```

**Ne İşe Yarar:** Başka repository'yi alt dizin olarak ekler
**Ne Yapar:** Submodule'den farklı olarak kodları ana repository'ye kopyalar

### Git Archive
```bash
# Archive oluştur
git archive --format=zip --output=release.zip HEAD

# Belirli dizini archive et
git archive --format=tar --prefix=project/ HEAD | gzip > project.tar.gz

# Tag'den archive oluştur
git archive --format=zip --output=v1.0.0.zip v1.0.0
```

**Ne İşe Yarar:** Repository'nin belirli bir versiyonunu paketler
**Ne Yapar:** Release dosyaları oluşturur

### Git Bundle
```bash
# Bundle oluştur
git bundle create repo.bundle HEAD master

# Bundle'ı klonla
git clone repo.bundle repo

# Bundle'a yeni commit'ler ekle
git bundle create repo.bundle HEAD master ^HEAD~10
```

**Ne İşe Yarar:** Repository'yi tek dosyada paketler
**Ne Yapar:** Offline repository paylaşımı sağlar 

---

## 24. Git Integration

### CI/CD Entegrasyonu

#### GitHub Actions
```yaml
# .github/workflows/ci.yml
name: CI
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Run tests
      run: npm test
    - name: Build
      run: npm run build
```

**Ne İşe Yarar:** Otomatik test ve build süreci
**Ne Yapar:** Her commit'te kod kalitesini kontrol eder

#### GitLab CI
```yaml
# .gitlab-ci.yml
stages:
  - test
  - build
  - deploy

test:
  stage: test
  script:
    - npm install
    - npm test

build:
  stage: build
  script:
    - npm run build
```

**Ne İşe Yarar:** GitLab'da otomatik pipeline
**Ne Yapar:** Kod değişikliklerini otomatik işler

### IDE Entegrasyonu

#### VS Code
```json
// settings.json
{
  "git.enableSmartCommit": true,
  "git.confirmSync": false,
  "git.autofetch": true,
  "gitlens.codeLens.enabled": true
}
```

**Ne İşe Yarar:** VS Code'da gelişmiş Git desteği
**Ne Yapar:** Git işlemlerini IDE içinde yapmayı sağlar

#### JetBrains IDE'leri
```bash
# IntelliJ IDEA, WebStorm, PyCharm
# Git entegrasyonu otomatik olarak gelir
# VCS > Git menüsünden erişilebilir
```

**Ne İşe Yarar:** Profesyonel IDE'lerde Git desteği
**Ne Yapar:** Gelişmiş Git araçları sağlar

### Issue Tracking Entegrasyonu

#### GitHub Issues
```bash
# Commit mesajında issue referansı
git commit -m "Fix #123: Login bug düzeltildi"

# Branch isminde issue numarası
git checkout -b fix/123-login-bug
```

**Ne İşe Yarar:** Commit'leri issue'larla bağlar
**Ne Yapar:** Otomatik issue takibi sağlar

#### Jira Integration
```bash
# Jira issue key'i commit mesajında
git commit -m "PROJ-123: Yeni özellik eklendi"

# Smart commits
git commit -m "PROJ-123 #time 2h #comment Bug fix tamamlandı"
```

**Ne İşe Yarar:** Jira ile Git entegrasyonu
**Ne Yapar:** Proje yönetimi ile kod değişikliklerini bağlar

### Deployment Entegrasyonu

#### Heroku
```bash
# Heroku'ya deploy
git push heroku main

# Environment variables
heroku config:set NODE_ENV=production
```

**Ne İşe Yarar:** Otomatik deployment
**Ne Yapar:** Git push ile otomatik yayınlama

#### Netlify
```bash
# Netlify'da otomatik deploy
# Git push otomatik olarak trigger eder
# Build komutları netlify.toml'da tanımlanır
```

**Ne İşe Yarar:** Statik site deployment
**Ne Yapar:** Git push ile otomatik site güncelleme 

---

## 25. Git Automation

### Script'ler ile Otomasyon

#### Otomatik Commit Script'i
```bash
#!/bin/bash
# auto-commit.sh
git add .
git commit -m "Auto commit: $(date)"
git push origin main
```

**Ne İşe Yarar:** Düzenli commit'ler oluşturur
**Ne Yapar:** Cron job ile otomatik backup sağlar

#### Branch Cleanup Script'i
```bash
#!/bin/bash
# cleanup-branches.sh
git branch --merged | grep -v "\*" | xargs -n 1 git branch -d
git remote prune origin
```

**Ne İşe Yarar:** Eski branch'leri temizler
**Ne Yapar:** Repository'yi düzenli tutar

### Git Hooks ile Otomasyon

#### Pre-commit Hook
```bash
#!/bin/sh
# .git/hooks/pre-commit
echo "Pre-commit hook çalışıyor..."

# Lint kontrolü
npm run lint
if [ $? -ne 0 ]; then
    echo "Lint hataları var!"
    exit 1
fi

# Test çalıştır
npm test
if [ $? -ne 0 ]; then
    echo "Test'ler başarısız!"
    exit 1
fi
```

**Ne İşe Yarar:** Commit öncesi kontroller yapar
**Ne Yapar:** Kod kalitesini otomatik kontrol eder

#### Post-merge Hook
```bash
#!/bin/sh
# .git/hooks/post-merge
echo "Post-merge hook çalışıyor..."

# Dependencies güncelle
npm install

# Build işlemi
npm run build
```

**Ne İşe Yarar:** Merge sonrası işlemler yapar
**Ne Yapar:** Otomatik dependency güncelleme ve build

### GitHub Actions ile Otomasyon

#### Release Automation
```yaml
# .github/workflows/release.yml
name: Release
on:
  push:
    tags:
      - 'v*'
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Create Release
      uses: actions/create-release@v1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        tag_name: ${{ github.ref }}
        release_name: Release ${{ github.ref }}
        body: |
          Changes in this Release:
          ${{ github.event.head_commit.message }}
        draft: false
        prerelease: false
```

**Ne İşe Yarar:** Otomatik release oluşturur
**Ne Yapar:** Tag push'unda otomatik GitHub release

### Git Aliases ile Otomasyon

#### Gelişmiş Alias'lar
```bash
# Otomatik add + commit
git config --global alias.ac '!f() { git add . && git commit -m "$1"; }; f'

# Otomatik push
git config --global alias.pushup '!f() { git push origin $(git branch --show-current); }; f'

# Otomatik pull + rebase
git config --global alias.pullr '!f() { git pull --rebase origin $(git branch --show-current); }; f'
```

**Ne İşe Yarar:** Karmaşık Git işlemlerini basitleştirir
**Ne Yapar:** Tek komutla birden fazla işlem yapar

---

## Sonuç

Bu Git cheatsheet, Git'in temel ve ileri seviye özelliklerini kapsamlı bir şekilde ele almaktadır. Her komutun ne işe yaradığı ve ne yaptığı açıkça belirtilmiştir.

### Önemli Notlar:
- Git komutlarını kullanmadan önce mutlaka test edin
- Önemli değişikliklerden önce backup alın
- Takım çalışmasında Git workflow'unuza uyun
- Güvenlik best practice'lerini takip edin

### Faydalı Kaynaklar:
- [Git Resmi Dokümantasyonu](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Git Book](https://git-scm.com/book/en/v2)

Bu cheatsheet'i düzenli olarak güncelleyerek Git bilgilerinizi taze tutun!