<div align="center">

# 🎬 VideoX Compressor

### Simple, hardware-accelerated Windows video compression for recorded classes, tutorials, screen recordings and low-motion videos.

<p>
  <a href="#download-en">Download</a> •
  <a href="#english">English</a> •
  <a href="#quick-start-en">Quick Start</a> •
  <a href="#activation-en">Activation</a> •
  <a href="#settings-en">Settings</a> •
  <a href="#pipeline-en">Pipeline</a> •
  <a href="#persian">فارسی</a>
</p>

![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![FFmpeg](https://img.shields.io/badge/Engine-FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)
![Hardware](https://img.shields.io/badge/Acceleration-NVIDIA%20%7C%20Intel%20%7C%20AMD-76B900?style=for-the-badge)
![Codec](https://img.shields.io/badge/Codec-H.265%20%7C%20H.264%20%7C%20VP9-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Beta-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-Device%20ID-blueviolet?style=for-the-badge)

**Code, design and development by The Louis Mahdi**  
**Telegram:** `@thelouis_mahdi`

</div>

---

<a id="download-en"></a>

## Download for Windows

For normal users, download the ready-to-run Windows ZIP package from **Releases**. You do **not** need to clone the source code.

<div align="center">

### 👉 [Download latest Windows release](https://github.com/TheLouisMahdi/VideoX_Compressor/releases/latest)

</div>

Recommended package name:

```text
VideoX_Compressor_v1.4.4_Beta_Stable_Device_ID.zip
```

After downloading:

1. Extract the ZIP file.
2. Run `VideoX.exe`.
3. Copy your Device ID from the activation page.
4. Send it to `@thelouis_mahdi` on Telegram to receive your device-specific `license.key` file.

> VideoX uses device-specific activation. Do not publish your `license.key` file.

---

## Important License Compatibility Notice

Starting from **VideoX Compressor v1.4.4 Beta - Stable Device ID**, the Device ID and license-generation structure has changed.

This means:

- Licenses generated for versions before `v1.4.4` are deprecated.
- Public beta builds before `v1.4.4` should be considered legacy / deprecated for licensing.
- Users upgrading from older beta builds may need a new `license.key` once.
- From `v1.4.4` onward, licenses should be generated using the updated v1.4.4 license admin tools.
- The old beta license flow should not be used for new users.

The reason for this change is stability. Older beta builds could generate a different Device ID after changes in network-related system information. Version `v1.4.4` removes unstable Device ID dependencies such as MAC address and computer name.

---

<a id="english"></a>

# 🇬🇧 English

## What is VideoX Compressor?

**VideoX Compressor** is a Windows GUI video compression tool designed to reduce large video files with a simple workflow.

It is best optimized for recorded classes, tutorials, screen recordings, online meetings, slide-based educational videos, low-motion lecture videos and already-compressed videos that need smaller output size.

Depending on the system, VideoX can try **NVIDIA NVENC**, **Intel QSV / Quick Sync**, **AMD AMF**, or fall back to CPU mode. It uses FFmpeg and FFprobe internally.

> Current public beta: **VideoX Compressor v1.4.4 Beta - Stable Device ID**

---

<a id="quick-start-en"></a>

## Quick Start for Normal Users

For most users, use **Simple Mode**.

```text
Interface Mode: Simple
Compression Level: Medium or Compressed
Fast Mode: On for GPU / parallel processing
Fast Mode: Off for CPU-only compression
```

VideoX avoids upscaling smaller videos, especially in Simple Mode. For example, a 480p source will not be enlarged to 720p only because a preset requested 720p.

---

<a id="activation-en"></a>

## License Activation Guide

VideoX uses a **Device ID based license system**.

1. Run `VideoX.exe`.
2. Copy the Device ID from the activation page.
3. Send your Device ID on Telegram to:

```text
@thelouis_mahdi
```

4. After verification, you will receive a device-specific `license.key` file.
5. Place `license.key` next to `VideoX.exe`, or select it from inside the app.
6. Click **Recheck**.
7. Enter the program.

### Stable Device ID in v1.4.4

Version `v1.4.4` improves Device ID stability.

Previous beta builds could generate a different Device ID when system network information changed, because the old algorithm depended on values such as computer name and MAC address. This could happen after changes involving Wi-Fi, LAN, Bluetooth, VPN, virtual adapters, Hyper-V, WSL or random MAC address settings.

The new Device ID logic:

- removes MAC address dependency
- removes computer-name dependency
- uses Windows MachineGuid as the primary stable identity
- creates a persistent Install ID fallback if MachineGuid is not available
- is not affected by GPU, driver, VPN, Wi-Fi, Bluetooth or network adapter changes

Important: users of older beta builds may need a new `license.key` once after upgrading, because the more stable Device ID algorithm can generate a new ID the first time.

---

## Simple Mode vs Advanced Mode

| Mode | Purpose |
|---|---|
| Simple | For normal users. Choose only one compression level and optionally enable Fast Mode. |
| Advanced | Full control over GPU, CPU, FPS, height, audio, pipeline and diagnostics. |

Simple Mode levels:

| Level | Target |
|---|---|
| High Quality | Best simple choice when quality matters more than minimum size. |
| Medium | Balanced size and quality. |
| Compressed | Smaller output for classes and tutorials. |
| Very Compressed | Stronger compression for low-motion videos. |
| Very Very Compressed | Aggressive compression with possible visible quality loss. |
| Maximum Compression | Smallest-size simple mode; quality loss may happen. |

---

## Why VideoX?

| Feature | Explanation |
|---|---|
| Simple / Advanced UI | Simple Mode for normal users; Advanced Mode for full control. |
| Stable Device ID | More stable activation ID in v1.4.4. |
| Hardware acceleration | Tries NVIDIA, Intel or AMD hardware encoding when available. |
| Dynamic GPU Preference | Shows only hardware paths that pass real runtime tests. |
| Pipeline preview | Explains the real Decode / Scale / Encode path before compression. |
| Legacy NVIDIA fallback | Can use a legacy NVIDIA FFmpeg build for older NVIDIA driver compatibility. |
| Smart Size Target | Improves size reduction on already-compressed videos. |
| No upscale protection | Prevents smaller sources from being enlarged unnecessarily. |
| File queue | Shows selected input files before compression. |
| Output validation | Checks output files and deletes invalid/corrupted partial outputs. |
| Diagnostic reports | Saves useful logs for debugging hardware and FFmpeg issues. |

---

<a id="settings-en"></a>

## Recommended Settings

### Simple Mode, normal use

```text
Interface Mode: Simple
Compression Level: Medium or Compressed
Fast Mode: On
```

### Simple Mode, CPU-only compatibility

```text
Interface Mode: Simple
Compression Level: Medium or Compressed
Fast Mode: Off
```

### Advanced Mode, safe public setting

```text
Preset: Recorded Class / Screen Recording
Output Format: mp4
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available
GPU Quality: 32 to 36
CPU CRF: 30 to 34
```

---

<a id="pipeline-en"></a>

## Pipeline Clarity Guide

### Performance Mode

| Option | What it does |
|---|---|
| Stable | Safer mode. Usually processes one hardware job at a time. |
| High Throughput | May process up to 2 hardware jobs in parallel on supported hardware. |

### Processing Strategy

| Option | What it means |
|---|---|
| Auto Balanced | Recommended default. Uses hardware encoding when available while keeping safer behavior. |
| Maximum Hardware Acceleration | Most meaningful for NVIDIA with Hardware Decode set to Aggressive. |
| CPU Only | Disables GPU encoding and forces CPU encoding. |

### Hardware Decode

| Option | Decode | Scale | Encode |
|---|---|---|---|
| Off | CPU | CPU | GPU or CPU depending on selected encoder |
| Auto | FFmpeg hardware auto when possible | Usually CPU | GPU or CPU |
| Aggressive | Mainly NVIDIA CUDA when NVIDIA is selected | NVIDIA CUDA only in NVIDIA + Maximum mode | NVIDIA NVENC |

`Hardware Decode: Off` is the safest mode and still allows GPU encoding.

### GPU Preference

VideoX shows only hardware options that pass real runtime tests.

```text
Auto Best Available
NVIDIA NVENC
Intel QSV
AMD AMF
CPU Only
```

For dual-GPU laptops, set these files to **High Performance** in Windows Graphics Settings:

```text
VideoX.exe
ffmpeg/modern/bin/ffmpeg.exe
ffmpeg/legacy-nvidia/bin/ffmpeg.exe
```

---

## Required Package Structure

```text
VideoX_Compressor_v1.4.4_Beta_Stable_Device_ID/
├── VideoX.exe
├── ffmpeg/
│   ├── modern/
│   │   └── bin/
│   │       ├── ffmpeg.exe
│   │       └── ffprobe.exe
│   └── legacy-nvidia/
│       └── bin/
│           ├── ffmpeg.exe
│           └── ffprobe.exe
├── _internal/
├── README.txt
└── LICENSE_NOTICE.txt
```

Do not delete `ffmpeg/` or `_internal/`. Do not include `license.key` in the public ZIP package.

---

<a id="persian"></a>

<div dir="rtl" align="right">

# 🇮🇷 فارسی

## معرفی برنامه

**ویدیو ایکس کامپرسور** یک نرم‌افزار ویندوزی برای فشرده‌سازی ویدیو است. هدف برنامه این است که کاربر بدون درگیر شدن با دستورهای پیچیده، بتواند فایل‌های ویدیویی سنگین را به خروجی کم‌حجم‌تر تبدیل کند.

> نسخه فعلی بتا: **VideoX Compressor v1.4.4 Beta - Stable Device ID**

---

## اطلاعیه مهم درباره لایسنس

از نسخه **v1.4.4 Beta - Stable Device ID** به بعد، ساختار Device ID و ساخت لایسنس تغییر کرده است.

یعنی:

- لایسنس‌های ساخته‌شده برای نسخه‌های قبل از `v1.4.4` منسوخ هستند.
- نسخه‌های قبل از `v1.4.4` از نظر لایسنس‌دهی قدیمی محسوب می‌شوند.
- کاربران نسخه‌های قبلی ممکن است بعد از ارتقا یک بار به `license.key` جدید نیاز داشته باشند.
- از این نسخه به بعد، لایسنس باید با پنل یا ابزار جدید v1.4.4 ساخته شود.
- ابزارهای قدیمی ساخت لایسنس دیگر برای کاربران جدید پیشنهاد نمی‌شوند.

دلیل این تغییر، پایدار کردن Device ID است. در نسخه‌های قبلی، Device ID ممکن بود با تغییرات شبکه، VPN، وای‌فای، بلوتوث یا آداپتورهای مجازی عوض شود.

---

## شروع سریع برای کاربر عادی

```text
Interface Mode: Simple
Compression Level: Medium یا Compressed
Fast Mode: On برای استفاده از GPU / پردازش سریع‌تر
Fast Mode: Off برای فشرده‌سازی فقط با CPU
```

برنامه در حالت ساده از بزرگ‌کردن بی‌دلیل ویدیوهای کوچک جلوگیری می‌کند.

---

## فعال‌سازی و Stable Device ID

نسخه `v1.4.4` پایداری Device ID را بهتر می‌کند.

در نسخه‌های قبلی، Device ID ممکن بود به دلیل تغییر اطلاعات شبکه عوض شود؛ مثلاً با تغییر Wi-Fi، LAN، Bluetooth، VPN، آداپتور مجازی، Hyper-V، WSL یا Random MAC Address.

در نسخه جدید:

- وابستگی به MAC Address حذف شد.
- وابستگی به نام کامپیوتر حذف شد.
- مبنای اصلی Device ID مقدار Windows MachineGuid است.
- اگر MachineGuid در دسترس نباشد، یک Install ID پایدار ساخته و ذخیره می‌شود.
- تغییر کارت گرافیک، درایور، VPN، وای‌فای، بلوتوث یا کارت شبکه نباید Device ID را عوض کند.

نکته مهم: کاربران نسخه‌های قدیمی‌تر ممکن است بعد از ارتقا به v1.4.4 یک بار به لایسنس جدید نیاز داشته باشند.

---

## حالت ساده و حرفه‌ای

| حالت | کاربرد |
|---|---|
| Simple | مناسب کاربر عمومی؛ فقط سطح فشرده‌سازی و Fast Mode را انتخاب می‌کند. |
| Advanced | مناسب کاربر حرفه‌ای؛ کنترل کامل روی GPU، CPU، FPS، کیفیت، صدا و Pipeline. |

---

## ساختار لازم پوشه‌ها

```text
VideoX_Compressor_v1.4.4_Beta_Stable_Device_ID/
├── VideoX.exe
├── ffmpeg/
│   ├── modern/
│   │   └── bin/
│   │       ├── ffmpeg.exe
│   │       └── ffprobe.exe
│   └── legacy-nvidia/
│       └── bin/
│           ├── ffmpeg.exe
│           └── ffprobe.exe
├── _internal/
├── README.txt
└── LICENSE_NOTICE.txt
```

پوشه‌های `ffmpeg` و `_internal` را حذف نکنید. فایل `license.key` را داخل بسته عمومی قرار ندهید.

</div>

---

<div align="center">

### Code, design and development by **The Louis Mahdi**

**Telegram:** `@thelouis_mahdi`

</div>
