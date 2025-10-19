# VibeOS Admin Rehberi – Single Agent v3.2  
> "Claude ile Profesyonel Yazılım Geliştirme Yönetimi"

## 🚀 1. Hızlı Kurulum (2 dakika)
```powershell
# Proje dizini oluştur
mkdir MyProject && cd MyProject

# Git repository başlat
git init

# VibeOS dosyalarını kopyala
# VibeOS_Single_Agent_v3.2.md, README_ADMIN.md, README_USER.md, README.md

# Temel klasör yapısı oluştur
mkdir .vibe, mgmt, src, tests
New-Item .vibe/symbols.json, .vibe/config.json -ItemType File
```

## 📊 2. Günlük Yönetim Komutları

### Proje Durumu Kontrolleri
| Amaç | Claude'a Söylenen | Beklenen Çıktı |
|------|------------------|----------------|
| **Genel durum** | "Proje durumunu kontrol et" | `mgmt/PROJECT_STATUS.md` güncellemesi |
| **Sağlık raporu** | "Sağlık kontrolü yap" | Constitution score, hata analizi |
| **Kod kalitesi** | "Kod kokusu taraması yap" | Duplicate code, karmaşık fonksiyonlar |
| **Sembol haritası** | "Sembol indexini güncelle" | `.vibe/symbols.json` yenileme |

### Git & Versiyon Kontrolü
```powershell
# Son commit'e dönmek için
git log --oneline -5                    # Son 5 commit'i göster
git checkout <hash>                     # Specific commit'e dön

# Sembol değişikliklerini takip etmek için
git log --grep="sym:"                   # Sembol etiketli commit'ler
```

## ⚙️ 3. Claude Konfigürasyonu

### Temel Çalışma Modları
```json
// .vibe/config.json
{
  "mode": "developer",           // architect | developer | debugger | researcher | quality
  "fast_track": false,          // true = Complexity ≤3 hızlı işlem
  "checkpoint_threshold": 5,     // Complexity ≥5 = Onay gerekli
  "auto_commit": false,         // true = Otomatik commit
  "strict_approval": true       // false = Daha az onay isteme
}
```

### Claude'a Mod Değiştirme
```
"Architect moduna geç - sadece plan yap, kod yazma"
"Developer moduna geç - planı kodla"
"Quality Checker moduna geç - testleri kontrol et"
"Fast-track modu aç - küçük değişiklikleri hızlı yap"
```

## 🛡️ 4. Kalite Kontrol Barajları

### Otomatik Durdurma Koşulları
- **3 aynı hata** → Claude durur, yardım ister
- **Complexity ≥ 8** → İnsan onayı olmadan commit atmaz  
- **Constitution score < 90%** → Düzeltme listesi sunar
- **Performance regresyonu > 20%** → Uyarı verir

### Manuel Onay Gereken Durumlar
- Major refactoring (10+ dosya değişimi)
- API breaking changes
- Database schema değişiklikleri
- Security-critical kod değişiklikleri

## 📈 5. Başarı Metrikleri Takibi

### Session Sonunda Kontrol Edilenler
```markdown
# mgmt/SESSION_REPORT.md örnek çıktı
- **Başarı Oranı**: 94%
- **Tamamlanan Görevler**: 8/9
- **Ortalama Complexity**: 6.2
- **Hata Sayısı**: 2
- **Constitution Score**: 96%
- **Kod Kalite Skoru**: 8.1/10
- **Teknik Borç Durumu**: İyileşti (+12%)
```

### Commit Mesajı Örnekleri
```
feat: Add user authentication [complexity:7] [sym:a1b2c3]
fix: Resolve login bug [fast-track] [sym:d4e5f6] 
refactor: Clean up API layer [approval-needed] [sym:g7h8i9]
```

## 🚨 6. Problem Çözme & Acil Durumlar

### Claude Sıkıştığında
```
"Sıkıştım yardım et"               → 3 alternatif yol sunar
"Son kararlı noktaya dön"          → git checkout son-stabil-commit
"Farklı yaklaşım dene"             → Alternatif strateji önerir
"Session raporunu hazırla"         → Mevcut durumu özetler
```

### Rollback Prosedürü
```powershell
# 1. Son iyi durumu bul
git log --oneline --grep="stable\|checkpoint"

# 2. Geri dön
git checkout <commit-hash>

# 3. Yeni branch oluştur
git checkout -b recovery-<date>

# 4. Claude'a durumu bildir
# "Rollback yaptım, <commit-hash> durumundayız"
```

## 🔧 7. Bakım & Güncelleme

### Haftalık Bakım Rutini
1. **Dependency Check**: "npm audit ve outdated kontrol et"
2. **Code Cleanup**: "Kullanılmayan kod var mı bak" 
3. **Symbol Index**: "Sembol indexini temizle ve güncel"
4. **Documentation**: "README'leri güncel mi kontrol et"

### Güvenlik Kontrolleri
```powershell
# .env dosyası git'te olmamalı
git ls-files | grep "\.env$"       # Boş çıktı olmalı

# Secrets leak kontrolü  
git log -S "password\|secret\|key" --oneline

# Package vulnerabilities
npm audit --audit-level=high
```

## 📚 8. Raporlama & Dokümantasyon

### Otomatik Oluşan Dosyalar
```
mgmt/
├── PROJECT_STATUS.md      # Güncel proje durumu
├── ERRORS_LOG.md          # Hata geçmişi ve çözümleri
├── SESSION_REPORT.md      # Session özeti
└── IMPROVEMENT.md         # İyileştirme önerileri

.vibe/
├── symbols.json           # Kod sembol haritası
├── config.json           # Claude konfigürasyonu  
└── session_notes.json    # Session notları
```

### Stakeholder Raporları İçin
```
"Executive summary hazırla"        → Yönetim için özet
"Technical debt raporu çıkar"      → Geliştirici ekibi için
"Performance metrics özetle"       → DevOps için
"Security assessment yap"          → InfoSec için
```

## 🎯 9. Best Practices

### Claude ile Verimli Çalışma
✅ **DO:**
- Küçük, atomik görevler verin
- Her önemli değişiklik öncesi onay istenmesini sağlayın
- Session notlarını düzenli kontrol edin
- Git commit mesajlarını okunaklı tutun

❌ **DON'T:**
- 10+ dosya değiştirecek dev görevleri tek seferde vermeyin
- Fast-track modunu kritik kod için kullanmayın
- Constitution kurallarını atlamaya zorlamayın
- Session arası context kaybını göz ardı etmeyin

### İdeal Workflow
```
1. Claude'a görevi tanımlayın
2. Complexity skorunu değerlendirtin
3. Eğer ≥8 ise adım adım approval alın  
4. Her checkpoint'te kontrolü yapın
5. Session sonunda raporu inceleyin
6. Git history'yi clean tutun
```

---

> **💡 Pro Tip**: Claude'un "constitution score" düştüğünde duraksama yapmayın - bu kalite kontrolünün çalıştığı anlamına gelir. Düzeltme önerilerini dinleyin.

**Detaylar**: Bu rehber VibeOS Single-Agent v3.2 için hazırlanmıştır. Güncellemeler için dosya tarihini kontrol edin.