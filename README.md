<div align="center">

# 🎬 VideoX Compressor

### Hardware-accelerated Windows video compression for recorded classes, tutorials, screen recordings and low-motion videos.

<p>
  <a href="#english">English</a> •
  <a href="#quick-start-en">Quick Start</a> •
  <a href="#activation-en">Activation</a> •
  <a href="#screenshots-en">Screenshots</a> •
  <a href="#settings-en">Settings Guide</a> •
  <a href="#hardware-en">Hardware Guide</a> •
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

<a id="english"></a>

# 🇬🇧 English

## What is VideoX Compressor?

**VideoX Compressor** is a Windows GUI video compression tool designed to reduce large video files with a simple workflow.

The main goal of VideoX is to make video compression easier for normal users while still using modern hardware acceleration when available. Depending on the system, VideoX can try **NVIDIA NVENC**, **Intel QSV / Quick Sync**, **AMD AMF**, or fall back to CPU mode.

VideoX is currently best optimized for:

- recorded classes
- tutorials
- screen recordings
- online meetings
- slide-based educational videos
- low-motion lecture videos
- already-compressed videos that need smaller output size

> Current public beta: **VideoX Compressor v1.3.9 Beta - NVENC Runtime Test Fix**

---

<a id="quick-start-en"></a>

## Quick Start for Normal Users

Most users do **not** need to understand every advanced parameter. Start with this stable setup:

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

Then:

1. Select videos.
2. Check the selected file queue.
3. Remove unwanted files using the `X` button.
4. Choose the output folder.
5. Click **Start Compress**.
6. Check the final report after compression.

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

Important notes:

- Each license is generated for one specific device.
- A license for one device will not work on another device.
- Do not publish your `license.key` file.
- Do not include `license.key` inside public ZIP packages.

---

## Why VideoX?

| Feature | Explanation |
|---|---|
| Hardware acceleration | Tries NVIDIA, Intel or AMD hardware encoding when available. |
| Dynamic GPU Preference | Shows only hardware paths that pass real runtime tests. |
| Manual GPU selection | User can choose Auto, NVIDIA, Intel, AMD or CPU when available. |
| Legacy NVIDIA fallback | Can use a legacy NVIDIA FFmpeg build for older NVIDIA driver compatibility. |
| CPU fallback | Uses CPU mode when hardware acceleration is unavailable or unstable. |
| Smart Size Target | Improves size reduction on already-compressed videos. |
| File queue | Shows selected input files before compression. |
| Remove files before start | Each input file can be removed with an `X` button before processing. |
| Output validation | Checks output files and deletes invalid/corrupted partial outputs. |
| Diagnostic reports | Saves useful logs for debugging hardware and FFmpeg issues. |

---

## What is new after v1.2.5?

Version `v1.2.5` introduced General Safe Diagnostics. Newer builds up to `v1.3.9` improved UI stability, compression behavior, hardware selection and NVIDIA compatibility.

| Area | Added / Improved |
|---|---|
| Smart Size Target | Better size reduction for already-compressed or low-bitrate videos. |
| Bitrate analysis | Logs source and output video/audio bitrate. |
| Output validation | Detects invalid, corrupted or incomplete outputs. |
| Cleanup | Deletes failed, cancelled or corrupted output files. |
| GPU Quality slider | GPU quality is controlled with a slider from 18 to 45. |
| CPU CRF slider | CPU quality is controlled with a slider from 18 to 45. |
| Help buttons | `!` buttons explain GPU Quality and CPU CRF. |
| RTL Persian help | Persian help popups are right-to-left. |
| File queue panel | Selected input files are shown clearly before compression. |
| Safe retry | Hardware failures can retry once with CPU fallback. |
| Legacy NVIDIA FFmpeg | Adds `ffmpeg/legacy-nvidia` for older NVIDIA driver compatibility. |
| GPU Preference | User can choose between detected hardware paths. |
| Dynamic GPU filtering | Only hardware options that pass runtime tests are shown. |
| NVENC runtime fix | Fixes NVIDIA being hidden because the internal test frame was too small. |

---

<a id="screenshots-en"></a>

## Screenshots

### License / Device ID Activation

<div align="center">

![VideoX License Activation](screenshots/license.png)

</div>

The activation page shows the Device ID. Send this code on Telegram to receive a device-specific `license.key` file.

### Main Compression Settings

<div align="center">

![VideoX Main Settings](screenshots/english-menu.png)

</div>

The main screen includes output folder, presets, output format, hardware strategy, GPU/CPU quality controls, audio settings and logs.

### File Queue and Removable Input List

<div align="center">

![VideoX File Queue](screenshots/file_selection.png)

</div>

Selected input files are shown in a queue list. Each file has an `X` button so users can remove it before starting compression.

### Progress and Final Report

<div align="center">

![VideoX Compression Report](screenshots/example.png)

</div>

VideoX shows compression progress and then prints a final report with input size, output size, reduction percentage, processing time and file summary.

---

## Real Compression Examples

### Recorded class / screen recording

For low-motion educational videos, VideoX can often reduce file size very aggressively while keeping the output useful for watching, sharing and archiving.

| Original | Compressed | Reduction |
|---:|---:|---:|
| 1.96 GB | About 25 MB | About 98.7% |

### Already-compressed normal video

Already-compressed videos may not shrink dramatically without quality risk. VideoX uses **Smart Size Target** to improve this case.

| Original | Compressed | Reduction |
|---:|---:|---:|
| 236 MB | 112 MB | About 52% |

More aggressive settings may reduce size further, but visible quality loss becomes more likely.

---

<a id="settings-en"></a>

## Simple Settings Guide

### Recommended for most users

```text
Preset: Recorded Class / Screen Recording
Output Format: mp4
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available
Height: 720 or 1080
FPS: 24 or 0
GPU Quality: 32 to 36
CPU CRF: 30 to 34
Audio Bitrate: 32k or 64k
Audio Channels: 1 for speech, 2 for stereo content
```

### For already-compressed videos

```text
Height: keep original height
FPS: 0
GPU Preference: Auto Best Available
GPU Quality: 35 to 40
CPU CRF: 34 to 38
Audio Bitrate: 32k
Audio Channels: 1
Performance Mode: Stable
Processing Strategy: Auto Balanced
Hardware Decode: Off
```

### For gaming or high-motion videos

```text
Preset: Gaming / High Motion
Output Format: mp4
Height: 1080
FPS: 0 or 60
GPU Quality: 26 to 30
CPU CRF: 24 to 28
Audio Bitrate: 64k or 96k
Audio Channels: 2
```

High-motion videos need more bitrate. Very aggressive compression may create visible artifacts.

---

## GPU Preference

VideoX v1.3.9 includes dynamic GPU selection.

Possible options:

```text
Auto Best Available
NVIDIA NVENC
Intel QSV
AMD AMF
CPU Only
```

The exact list depends on the system. VideoX shows only hardware options that pass real runtime tests.

### Dual-GPU / hybrid laptop note

On laptops with integrated graphics plus NVIDIA/AMD dedicated GPU, Windows may route processes differently.

For best results, set these files to **High Performance** in Windows Graphics Settings:

```text
VideoX.exe
ffmpeg/modern/bin/ffmpeg.exe
ffmpeg/legacy-nvidia/bin/ffmpeg.exe
```

NVIDIA Control Panel alone may not always be enough because the actual encoding process is performed by `ffmpeg.exe`.

---

## Quality Controls

### GPU Quality

| Range | Meaning |
|---|---|
| 18 to 25 | Very high quality, larger file |
| 26 to 32 | Balanced quality and size |
| 33 to 36 | Smaller file, good for classes and low-motion videos |
| 37 to 45 | Strong compression, higher quality-loss risk |

Lower value means better quality and larger file. Higher value means smaller file and stronger compression.

### CPU CRF

| Range | Meaning |
|---|---|
| 18 to 24 | High quality, larger file |
| 25 to 30 | Balanced mode |
| 31 to 34 | Smaller file, good for classes and tutorials |
| 35 to 45 | Strong compression, higher quality-loss risk |

CPU CRF matters when VideoX uses CPU fallback or when hardware acceleration is unavailable.

---

<a id="hardware-en"></a>

## Best Settings for Different Systems

### Weak laptop / no dedicated GPU

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced or CPU Only
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: CPU Only or Auto Best Available
Height: 720
FPS: 24 or 0
Output Format: mp4
```

### Intel Iris / Intel integrated graphics

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available or Intel QSV
Output Format: mp4
```

Intel QSV may work well for normal videos, but long already-compressed videos can be more sensitive. If a hardware job fails, VideoX can retry with CPU fallback.

### NVIDIA GTX / RTX

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available or NVIDIA NVENC
Output Format: mp4
```

For old NVIDIA drivers, VideoX can try `ffmpeg/legacy-nvidia` when modern NVENC fails and the legacy runtime test passes.

### AMD Radeon

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available or AMD AMF
Output Format: mp4
```

---

## Diagnostic Logs and Bug Reports

If an error happens, VideoX can save diagnostic information that helps identify the problem.

Reports may include:

- app version
- local and UTC timestamp
- Windows and system information
- FFmpeg and FFprobe paths
- modern FFmpeg path
- legacy NVIDIA FFmpeg path
- available encoders
- runtime encoder test results
- NVIDIA driver information
- selected GPU Preference
- selected encoder
- FFmpeg profile used
- current input file
- FFmpeg error output
- UI log

Default log folder:

```text
C:\Users\<User>\AppData\Local\TheLouisMahdi\VideoXCompressor\logs
```

Use **Open Logs** or **Export Bug Report** when reporting a problem.

---

## Technical Overview

| Component | Role |
|---|---|
| FFmpeg | Main compression engine. |
| FFprobe | Reads video metadata such as FPS, resolution, bitrate, codec and duration. |
| NVIDIA NVENC | NVIDIA hardware encoder used when runtime tests pass. |
| Intel QSV | Intel Quick Sync hardware path used when runtime tests pass. |
| AMD AMF | AMD hardware encoder path used when runtime tests pass. |
| CPU fallback | Used when hardware acceleration is unavailable or unstable. |
| Modern FFmpeg | Main FFmpeg profile for normal systems. |
| Legacy NVIDIA FFmpeg | Fallback FFmpeg profile for older NVIDIA driver compatibility. |
| H.265 / HEVC | Main compression codec for strong size reduction in MP4/MKV/MOV outputs. |
| H.264 | Compatibility-focused codec when HEVC is unavailable or unsuitable. |
| VP9 / Opus | Used for WEBM output. |

For general use, **MP4** is recommended.

---

## Download & Installation

Download the latest ZIP package from the **Releases** section.

Recommended package name:

```text
VideoX_Compressor_v1.3.9_Beta_NVENC_Runtime_Test_Fix.zip
```

Extract the ZIP file and run:

```text
VideoX.exe
```

Required folder structure:

```text
VideoX_Compressor_v1.3.9_Beta_NVENC_Runtime_Test_Fix/
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

Do not delete these folders:

```text
ffmpeg/
_internal/
```

Do not include `license.key` in the public ZIP package.

---

## Beta Status

VideoX Compressor is currently in **Beta**. It is usable and actively tested, but it is still being improved toward a more polished commercial-level release.

Current development focus:

- better results on recorded classes and low-motion videos
- better behavior for already-compressed videos
- better compatibility with Intel, NVIDIA and AMD systems
- safer retry and fallback behavior
- clearer UI for non-technical users
- more accurate progress and final reports
- better high-motion presets
- continuous feedback from testers and real users

---

<a id="persian"></a>

<div dir="rtl" align="right">

# 🇮🇷 فارسی

## معرفی برنامه

**ویدیو ایکس کامپرسور** یک نرم‌افزار ویندوزی برای فشرده‌سازی ویدیو است. هدف برنامه این است که کاربر بدون درگیر شدن با دستورهای پیچیده، بتواند فایل‌های ویدیویی سنگین را به خروجی کم‌حجم‌تر تبدیل کند.

تمرکز اصلی برنامه روی فشرده‌سازی شتاب‌داده‌شده با سخت‌افزار است. برنامه تلاش می‌کند بهترین مسیر پردازش موجود روی همان سیستم را انتخاب کند. بسته به سخت‌افزار و درایور، ممکن است از مسیرهای انویدیا، اینتل، ای‌ام‌دی یا حالت پردازنده استفاده شود.

بهترین کاربرد فعلی برنامه برای ویدیوهای کم‌تحرک است؛ مثل کلاس ضبط‌شده، آموزش، جلسه آنلاین، اسکرین‌ریکورد و ویدیوهای پاورپوینتی.

> نسخه فعلی بتا: **VideoX Compressor v1.3.9 Beta - NVENC Runtime Test Fix**

---

## شروع سریع برای کاربر عادی

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

بعد:

1. ویدیوها را انتخاب کنید.
2. لیست فایل‌های انتخاب‌شده را بررسی کنید.
3. اگر فایل اشتباهی انتخاب شده بود، با دکمه `X` آن را حذف کنید.
4. پوشه خروجی را انتخاب کنید.
5. روی شروع فشرده‌سازی بزنید.
6. در پایان، گزارش نهایی را بررسی کنید.

---

## آموزش فعال‌سازی

1. فایل `VideoX.exe` را اجرا کنید.
2. در صفحه فعال‌سازی، کد دستگاه را کپی کنید.
3. کد دستگاه را در تلگرام به آیدی زیر ارسال کنید.

```text
@thelouis_mahdi
```

4. بعد از بررسی، فایل مخصوص همان دستگاه را دریافت می‌کنید.
5. فایل لایسنس را کنار فایل اجرایی برنامه قرار دهید یا از داخل برنامه انتخاب کنید.
6. روی دکمه بررسی دوباره بزنید.
7. وارد برنامه شوید.

نکات مهم:

- هر فایل لایسنس فقط برای یک دستگاه ساخته می‌شود.
- لایسنس یک دستگاه روی دستگاه دیگر فعال نمی‌شود.
- فایل لایسنس خود را عمومی منتشر نکنید.
- فایل `license.key` را داخل بسته عمومی قرار ندهید.

---

## تغییرات مهم بعد از نسخه 1.2.5

| بخش | تغییرات |
|---|---|
| Smart Size Target | عملکرد بهتر برای ویدیوهایی که از قبل کم‌حجم یا فشرده هستند. |
| بررسی خروجی | خروجی با اطلاعات ویدیویی بررسی می‌شود تا فایل خراب تشخیص داده شود. |
| پاک‌سازی خروجی خراب | فایل ناقص، خراب یا کنسل‌شده پاک می‌شود. |
| اسلایدر کیفیت گرافیکی | مقدار کیفیت GPU با نوار قابل تغییر است. |
| اسلایدر کیفیت پردازنده | مقدار CPU CRF با نوار قابل تغییر است. |
| دکمه راهنما | کنار کیفیت GPU و CPU دکمه `!` برای توضیح ساده اضافه شده است. |
| متن فارسی راست‌به‌چپ | توضیحات فارسی راهنما راست‌چین و راست‌به‌چپ شده‌اند. |
| لیست فایل‌های ورودی | فایل‌های انتخاب‌شده داخل پنل مشخص نمایش داده می‌شوند. |
| تلاش دوباره امن | اگر پردازش سخت‌افزاری خطا بدهد، برنامه یک بار با پردازنده دوباره تلاش می‌کند. |
| FFmpeg لگسی انویدیا | برای سازگاری بهتر با درایورهای قدیمی‌تر انویدیا اضافه شده است. |
| GPU Preference | کاربر می‌تواند مسیر پردازش را انتخاب کند. |
| فیلتر پویا GPU | فقط گزینه‌هایی نمایش داده می‌شوند که تست واقعی را پاس کنند. |
| اصلاح تست NVENC | مشکل پنهان شدن اشتباه NVIDIA به دلیل کوچک بودن فریم تست اصلاح شد. |

---

## اسکرین‌شات‌ها

### صفحه فعال‌سازی و کد دستگاه

<div align="center">

![صفحه فعال‌سازی و کد دستگاه](screenshots/license.png)

</div>

### صفحه اصلی تنظیمات

<div align="center">

![صفحه اصلی تنظیمات](screenshots/english-menu.png)

</div>

### لیست فایل‌های انتخاب‌شده

<div align="center">

![لیست فایل‌های انتخاب‌شده](screenshots/file_selection.png)

</div>

### گزارش پیشرفت و خروجی نهایی

<div align="center">

![گزارش پیشرفت و خروجی نهایی](screenshots/example.png)

</div>

---

## راهنمای تنظیمات ساده

### حالت پیشنهادی برای بیشتر کاربران

```text
Preset: Recorded Class / Screen Recording
Output Format: mp4
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available
Height: 720 or 1080
FPS: 24 or 0
GPU Quality: 32 to 36
CPU CRF: 30 to 34
Audio Bitrate: 32k or 64k
Audio Channels: 1 for speech, 2 for stereo content
```

### برای ویدیوهای از قبل فشرده‌شده

```text
Height: keep original height
FPS: 0
GPU Preference: Auto Best Available
GPU Quality: 35 to 40
CPU CRF: 34 to 38
Audio Bitrate: 32k
Audio Channels: 1
Performance Mode: Stable
Processing Strategy: Auto Balanced
Hardware Decode: Off
```

---

## راهنمای GPU Preference

برنامه در نسخه v1.3.9 فقط گزینه‌هایی را نشان می‌دهد که تست واقعی زمان اجرا را پاس کنند.

گزینه‌های ممکن:

```text
Auto Best Available
NVIDIA NVENC
Intel QSV
AMD AMF
CPU Only
```

روی لپتاپ‌های دو گرافیکه، بهتر است این فایل‌ها را در Windows Graphics Settings روی High Performance قرار دهید:

```text
VideoX.exe
ffmpeg/modern/bin/ffmpeg.exe
ffmpeg/legacy-nvidia/bin/ffmpeg.exe
```

تنظیم NVIDIA Control Panel به‌تنهایی همیشه کافی نیست، چون پردازش اصلی توسط `ffmpeg.exe` انجام می‌شود.

---

## راهنمای کیفیت

### کیفیت GPU

| بازه | معنی |
|---|---|
| 18 تا 25 | کیفیت بسیار بالا، حجم بیشتر |
| 26 تا 32 | تعادل بین کیفیت و حجم |
| 33 تا 36 | حجم کمتر، مناسب کلاس و ویدیوهای کم‌تحرک |
| 37 تا 45 | فشرده‌سازی شدیدتر، احتمال افت کیفیت بیشتر |

### کیفیت CPU

| بازه | معنی |
|---|---|
| 18 تا 24 | کیفیت بالا، حجم بیشتر |
| 25 تا 30 | حالت متعادل |
| 31 تا 34 | حجم کمتر، مناسب کلاس و آموزش |
| 35 تا 45 | فشرده‌سازی شدیدتر، احتمال افت کیفیت بیشتر |

---

## بهترین تنظیمات برای سیستم‌های مختلف

### لپتاپ ضعیف یا بدون کارت گرافیک مجزا

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced or CPU Only
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: CPU Only or Auto Best Available
Height: 720
FPS: 24 or 0
Output Format: mp4
```

### لپتاپ با گرافیک داخلی اینتل

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available or Intel QSV
Output Format: mp4
```

### سیستم دارای کارت گرافیک انویدیا

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available or NVIDIA NVENC
Output Format: mp4
```

### سیستم دارای کارت گرافیک ای‌ام‌دی

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
GPU Preference: Auto Best Available or AMD AMF
Output Format: mp4
```

---

## لاگ‌ها و گزارش خطا

اگر خطا رخ دهد، برنامه می‌تواند گزارش عیب‌یابی ذخیره کند.

گزارش می‌تواند شامل این موارد باشد:

- نسخه برنامه
- تاریخ و ساعت
- اطلاعات ویندوز و سیستم
- مسیر FFmpeg مدرن
- مسیر FFmpeg لگسی انویدیا
- شتاب‌دهنده‌های موجود
- نتیجه تست زمان اجرای شتاب‌دهنده‌ها
- نسخه درایور انویدیا
- GPU Preference انتخاب‌شده
- شتاب‌دهنده انتخاب‌شده
- پروفایل FFmpeg استفاده‌شده
- فایل ورودی فعلی
- خطای پردازش
- لاگ برنامه

محل پیش‌فرض لاگ‌ها:

```text
C:\Users\<User>\AppData\Local\TheLouisMahdi\VideoXCompressor\logs
```

---

## نصب و اجرا

از بخش Releases آخرین نسخه را دانلود کنید.

نام پیشنهادی بسته:

```text
VideoX_Compressor_v1.3.9_Beta_NVENC_Runtime_Test_Fix.zip
```

بعد از خارج کردن از حالت فشرده، این فایل را اجرا کنید:

```text
VideoX.exe
```

ساختار لازم پوشه‌ها:

```text
VideoX_Compressor_v1.3.9_Beta_NVENC_Runtime_Test_Fix/
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

پوشه‌های `ffmpeg` و `_internal` را حذف نکنید.

---

## وضعیت بتا

برنامه در حال حاضر در وضعیت بتا قرار دارد. برنامه قابل استفاده است، اما هنوز در حال توسعه و بهبود برای رسیدن به یک محصول کامل‌تر است.

تمرکز فعلی توسعه:

- نتیجه بهتر روی کلاس‌های ضبط‌شده و ویدیوهای کم‌تحرک
- عملکرد بهتر روی ویدیوهای از قبل فشرده‌شده
- سازگاری بهتر با سیستم‌های اینتل، انویدیا و ای‌ام‌دی
- انتخاب دقیق‌تر مسیر GPU در لپتاپ‌های دو گرافیکه
- تلاش دوباره و بازگشت امن‌تر هنگام خطا
- رابط کاربری ساده‌تر برای کاربران غیرتخصصی
- گزارش دقیق‌تر پیشرفت و پایان کار
- دریافت بازخورد از تسترها و کاربران واقعی

</div>

---

<div align="center">

### Code, design and development by **The Louis Mahdi**

**Telegram:** `@thelouis_mahdi`

</div>
