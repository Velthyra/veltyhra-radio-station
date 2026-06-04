# VELTHYRA | Administrative Radio Portal

[![Version](https://img.shields.io/badge/Version-3.0.1--Industrial-blueviolet?style=for-the-badge)](https://github.com/)
[![PHP](https://img.shields.io/badge/PHP-8.x-777bb4?style=for-the-badge&logo=php)](https://www.php.net/)

Velthyra is a lightweight, centralized administrative system designed for radio broadcast management and real-time streaming telemetry. It provides a multi-lingual interface for controlling in-game audio streams with precision and security.

---

## Key Features

- **Globalization**: Native support for 6 languages (EN, TR, FR, BG, DE, RU) via central localization engine.
- **Security**: SHA-512 Master Key authentication, session fingerprinting, and IP-level blacklisting.
- **Telemetry**: Real-time track progress visualization and gapless stream synchronization.
- **Data Layer**: JSON-based architecture. No database required. Portable and fast.
- **Media Hub**: Centralized MP3 library with automated audit logging.

---

## Deployment Guide

### 1. File Upload
Upload all files to a PHP-enabled web server. Requires PHP 8.0+ with GD and Session extensions.

### 2. File Permissions
The following directories must be writable by the server process:
```bash
chmod -R 775 ./data/
chmod -R 775 ./admin/uploads/
```

### 3. Core Configuration
Identify `includes/config.php` and define a unique Security Salt:
```php
define('VELORIAN_SALT', 'CHANGEMEBUDDY');
```

---

## Administrative Access

**Login Path:** `http://your-domain.com/admin/login.php`

> [!IMPORTANT]
> Change the Master Key.
> Open `functions/auth.php` and locate the `VELORIAN_MASTER_KEY` constant. 
> Replace the placeholder `CHANGEMEBUDDY` with a secure passphrase immediately.

---

## XMR Radio Integration

Velthyra is designed for roleplay environments requiring a constant audio stream link. Use the following Endpoint URL for in-game radio systems:

### `http://your-domain.com/stream.php`

**Technical Logic:**
- **Synchronization:** The stream is synchronized for all listeners based on server-side micro-timestamping.
- **Automated Playback:** The engine cycles through the `admin/uploads/mp3s/` library automatically.
- **Low Latency:** Optimized for consistent playback across different geographical regions.

---

## Administrator Manual

### 1.01 Dashboard
Summary of server health, disk usage, and user suggestions.

### 1.02 Live Monitor
Technical telemetry view showing track offset, duration, and synchronization source.

### 1.03 Library Operations
MP3 file management. Supports secure upload and deletion. Metadata extraction is handled internally.

### 1.04 Security Matrix
Access to Audit Logs for tracking administrative actions. Global Blacklist management for IP-level access control.

### 1.05 Global Settings
Site title, brand color calibration, and Maintenance Mode toggle for public traffic.

---

## Disclaimer

This product is intended for fictional roleplay purposes only. It has no affiliation with real-world broadcasting entities or regulatory frameworks.

---
**VELTHYRA ENTERPRISE SOLUTIONS**  
*Ref: VLT-MAN-2026*
