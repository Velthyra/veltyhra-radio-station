# VELTHYRA | Administrative Radio Portal

[![Version](https://img.shields.io/badge/Version-3.0.1--Industrial-blueviolet?style=for-the-badge)](https://github.com/)
[![PHP](https://img.shields.io/badge/PHP-8.x-777bb4?style=for-the-badge&logo=php)](https://www.php.net/)

Velthyra is a lightweight, centralized administrative system engineered for radio broadcast management and real-time streaming telemetry.

---

## System Architecture / Sistem Mimarisi

```mermaid
graph TD
    A[Admin Portal] -->|Manages| B(Data Layer /JSON/)
    A -->|Uploads| C(MP3 Library)
    D[Stream Endpoint] -->|Reads| B
    D -->|Reads| C
    D -->|Outputs| E[In-Game Radio]
    
    subgraph Security Layer
    F[Master Key]
    G[IP Blacklist]
    H[Audit Logs]
    end
    
    A -.-> Security Layer
```

---

## [TR] TÜRKÇE REHBER

### 1.01 Sistem Özeti
Velthyra, radyo yayını ve içerik yönetimi için tasarlanmış merkezi bir idari arayüzdür. Veritabanı gerektirmeyen JSON mimarisi sayesinde hızlı ve taşınabilir bir yapı sunar.

### 1.02 Kurulum Adımları
1. **Dosya Aktarımı**: Tüm dosyaları PHP 8.0+ destekleyen sunucunuza yükleyin.
2. **İzinler**: `./data/` ve `./admin/uploads/` klasörlerinin yazılabilir (CHMOD 775) olduğundan emin olun.
3. **Konfigürasyon**: Aşağıda belirtilen kritik dosyaları güncelleyin.

### 1.03 XMR Radyo Entegrasyonu
Oyun içi sistemlere entegre etmek için `stream.php` dosyasını kullanın.
**Link**: `http://site-adresiniz.com/stream.php`

---

## [EN] ENGLISH GUIDE

### 1.01 System Overview
Velthyra is a centralized administrative interface designed for radio broadcasting and content management. Its zero-database JSON architecture ensures high performance and portability.

### 1.02 Deployment Guide
1. **Upload**: Deploy all source files to a PHP 8.0+ web server environment.
2. **Permissions**: Ensure `./data/` and `./admin/uploads/` are writable (CHMOD 775).
3. **Configuration**: Update the critical files listed in the section below.

### 1.03 XMR Radio Integration
Use the `stream.php` endpoint for in-game radio system integration.
**Link**: `http://yourdomain.com/stream.php`

---

## CRITICAL CONFIGURATION / DEĞİŞTİRİLECEK YERLER

Güvenli bir kurulum için aşağıdaki dosyalardaki değerleri mutlaka değiştirmeniz gerekmektedir:

| Dosya Yolu (Path) | Değişken (Variable) | İşlem (Action) |
| :--- | :--- | :--- |
| `functions/auth.php` | `VELORIAN_MASTER_KEY` | `CHANGEMEBUDDY` değerini çok uzun ve güvenli bir anahtar ile değiştirin. |
| `includes/config.php` | `VELORIAN_SALT` | `CHANGEMEBUDDY` değerini rastgele, uzun bir metin ile değiştirin. |
| `data/users.json` | `admin / password` | İlk girişte admin panelinden şifrenizi mutlaka güncelleyin. (Varsayılan: admin/admin) |

---

## Modüller / Modules

- **Dashboard**: Sistem sağlığı ve sunucu istatistikleri.
- **Live Monitor**: Parça bilgisi, saniye (offset) ve senkronizasyon takibi.
- **Library**: MP3 yükleme, listeleme ve silme işlemleri.
- **Security**: IP engelleme (Blacklist) ve işlem geçmişi (Audit Logs).
- **Settings**: Site başlığı, renk teması ve bakım modu yönetimi.

---
**VELTHYRA ENTERPRISE SOLUTIONS**  
*The Structure of Sound | Ref: VLT-MAN-2026*
