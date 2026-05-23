<div align="center">

# 🎬 VideoX Compressor

### Hardware-accelerated Windows video compression for recorded classes, tutorials, screen recordings and everyday videos.

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
![Hardware](https://img.shields.io/badge/Hardware%20Acceleration-NVIDIA%20%7C%20Intel%20%7C%20AMD-76B900?style=for-the-badge)
![Codec](https://img.shields.io/badge/Codec-H.265%20%2F%20H.264%20%2F%20VP9-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Beta-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-Device%20ID-blueviolet?style=for-the-badge)

**Code, design and development by The Louis Mahdi**  
**Telegram:** `@thelouis_mahdi`

</div>

---

<a id="english"></a>

# 🇬🇧 English

## What is VideoX Compressor?

**VideoX Compressor** is a Windows video compression application designed to make large video files much smaller through a simple graphical interface.

The main goal of VideoX is to make compression easier for normal users while still using modern video acceleration when available. Depending on the system, VideoX can try hardware paths such as **NVIDIA NVENC**, **Intel Quick Sync / QSV**, **AMD AMF**, or fall back to CPU mode.

VideoX is especially useful for:

- recorded classes
- screen recordings
- tutorials
- online meetings
- slide-based educational videos
- low-motion lecture videos
- everyday videos that need smaller file size

> Current public beta: **VideoX Compressor v1.3.4 Beta - File Queue & Safe Retry**

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
GPU Quality: 32 to 36
CPU CRF: 30 to 34
```

Then:

1. Select videos.
2. Check the selected file queue.
3. Remove any unwanted file using the `X` button.
4. Choose the output folder.
5. Click **Start Compress**.
6. Read the final report after compression.

---

<a id="activation-en"></a>

## License Activation Guide

VideoX uses a **Device ID based license system**.

### Activation steps

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

### Important license notes

- Each license is generated for one specific device.
- A license for one device will not work on another device.
- Do not publish your `license.key` file.
- If activation fails, send your Device ID and a screenshot of the activation page.

---

## Why VideoX?

| Feature | Explanation |
|---|---|
| Hardware acceleration | Tries to use NVIDIA, Intel or AMD video acceleration when available. |
| CPU fallback | If hardware acceleration fails, VideoX can continue with CPU mode. |
| Smart compression | Can detect already-compressed videos and use smarter size targeting. |
| Simple UI | Select videos, choose preset, choose folder and start compression. |
| File queue | Selected files are shown in a clear list before compression. |
| Remove before start | Each selected file has an `X` button for removing it from the queue. |
| Ready presets | Includes modes for class recordings, balanced use, gaming, movies and social media. |
| Final report | Shows input size, output size, reduction percentage and processing time. |
| Safe retry | If hardware output fails, VideoX can retry once with CPU fallback. |
| Diagnostic logs | General Safe Mode can save useful logs and bug reports. |

---

## What is new after v1.2.5?

Version `v1.2.5` focused on General Safe Diagnostics. Newer builds up to `v1.3.4` add more UI and compression improvements.

| Area | Added / Improved |
|---|---|
| Smart Size Target | Better compression behavior for videos that are already low-bitrate or already compressed. |
| Already-compressed warning | Warns when a source video may not compress much without quality risk. |
| Bitrate analysis | Logs source and output video/audio bitrate. |
| Output validation | Uses video metadata checks to detect invalid or corrupted output files. |
| Failed output cleanup | Deletes failed, incomplete, cancelled or corrupted output files. |
| Log cleanup | Clears old VideoX logs before a new compression session to avoid wasting disk space. |
| GPU Quality slider | GPU quality is now controlled with a slider from 18 to 45. |
| CPU CRF slider | CPU quality is now controlled with a slider from 18 to 45. |
| Help buttons | `!` buttons explain GPU Quality and CPU CRF in a popup. |
| RTL Persian help | Persian help text is right-to-left to avoid mixed text problems. |
| File queue panel | Selected input files are now shown in a clear queue list. |
| Remove file button | Each file in the queue can be removed before compression. |
| Safe hardware retry | If hardware encoding fails, VideoX retries once with CPU fallback. |
| Better final status | Failed jobs no longer show as simply Finished; the app reports errors clearly. |

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

VideoX shows compression progress and then prints a final report with total input size, output size, reduction percentage, processing time and file summary.

---

## Real Compression Examples

### Recorded class / screen recording

For low-motion educational videos, VideoX can often reduce file size very aggressively while keeping the output useful for watching, sharing and archiving.

Example from testing:

| Original | Compressed | Reduction |
|---:|---:|---:|
| 1.96 GB | About 25 MB | About 98.7% |

### Already-compressed normal video

For videos that are already low-bitrate, VideoX may not be able to reduce size dramatically without quality risk. Newer versions use **Smart Size Target** to improve this case.

Example from testing:

| Original | Compressed | Reduction |
|---:|---:|---:|
| 236 MB | 112 MB | About 52% |

When more aggressive settings are used, smaller outputs may be possible, but visible quality loss becomes more likely.

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
GPU Quality: 35 to 40
CPU CRF: 34 to 38
Audio Bitrate: 32k
Audio Channels: 1
Performance Mode: Stable
Processing Strategy: Auto Balanced
Hardware Decode: Off
```

VideoX will try Smart Size Target when it detects an already-compressed source. This aims for a smaller file while avoiding automatic heavy downscaling.

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

## Quality Controls

### GPU Quality

GPU Quality controls compression in hardware-accelerated mode.

| Range | Meaning |
|---|---|
| 18 to 25 | Very high quality, larger file |
| 26 to 32 | Balanced quality and size |
| 33 to 36 | Smaller file, good for classes and low-motion videos |
| 37 to 45 | Strong compression, higher quality-loss risk |

Lower number means better quality and larger file. Higher number means smaller file and stronger compression.

### CPU CRF

CPU CRF controls compression quality in CPU mode.

| Range | Meaning |
|---|---|
| 18 to 24 | High quality, larger file |
| 25 to 30 | Balanced mode |
| 31 to 34 | Smaller file, good for classes and tutorials |
| 35 to 45 | Strong compression, higher quality-loss risk |

CPU CRF matters when VideoX uses CPU fallback or when hardware acceleration is not available.

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
Output Format: mp4
```

Intel Quick Sync / QSV may work well for normal videos, but long already-compressed videos can be more sensitive. If a hardware job fails, VideoX can retry once with CPU fallback.

### NVIDIA GTX / RTX

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
Output Format: mp4
```

For speed testing on stronger NVIDIA systems:

```text
Performance Mode: High Throughput
Processing Strategy: Maximum Hardware Acceleration
Hardware Decode: Aggressive
Workers: 1 or 2
```

If errors happen, return to Stable mode and Hardware Decode Off.

### AMD Radeon

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
Output Format: mp4
```

If AMD AMF is available and stable, VideoX may use it. Otherwise, it falls back to CPU mode.

---

## Diagnostic Logs and Bug Reports

If an error happens, VideoX can save diagnostic information that helps identify the problem.

Reports may include:

- app version
- local and UTC timestamp
- Windows and system information
- FFmpeg and FFprobe paths
- available encoders
- runtime encoder test results
- selected settings
- selected encoder
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

VideoX is built as a Windows GUI application around FFmpeg and FFprobe.

| Component | Role |
|---|---|
| FFmpeg | Main compression engine. |
| FFprobe | Reads video metadata such as FPS, resolution, bitrate, codec and duration. |
| NVIDIA NVENC | NVIDIA hardware encoder used when available. |
| Intel QSV | Intel Quick Sync hardware path used when available. |
| AMD AMF | AMD hardware encoder path used when available. |
| CPU fallback | Used automatically when hardware acceleration is unavailable or unstable. |
| H.265 / HEVC | Main compression codec for strong size reduction in MP4/MKV/MOV outputs. |
| H.264 | Compatibility-focused codec when HEVC is unavailable or not suitable. |
| VP9 / Opus | Used for WEBM output. |

For general use, **MP4** is recommended.

---

## Download & Installation

Download the latest ZIP package from the **Releases** section.

Recommended package name:

```text
VideoX_Compressor_v1.3.4_Beta_File_Queue_Safe_Retry.zip
```

Extract the ZIP file and run:

```text
VideoX.exe
```

Do not delete these folders:

```text
ffmpeg/
_internal/
```

The FFmpeg folder should contain:

```text
ffmpeg/bin/ffmpeg.exe
ffmpeg/bin/ffprobe.exe
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

> نسخه فعلی بتا: **VideoX Compressor v1.3.4 Beta - File Queue & Safe Retry**

---

## شروع سریع برای کاربر عادی

لازم نیست همه پارامترها را بلد باشید. برای شروع از این تنظیمات استفاده کنید:

```text
Preset: Recorded Class / Screen Recording
Output Format: mp4
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
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

برنامه از سیستم لایسنس بر اساس کد دستگاه استفاده می‌کند.

### مراحل فعال‌سازی

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

### نکات مهم لایسنس

- هر فایل لایسنس فقط برای یک دستگاه ساخته می‌شود.
- لایسنس یک دستگاه روی دستگاه دیگر فعال نمی‌شود.
- فایل لایسنس خود را عمومی منتشر نکنید.
- اگر فعال‌سازی مشکل داشت، کد دستگاه و عکس صفحه فعال‌سازی را ارسال کنید.

---

## چرا این برنامه؟

| قابلیت | توضیح |
|---|---|
| شتاب‌دهی سخت‌افزاری | در صورت وجود سخت‌افزار مناسب، پردازش ویدیو با مسیر گرافیکی انجام می‌شود. |
| بازگشت به پردازنده | اگر شتاب‌دهنده سخت‌افزاری خطا بدهد، برنامه می‌تواند با پردازنده ادامه دهد. |
| فشرده‌سازی هوشمند | برای ویدیوهایی که از قبل فشرده شده‌اند، برنامه مسیر مناسب‌تری انتخاب می‌کند. |
| رابط ساده | کاربر فایل را انتخاب می‌کند، حالت آماده را می‌زند و فشرده‌سازی را شروع می‌کند. |
| لیست فایل‌های ورودی | فایل‌های انتخاب‌شده قبل از شروع کار در یک لیست مشخص نمایش داده می‌شوند. |
| حذف فایل از ورودی | کنار هر فایل دکمه `X` وجود دارد تا قبل از شروع حذف شود. |
| گزارش نهایی | حجم قبل و بعد، درصد کاهش حجم و زمان پردازش نمایش داده می‌شود. |
| گزارش خطا | اگر خطا رخ دهد، برنامه می‌تواند گزارش عیب‌یابی ذخیره کند. |

---

## تغییرات مهم بعد از نسخه 1.2.5

| بخش | تغییرات |
|---|---|
| Smart Size Target | عملکرد بهتر برای ویدیوهایی که از قبل کم‌حجم یا فشرده هستند. |
| هشدار فایل فشرده‌شده | اگر ویدیو از قبل بیت‌ریت پایینی داشته باشد، برنامه هشدار می‌دهد. |
| تحلیل بیت‌ریت | بیت‌ریت ویدیو و صدا قبل و بعد از فشرده‌سازی در لاگ نوشته می‌شود. |
| بررسی خروجی | خروجی با اطلاعات ویدیویی بررسی می‌شود تا فایل خراب تشخیص داده شود. |
| پاک‌سازی خروجی خراب | فایل ناقص، خراب یا کنسل‌شده پاک می‌شود. |
| پاک‌سازی لاگ قدیمی | قبل از هر پردازش جدید، لاگ‌های قدیمی پاک می‌شوند. |
| اسلایدر کیفیت گرافیکی | مقدار کیفیت GPU با نوار قابل تغییر است. |
| اسلایدر کیفیت پردازنده | مقدار CPU CRF با نوار قابل تغییر است. |
| دکمه راهنما | کنار کیفیت GPU و CPU دکمه `!` برای توضیح ساده اضافه شده است. |
| متن فارسی راست‌به‌چپ | توضیحات فارسی راهنما راست‌چین و راست‌به‌چپ شده‌اند. |
| لیست فایل‌های ورودی | فایل‌های انتخاب‌شده داخل پنل مشخص نمایش داده می‌شوند. |
| تلاش دوباره امن | اگر پردازش سخت‌افزاری خطا بدهد، برنامه یک بار با پردازنده دوباره تلاش می‌کند. |

---

## اسکرین‌شات‌ها

### صفحه فعال‌سازی و کد دستگاه

<div align="center">

![صفحه فعال‌سازی و کد دستگاه](screenshots/license.png)

</div>

در این صفحه، کد دستگاه نمایش داده می‌شود و کاربر می‌تواند آن را برای دریافت لایسنس ارسال کند.

### صفحه اصلی تنظیمات

<div align="center">

![صفحه اصلی تنظیمات](screenshots/english-menu.png)

</div>

در این صفحه، کاربر می‌تواند مسیر خروجی، حالت آماده، فرمت خروجی، استراتژی پردازش، کیفیت GPU، کیفیت CPU، تنظیمات صدا و لاگ برنامه را ببیند.

### لیست فایل‌های انتخاب‌شده

<div align="center">

![لیست فایل‌های انتخاب‌شده](screenshots/file_selection.png)

</div>

فایل‌های ورودی در یک لیست مشخص نمایش داده می‌شوند و کاربر می‌تواند قبل از شروع فشرده‌سازی، فایل‌های اضافی را حذف کند.

### گزارش پیشرفت و خروجی نهایی

<div align="center">

![گزارش پیشرفت و خروجی نهایی](screenshots/example.png)

</div>

بعد از پایان کار، برنامه حجم ورودی، حجم خروجی، درصد کاهش حجم، زمان پردازش و خلاصه فایل‌ها را نمایش می‌دهد.

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
GPU Quality: 35 to 40
CPU CRF: 34 to 38
Audio Bitrate: 32k
Audio Channels: 1
Performance Mode: Stable
Processing Strategy: Auto Balanced
Hardware Decode: Off
```

برنامه در این حالت تلاش می‌کند حجم را بهتر کم کند، اما اگر ویدیو از قبل خیلی فشرده باشد، کاهش حجم بسیار زیاد بدون افت کیفیت همیشه ممکن نیست.

---

## راهنمای کیفیت

### کیفیت GPU

| بازه | معنی |
|---|---|
| 18 تا 25 | کیفیت بسیار بالا، حجم بیشتر |
| 26 تا 32 | تعادل بین کیفیت و حجم |
| 33 تا 36 | حجم کمتر، مناسب کلاس و ویدیوهای کم‌تحرک |
| 37 تا 45 | فشرده‌سازی شدیدتر، احتمال افت کیفیت بیشتر |

عدد کمتر یعنی کیفیت بهتر و حجم بیشتر. عدد بالاتر یعنی حجم کمتر و فشرده‌سازی شدیدتر.

### کیفیت CPU

| بازه | معنی |
|---|---|
| 18 تا 24 | کیفیت بالا، حجم بیشتر |
| 25 تا 30 | حالت متعادل |
| 31 تا 34 | حجم کمتر، مناسب کلاس و آموزش |
| 35 تا 45 | فشرده‌سازی شدیدتر، احتمال افت کیفیت بیشتر |

کیفیت CPU زمانی مهم‌تر است که برنامه با پردازنده کار کند یا شتاب‌دهنده سخت‌افزاری در دسترس نباشد.

---

## بهترین تنظیمات برای سیستم‌های مختلف

### لپتاپ ضعیف یا بدون کارت گرافیک مجزا

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced or CPU Only
General Safe Mode: On
Hardware Decode: Off
Workers: 1
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
Output Format: mp4
```

روی بعضی سیستم‌های اینتل، ویدیوهای طولانی یا از قبل فشرده‌شده ممکن است حساس‌تر باشند. اگر پردازش سخت‌افزاری خطا بدهد، برنامه یک بار با پردازنده دوباره تلاش می‌کند.

### سیستم دارای کارت گرافیک انویدیا

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
Output Format: mp4
```

برای تست سرعت روی سیستم قوی‌تر:

```text
Performance Mode: High Throughput
Processing Strategy: Maximum Hardware Acceleration
Hardware Decode: Aggressive
Workers: 1 or 2
```

اگر خطا رخ داد، به حالت Stable و Hardware Decode Off برگردید.

### سیستم دارای کارت گرافیک ای‌ام‌دی

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
Output Format: mp4
```

اگر مسیر سخت‌افزاری ای‌ام‌دی فعال و پایدار باشد، برنامه از آن استفاده می‌کند. در غیر این صورت به حالت پردازنده برمی‌گردد.

---

## لاگ‌ها و گزارش خطا

اگر خطا رخ دهد، برنامه می‌تواند گزارش عیب‌یابی ذخیره کند.

گزارش می‌تواند شامل این موارد باشد:

- نسخه برنامه
- تاریخ و ساعت
- اطلاعات ویندوز و سیستم
- مسیر ابزارهای پردازش ویدیو
- شتاب‌دهنده‌های موجود
- نتیجه تست شتاب‌دهنده‌ها
- تنظیمات انتخاب‌شده
- شتاب‌دهنده انتخاب‌شده
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
VideoX_Compressor_v1.3.4_Beta_File_Queue_Safe_Retry.zip
```

بعد از خارج کردن از حالت فشرده، این فایل را اجرا کنید:

```text
VideoX.exe
```

این پوشه‌ها را حذف نکنید:

```text
ffmpeg/
_internal/
```

فایل `license.key` را داخل بسته عمومی منتشر نکنید.

---

## وضعیت بتا

برنامه در حال حاضر در وضعیت بتا قرار دارد. برنامه قابل استفاده است، اما هنوز در حال توسعه و بهبود برای رسیدن به یک محصول کامل‌تر است.

تمرکز فعلی توسعه:

- نتیجه بهتر روی کلاس‌های ضبط‌شده و ویدیوهای کم‌تحرک
- عملکرد بهتر روی ویدیوهای از قبل فشرده‌شده
- سازگاری بهتر با سیستم‌های اینتل، انویدیا و ای‌ام‌دی
- تلاش دوباره و بازگشت امن‌تر هنگام خطا
- رابط کاربری ساده‌تر برای کاربران غیرتخصصی
- گزارش دقیق‌تر پیشرفت و پایان کار
- بهبود حالت‌های آماده برای ویدیوهای پرتحرک
- دریافت بازخورد از تسترها و کاربران واقعی

به عنوان توسعه‌دهنده، من به‌صورت مستقیم با تسترها و کاربران در ارتباط هستم تا مشکلات، باگ‌ها و پیشنهادها را بررسی کنم.

</div>

---

<div align="center">

### Code, design and development by **The Louis Mahdi**

**Telegram:** `@thelouis_mahdi`

</div>
