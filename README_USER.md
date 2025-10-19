# VibeOS Kullanıcı Rehberi – v3.2
> "Claude ile Kod Yazmak İçin 5 Dakikalık Rehber"

## 🎯 Temel Prensip
**Claude'a söylediğiniz her şey VibeOS kuralları çerçevesinde yapılır:**
- Büyük işleri küçük parçalara böler
- Her önemli değişiklik için onay ister  
- Git commit'lerini otomatik atar
- Kod kalitesini sürekli kontrol eder

---

## 🚀 İlk Kullanım (30 saniye)

### 1. Proje başlat
```
"Yeni bir React projesi oluştur, TypeScript kullan"
```

### 2. Özellik ekle
```
"Ana sayfada mavi bir buton ekle, tıklayınca 'Merhaba' yazsın"
```

### 3. Test et
```
"Bu buton için test yaz ve çalıştır"
```

**Bu kadar! Claude gerisini halleder.**

---

## 💬 Doğru İletişim Örnekleri

### ✅ İYİ Örnekler:
```
"Login formu yap - email ve password alanları olsun"
"Bu fonksiyonu daha hızlı çalışacak şekilde optimize et"  
"Kod kokusu var mı kontrol et, temizle"
"Bu hatayı çöz: TypeError: Cannot read property"
"README.md dosyasını güncelle"
```

### ❌ Kötü Örnekler:
```
"Tüm projeyi değiştir"              → Çok genel
"Hep birlikte yapalım"              → Claude ne yapacağını bilemez
"İstediğin gibi yap"                → Hedef belirsiz
"5 dk'da bitir"                     → Zamana odaklanmış, kaliteye değil
```

---

## 🎚️ Çalışma Modları

### 🏃 Hızlı Mod
Küçük değişiklikler için:
```
"Hızlı mod aç"
"Bu butonun rengini kırmızı yap"
"Hızlı mod kapat" 
```

### 🏗️ Architect Modu
Büyük planlama için:
```
"Architect moduna geç"
"E-ticaret sitesi mimarisi planla"
"Developer moduna geç ve planı kodla"
```

### 🔍 Quality Modu  
Kod inceleme için:
```
"Quality Checker moduna geç"
"Tüm kodu gözden geçir, sorunları listele"
"Test coverage'ı kontrol et"
```

---

## 🛡️ Güvenlik & Onay Sistemi

### Otomatik Onay İstenen Durumlar:
- **Complexity ≥ 8** işlerde
- **10+ dosya** değişikliğinde  
- **Database schema** değişiminde
- **API breaking change**'lerinde

### Onay Verme:
```
Claude: "Bu değişiklik 15 dosyayı etkileyecek, onay verir misiniz?"
Siz: "Evet, devam et"
Siz: "Hayır, daha küçük parçalara böl"
```

---

## 📊 İlerleme Takibi

### Session Sonu Raporu
Claude her session sonunda size özetler:
```
✅ Tamamlanan: 5/6 görev
📊 Başarı Oranı: %94
🐛 Hata Sayısı: 1
⚡ Kalite Skoru: 8.7/10
📝 Öneriler: 3 iyileştirme
```

### Git Commit Mesajları
Claude'un attığı commit'ler:
```
feat: Add login form [complexity:6] [sym:a1b2c3]
fix: Resolve button color issue [fast-track]  
refactor: Optimize API calls [approval-needed]
```

---

## 🚨 Sorun Çözme 

### Claude Takıldığında
```
Claude: "Bu sorunu 3 farklı yoldan denedim, yardım eder misiniz?"
Siz: "Farklı yaklaşım öner"
Siz: "Son kararlı noktaya dön"
Siz: "Session raporunu hazırla"
```

### Geri Alma
```
"Son commit'i geri al"
"2 commit geri git" 
"Bugün yapılan değişiklikleri undo et"
```

---

## 🎯 Popüler İstekler

### Frontend
```
"Modern bir navbar yap"
"Dark mode toggle ekle"  
"Bu sayfayı responsive yap"
"Loading spinner ekle"
"Form validasyonu yap"
```

### Backend  
```
"REST API endpoints yaz"
"Database modeli oluştur"
"Authentication middleware ekle"
"Error handling iyileştir"
"API documentation güncel"
```

### Testing
```
"Unit testler yaz"
"Integration test ekle"  
"E2E test senaryoları oluştur"
"Test coverage raporu çıkar"
```

### Maintenance
```
"Kod kokusu taraması yap"
"Kullanılmayan kodları temizle"
"Dependencies güncelle" 
"Security audit yap"
"Performance analizi yap"
```

---

## 📁 Dosya Yapısı (Otomatik Oluşur)

```
YourProject/
├── src/              # Kodlarınız
├── tests/            # Testler
├── .vibe/            # VibeOS konfigürasyonu  
│   ├── symbols.json  # Kod haritası
│   └── config.json   # Ayarlar
├── mgmt/             # Yönetim raporları
│   ├── PROJECT_STATUS.md
│   ├── SESSION_REPORT.md
│   └── ERRORS_LOG.md
└── README.md         # Bu dosya
```

---

## 💡 İpuçları

### ✅ Verimli Çalışma İçin:
- **Spesifik** olun: "Buton ekle" yerine "Mavi login butonu ekle"
- **Adım adım** ilerleyin: Büyük değişiklikleri parçalara bölün
- **Onayları** okuyun: Claude'un ne yapacağını anladığınızdan emin olun
- **Session raporlarını** kontrol edin: İlerlemeniziölçün

### ❌ Kaçınılması Gerekenler:
- Çok genel talepler yapmayın
- Claude'u anayasa kurallarını atlamaya zorlamayın
- Fast-track modunu kritik işler için kullanmayın
- Session arası context kaybını göz ardı etmeyin

---

**🔥 Pro Tip**: Claude size "constitution score düştü" derse endişe etmeyin - bu kalite kontrolünün çalıştığı anlamına gelir!

---

> **📞 Yardım**: Daha detaylı bilgi için `README_ADMIN.md` dosyasını inceleyin veya Claude'a "Yardım dosyalarını göster" deyin.