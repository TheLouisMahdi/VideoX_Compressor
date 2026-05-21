<div align="center">

# 🎬 VideoX Compressor

### GPU-accelerated Windows video compression for recorded classes, tutorials, screen recordings and everyday videos.

<p>
  <a href="#english">English</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#real-compression-example">Real Compression Test</a> •
  <a href="#presets">Presets</a> •
  <a href="#parameter-ranges">Parameter Ranges</a> •
  <a href="#license-activation">License</a> •
  <a href="#فارسی">فارسی</a>
</p>

![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![FFmpeg](https://img.shields.io/badge/Engine-FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)
![GPU](https://img.shields.io/badge/Acceleration-NVIDIA%20NVENC-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![HEVC](https://img.shields.io/badge/Codec-H.265%20%2F%20HEVC-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Beta-blue?style=for-the-badge)
![Activation](https://img.shields.io/badge/License-Device%20ID-blueviolet?style=for-the-badge)

**Designed and developed by The Louis Mahdi**  
**Telegram:** `@thelouis_mahdi`

</div>

---

<a id="english"></a>

## 🇬🇧 English

### What is VideoX Compressor?

**VideoX Compressor** is a Windows video compression application built to make heavy video files much smaller through a simple graphical interface.

The main focus of the project is **hardware-accelerated compression**. When a supported NVIDIA GPU is available, VideoX uses **NVIDIA NVENC** to offload video encoding work from the CPU to the GPU. This makes compression much faster than typical CPU-only workflows and is especially useful on laptops and PCs with NVIDIA graphics cards.

The strongest current use case is **low-motion video**, such as:

- recorded classes
- screen recordings
- tutorials
- online meetings
- slide-based educational videos
- university lecture recordings

For this type of content, VideoX can produce a **dramatic file-size reduction** while keeping the output highly usable for watching, sharing and archiving.

> VideoX is currently a **Beta product**. It is usable and actively tested, but it is still improving toward a more polished commercial-level release.

---

<a id="value"></a>

## 🚀 Why VideoX?

| Advantage | Explanation |
|---|---|
| GPU acceleration | Uses NVIDIA NVENC hardware encoding when available. |
| Very fast on supported GPUs | Encoding can be much faster than CPU-only compression. |
| Huge reduction on low-motion videos | Especially strong for classes, tutorials and screen recordings. |
| Simple workflow | Select videos, choose preset, select output folder, compress. |
| Ready presets | Built-in modes for class recordings, balanced use, gaming, movies and social media. |
| Editable settings | Presets apply recommended values, but users can still adjust parameters manually. |
| Progress and final report | Shows progress, output size, reduction percentage and real processing time. |
| Device-based activation | License is connected to the user device by Device ID. |

---

<a id="latest-beta"></a>

## 🆕 Important Changes in the Latest Beta

Compared with the earlier builds, the latest beta adds the most important product-level improvements:

| Area | Added / Improved |
|---|---|
| UI stability | Resizable window, scrollable settings panel, resizable log area and mouse-wheel scrolling. |
| Queue safety | Files and settings are locked while compression is running to prevent queue bugs. |
| Hidden FFmpeg window | FFmpeg and FFprobe run without opening a visible CMD window. |
| Progress tracking | Current-file progress bar, total progress bar and controlled progress logs. |
| Final report | English report with input size, output size, reduction percentage, success/fail count and output folder. |
| Better errors | Clearer English FFmpeg error messages with possible fixes. |
| Ready presets | Class Recording, Balanced, Gaming / High Motion, Movie / Cinematic, Social Media / Ultra Small. |
| Save settings | Saves language, preset, output folder, window size and custom settings. |
| Cancel support | Compression can be stopped from inside the UI. |
| ffprobe metadata | Reads FPS, resolution, codec and duration for better reporting and warnings. |
| Disk check | Warns if the output drive may not have enough free space. |
| Log tools | Clear Log, Save Log and automatic log saving. |

---

<a id="screenshots"></a>

## 📸 Screenshots

Upload the screenshots inside the `screenshots/` folder with these exact names:

| Screenshot | File name |
|---|---|
| License / Device ID page | `screenshots/videox-license-activation.png` |
| Main settings page | `screenshots/videox-main-settings.png` |
| Preset dropdown page | `screenshots/videox-presets.png` |
| Progress and final report page | `screenshots/videox-progress-report.png` |
| Real class compression comparison | `screenshots/class_compression_example.jpg` |
| GPU usage benchmark | `screenshots/gpu_usage.png` |

### License / Device ID Activation

<div align="center">

![VideoX License Activation](screenshots/videox-license-activation.png)

</div>

The activation page shows the user Device ID. The user sends this code on Telegram and receives a device-specific `license.key` file.

### Main Compression Interface

<div align="center">

![VideoX Main Settings](screenshots/videox-main-settings.png)

</div>

The main interface includes video selection, output folder, ready presets, output format, compression parameters and the log area.

### Ready Presets

<div align="center">

![VideoX Presets](screenshots/videox-presets.png)

</div>

Presets make the program easier for non-technical users. They apply recommended settings automatically, while still allowing manual changes.

### Progress and Final Report

<div align="center">

![VideoX Progress Report](screenshots/videox-progress-report.png)

</div>

VideoX shows progress, real processing time, total input size, total output size and reduction percentage.

### GPU Acceleration in Action

<div align="center">

![GPU Usage](screenshots/gpu_usage.png)

</div>

In testing, VideoX used an **NVIDIA GeForce GTX 1650 Ti** and pushed the GPU video encode engine close to full usage. This demonstrates the accelerator-based design of the app.

---

<a id="real-compression-example"></a>

## 📉 Real Compression Example

### Recorded Class Compression Test

<div align="center">

![Class Compression Example](screenshots/class_compression_example.jpg)

</div>

This test was performed on a recorded class video.

| Item | Size |
|---|---:|
| Original recorded class video | 1.96 GB |
| Compressed output | 25 MB |
| Approximate reduction | ~98.7% |

This type of result is most realistic for low-motion content such as recorded lectures, tutorials, screen recordings, online meetings and slide-based videos.

---

<a id="presets"></a>

## 🎛️ Ready Presets

VideoX includes ready-made modes for different video types. Presets apply suggested values automatically, but the output format and parameters remain editable.

### 1. Recorded Class / Screen Recording

Best for recorded classes, tutorials, meetings and low-motion videos.

```text
Workers: 1
Height: 720 or 1080
FPS: 24
Output Format: mp4
GPU Quality: 32
CPU CRF: 30
Audio Bitrate: 32k
Audio Channels: 1
```

### 2. Balanced

General-purpose mode when you are not sure which preset to choose.

```text
Workers: 1
Height: 1080
FPS: 0
Output Format: mp4
GPU Quality: 30
CPU CRF: 28
Audio Bitrate: 64k
Audio Channels: 2
```

### 3. Gaming / High Motion

Designed for gameplay, fast camera movement and motion-heavy videos.

```text
Workers: 1
Height: 1080
FPS: 0 or 60
Output Format: mp4
GPU Quality: 28
CPU CRF: 25
Audio Bitrate: 64k
Audio Channels: 2
```

### 4. Movie / Cinematic

Better for videos where visual detail preservation matters more than extreme compression.

```text
Workers: 1
Height: 1080
FPS: 0 or 24
Output Format: mp4
GPU Quality: 27
CPU CRF: 24
Audio Bitrate: 96k
Audio Channels: 2
```

### 5. Social Media / Ultra Small

Best when the smallest possible output size is the priority.

```text
Workers: 1
Height: 480
FPS: 24
Output Format: mp4
GPU Quality: 35
CPU CRF: 33
Audio Bitrate: 24k
Audio Channels: 1
```

---

<a id="parameter-ranges"></a>

## 📏 Parameter Ranges

| Parameter | Allowed / Recommended Range | Meaning |
|---|---|---|
| Workers | 1 to 4 | Number of simultaneous jobs. In GPU mode, VideoX may force Workers to 1 for stability. |
| Height | 144 or higher | Output video height. Common values: 480, 720, 1080. |
| FPS | 0 or higher | `0` keeps the original FPS. 24 is good for classes; 30/60 is better for high-motion videos. |
| Output Format | mp4, mkv, mov, webm, avi | MP4 is recommended for general use. |
| GPU Quality | 18 to 45 | Lower number = better quality and larger file. Higher number = smaller file and lower quality. |
| CPU CRF | 18 to 45 | Lower number = better quality and larger file. Higher number = smaller file and lower quality. |
| Audio Bitrate | 24k, 32k, 64k, 96k, etc. | Higher value gives better audio quality and larger size. |
| Audio Channels | 1 or 2 | `1` = mono, `2` = stereo. |

### Quick Guide

```text
GPU Quality:
26 = High Quality
28 = Balanced
30 = Compressed
32 = Heavy Compression
35 = Ultra Small Size

CPU CRF:
22-24 = High Quality
25-28 = Balanced
30+ = Heavy Compression

FPS:
0 = Keep original FPS
24 = Classes / tutorials / low-motion videos
30 = General videos
60 = Gaming / fast motion

Height:
1080 = High Quality
720 = Balanced
480 = Ultra Small Size

Audio:
32k mono = Smallest Size
64k stereo = Better Quality
96k stereo = Movies / Music
```

---

<a id="technical"></a>

## ⚙️ Technical Overview

VideoX is built as a Windows GUI application around FFmpeg and FFprobe.

| Component | Role |
|---|---|
| FFmpeg | Main compression engine. |
| FFprobe | Reads video metadata such as FPS, resolution, codec and duration. |
| NVIDIA NVENC | GPU hardware encoder used for faster MP4/MKV/MOV compression when available. |
| CPU fallback | Used automatically when NVENC is not available or when the selected format requires CPU mode. |
| H.265 / HEVC | Main compression codec for strong size reduction in MP4/MKV/MOV outputs. |
| VP9 / Opus | Used for WEBM output. |

### GPU / CPU Behavior

| Output Format | Processing Mode |
|---|---|
| MP4 | GPU if NVIDIA NVENC is available, otherwise CPU |
| MKV | GPU if NVIDIA NVENC is available, otherwise CPU |
| MOV | GPU if NVIDIA NVENC is available, otherwise CPU |
| WEBM | CPU mode |
| AVI | GPU/CPU depending on available encoder |

For general use, **MP4** is recommended.

---

<a id="download"></a>

## 📦 Download & Installation

Go to the **Releases** section and download the latest ZIP package.

```text
VideoX_Compressor_v1.x_Beta.zip
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

---

<a id="license-activation"></a>

## 🔐 How to Get a License

VideoX uses a **Device ID based license system**.

### Steps

1. Open `VideoX.exe`.
2. Copy the Device ID shown on the activation page.
3. Send the Device ID on Telegram to:

```text
@thelouis_mahdi
```

4. After verification, you will receive a `license.key` file.
5. Place `license.key` next to `VideoX.exe`, or select it from inside the app.
6. Click **Recheck**.
7. Enter the program.

The license is device-specific and works only on the registered device.

---

<a id="usage"></a>

## 🚀 How to Use

1. Download and extract the ZIP file.
2. Run `VideoX.exe`.
3. Activate the software using `license.key`.
4. Select videos or drag and drop them into the app.
5. Choose an output folder.
6. Select a ready preset or edit settings manually.
7. Choose the output format.
8. Click **Start Compress**.
9. Watch progress in the UI.
10. Read the final report in the log.

---

<a id="beta-status"></a>

## 🧪 Beta Status

VideoX Compressor is currently in **Beta**. It is not yet a fully polished commercial product, but it is actively moving in that direction.

Current focus:

- best results on recorded classes and low-motion educational videos
- better stability for batch processing
- better high-motion presets
- improved UI/UX
- more accurate ETA calculation
- continuous feedback from testers and real users

As the developer, I stay in direct contact with testers and users to collect feedback, fix bugs and improve the application over time.

---

<a id="فارسی"></a>

# 🇮🇷 فارسی

## VideoX Compressor چیست؟

**VideoX Compressor** یک نرم‌افزار ویندوزی برای فشرده‌سازی ویدیو است که بدون نیاز به نوشتن دستورهای پیچیده FFmpeg، حجم فایل‌های ویدیویی را کاهش می‌دهد.

تمرکز اصلی VideoX روی **فشرده‌سازی شتاب‌داده‌شده با سخت‌افزار** است. اگر سیستم کارت گرافیک NVIDIA مناسب داشته باشد، برنامه از **NVIDIA NVENC** استفاده می‌کند تا پردازش ویدیو از CPU به GPU منتقل شود. این کار می‌تواند فشرده‌سازی را نسبت به حالت CPU-only بسیار سریع‌تر کند.

بهترین کاربرد فعلی VideoX برای ویدیوهای کم‌تحرک است، مثل:

- کلاس ضبط‌شده
- اسکرین‌ریکورد
- آموزش
- جلسه آنلاین
- ویدیوهای پاورپوینتی
- ضبط‌های درسی دانشگاهی

در این نوع ویدیوها، VideoX می‌تواند **کاهش حجم چشمگیر** ایجاد کند و خروجی همچنان برای مشاهده، ارسال و آرشیو قابل استفاده باقی بماند.

> VideoX در حال حاضر یک **محصول بتا** است. قابل استفاده و در حال تست است، اما هنوز در مسیر تبدیل شدن به یک محصول تجاری کامل‌تر قرار دارد.

---

## چرا VideoX؟

| مزیت | توضیح |
|---|---|
| شتاب‌دهی GPU | در صورت وجود کارت NVIDIA مناسب، از NVENC استفاده می‌کند. |
| سرعت بالا روی GPU | فشرده‌سازی می‌تواند بسیار سریع‌تر از حالت CPU-only باشد. |
| کاهش حجم شدید روی ویدیوهای کم‌تحرک | مخصوصاً برای کلاس، آموزش و اسکرین‌ریکورد بسیار مناسب است. |
| کاربری ساده | انتخاب ویدیو، انتخاب Preset، انتخاب خروجی و شروع فشرده‌سازی. |
| حالت‌های آماده | حالت آماده برای کلاس، متعادل، گیمینگ، فیلم و شبکه اجتماعی دارد. |
| تنظیمات قابل تغییر | Preset فقط مقدار پیشنهادی می‌دهد و کاربر همچنان می‌تواند تنظیمات را تغییر دهد. |
| گزارش و پیشرفت | درصد پیشرفت، حجم خروجی، درصد کاهش حجم و زمان واقعی نمایش داده می‌شود. |
| فعال‌سازی دستگاهی | لایسنس بر اساس Device ID همان دستگاه فعال می‌شود. |

---

## تغییرات مهم نسخه جدید

| بخش | تغییرات اضافه‌شده یا بهبودیافته |
|---|---|
| پایداری رابط کاربری | پنجره قابل تغییر اندازه، بخش تنظیمات اسکرول‌دار، لاگ قابل تغییر اندازه و اسکرول با موس. |
| امنیت صف پردازش | هنگام فشرده‌سازی، فایل‌ها و تنظیمات قفل می‌شوند تا صف پردازش خراب نشود. |
| حذف پنجره CMD | FFmpeg و FFprobe دیگر پنجره CMD جدا باز نمی‌کنند. |
| نمایش پیشرفت | Progress Bar برای فایل جاری، کل عملیات و لاگ کنترل‌شده پیشرفت اضافه شد. |
| گزارش نهایی | گزارش انگلیسی شامل حجم ورودی، حجم خروجی، درصد کاهش، موفق/ناموفق و مسیر خروجی اضافه شد. |
| خطاهای بهتر | خطاهای FFmpeg واضح‌تر شدند و پیشنهاد رفع مشکل نمایش داده می‌شود. |
| Presetهای آماده | کلاس، متعادل، گیمینگ، فیلم و شبکه اجتماعی اضافه شدند. |
| ذخیره تنظیمات | زبان، Preset، مسیر خروجی، اندازه پنجره و تنظیمات سفارشی ذخیره می‌شوند. |
| توقف پردازش | فشرده‌سازی از داخل UI قابل توقف است. |
| خواندن اطلاعات ویدیو | FPS، رزولوشن، کدک و مدت ویدیو با ffprobe خوانده می‌شود. |
| بررسی فضای دیسک | اگر فضای خروجی کم باشد، برنامه هشدار می‌دهد. |
| ابزار لاگ | پاک کردن لاگ، ذخیره لاگ و ذخیره خودکار لاگ اضافه شد. |

---

## اسکرین‌شات‌ها

عکس‌ها را داخل پوشه `screenshots/` با این نام‌ها آپلود کنید:

| عکس | نام فایل |
|---|---|
| صفحه لایسنس و Device ID | `screenshots/videox-license-activation.png` |
| صفحه اصلی تنظیمات | `screenshots/videox-main-settings.png` |
| منوی Presetها | `screenshots/videox-presets.png` |
| صفحه پیشرفت و گزارش نهایی | `screenshots/videox-progress-report.png` |
| نمونه واقعی فشرده‌سازی کلاس | `screenshots/class_compression_example.jpg` |
| تست استفاده از GPU | `screenshots/gpu_usage.png` |

---

## نمونه واقعی فشرده‌سازی کلاس

```text
حجم فایل اصلی: 1.96 GB
حجم فایل خروجی: 25 MB
کاهش حجم تقریبی: 98.7%
```

این نتیجه بیشتر برای ویدیوهای کم‌تحرک مثل کلاس، آموزش، جلسه، اسکرین‌ریکورد و ویدیوهای پاورپوینتی قابل دستیابی است.

---

## حالت‌های آماده

VideoX چند حالت آماده دارد. هر حالت مقدارهای پیشنهادی را اعمال می‌کند، اما کاربر همچنان می‌تواند فرمت خروجی و پارامترها را تغییر دهد.

### 1. کلاس / اسکرین‌ریکورد

مناسب کلاس ضبط‌شده، آموزش، جلسه و ویدیوهای کم‌تحرک.

```text
Workers: 1
Height: 720 یا 1080
FPS: 24
Output Format: mp4
GPU Quality: 32
CPU CRF: 30
Audio Bitrate: 32k
Audio Channels: 1
```

### 2. متعادل

مناسب استفاده عمومی وقتی نمی‌دانید کدام حالت بهتر است.

```text
Workers: 1
Height: 1080
FPS: 0
Output Format: mp4
GPU Quality: 30
CPU CRF: 28
Audio Bitrate: 64k
Audio Channels: 2
```

### 3. گیمینگ / ویدیو پرتحرک

مناسب گیم‌پلی، حرکت سریع دوربین و ویدیوهای motion بالا.

```text
Workers: 1
Height: 1080
FPS: 0 یا 60
Output Format: mp4
GPU Quality: 28
CPU CRF: 25
Audio Bitrate: 64k
Audio Channels: 2
```

### 4. فیلم / سینمایی

مناسب وقتی حفظ جزئیات تصویر مهم‌تر از کوچک‌ترین حجم ممکن است.

```text
Workers: 1
Height: 1080
FPS: 0 یا 24
Output Format: mp4
GPU Quality: 27
CPU CRF: 24
Audio Bitrate: 96k
Audio Channels: 2
```

### 5. شبکه اجتماعی / حجم خیلی کم

مناسب وقتی کمترین حجم خروجی اولویت اصلی است.

```text
Workers: 1
Height: 480
FPS: 24
Output Format: mp4
GPU Quality: 35
CPU CRF: 33
Audio Bitrate: 24k
Audio Channels: 1
```

---

## بازه پارامترها

| پارامتر | بازه مجاز / پیشنهادی | توضیح |
|---|---|---|
| Workers | 1 تا 4 | تعداد پردازش همزمان. در حالت GPU ممکن است برای پایداری روی 1 تنظیم شود. |
| Height | 144 به بالا | ارتفاع خروجی. مقدارهای رایج: 480، 720، 1080. |
| FPS | 0 به بالا | مقدار 0 یعنی حفظ FPS اصلی. برای کلاس 24 مناسب است؛ برای ویدیو پرتحرک 30 یا 60 بهتر است. |
| Output Format | mp4, mkv, mov, webm, avi | برای استفاده عمومی mp4 پیشنهاد می‌شود. |
| GPU Quality | 18 تا 45 | عدد کمتر یعنی کیفیت بهتر و حجم بیشتر. عدد بیشتر یعنی حجم کمتر و کیفیت پایین‌تر. |
| CPU CRF | 18 تا 45 | عدد کمتر یعنی کیفیت بهتر و حجم بیشتر. عدد بیشتر یعنی حجم کمتر و کیفیت پایین‌تر. |
| Audio Bitrate | 24k، 32k، 64k، 96k و مشابه | عدد بیشتر یعنی کیفیت صدای بهتر و حجم بیشتر. |
| Audio Channels | 1 یا 2 | مقدار 1 یعنی مونو، مقدار 2 یعنی استریو. |

---

## توضیح فنی

VideoX یک برنامه گرافیکی ویندوزی بر پایه FFmpeg و FFprobe است.

| بخش | نقش |
|---|---|
| FFmpeg | موتور اصلی فشرده‌سازی. |
| FFprobe | خواندن اطلاعات ویدیو مثل FPS، رزولوشن، کدک و مدت. |
| NVIDIA NVENC | encoder سخت‌افزاری GPU برای سرعت بیشتر در خروجی‌های MP4/MKV/MOV. |
| CPU fallback | اگر GPU مناسب وجود نداشته باشد، برنامه با CPU کار می‌کند. |
| H.265 / HEVC | کدک اصلی برای کاهش حجم قوی در خروجی‌های MP4/MKV/MOV. |
| VP9 / Opus | برای خروجی WEBM استفاده می‌شود. |

### رفتار GPU و CPU

| فرمت خروجی | حالت پردازش |
|---|---|
| MP4 | در صورت وجود NVIDIA NVENC با GPU، در غیر این صورت CPU |
| MKV | در صورت وجود NVIDIA NVENC با GPU، در غیر این صورت CPU |
| MOV | در صورت وجود NVIDIA NVENC با GPU، در غیر این صورت CPU |
| WEBM | حالت CPU |
| AVI | بسته به encoder، GPU یا CPU |

برای استفاده عمومی، **MP4** پیشنهاد می‌شود.

---

## نصب و اجرا

از بخش **Releases** آخرین فایل ZIP را دانلود کنید.

```text
VideoX_Compressor_v1.x_Beta.zip
```

فایل ZIP را Extract کنید و اجرا کنید:

```text
VideoX.exe
```

این پوشه‌ها را حذف نکنید:

```text
ffmpeg/
_internal/
```

پوشه FFmpeg باید شامل این فایل‌ها باشد:

```text
ffmpeg/bin/ffmpeg.exe
ffmpeg/bin/ffprobe.exe
```

---

## نحوه دریافت لایسنس

VideoX از سیستم لایسنس بر اساس **Device ID** استفاده می‌کند.

### مراحل

1. فایل `VideoX.exe` را اجرا کنید.
2. در صفحه فعال‌سازی، Device ID را کپی کنید.
3. این کد را در تلگرام به آیدی زیر ارسال کنید:

```text
@thelouis_mahdi
```

4. بعد از بررسی، فایل `license.key` را دریافت می‌کنید.
5. فایل `license.key` را کنار `VideoX.exe` قرار دهید یا از داخل برنامه انتخاب کنید.
6. روی **Recheck** بزنید.
7. وارد برنامه شوید.

لایسنس مخصوص همان دستگاه است و روی دستگاه دیگر فعال نمی‌شود.

---

## نحوه استفاده

1. فایل ZIP را دانلود و Extract کنید.
2. `VideoX.exe` را اجرا کنید.
3. برنامه را با فایل `license.key` فعال کنید.
4. ویدیوها را انتخاب کنید یا داخل برنامه Drag & Drop کنید.
5. پوشه خروجی را انتخاب کنید.
6. یک Preset آماده انتخاب کنید یا تنظیمات را دستی تغییر دهید.
7. فرمت خروجی را انتخاب کنید.
8. روی **Start Compress** بزنید.
9. پیشرفت پردازش را داخل UI ببینید.
10. گزارش نهایی را در Log بررسی کنید.

---

## وضعیت بتا

VideoX Compressor در حال حاضر در وضعیت **Beta** قرار دارد. هنوز یک محصول تجاری کاملاً نهایی‌شده نیست، اما به‌صورت فعال در همین مسیر توسعه پیدا می‌کند.

تمرکز فعلی:

- بهترین نتیجه روی کلاس‌های ضبط‌شده و ویدیوهای کم‌تحرک
- پایداری بهتر برای پردازش چند فایل
- Presetهای بهتر برای ویدیوهای پرتحرک
- بهبود UI/UX
- دقیق‌تر شدن ETA
- دریافت بازخورد مداوم از تسترها و کاربران واقعی

به‌عنوان توسعه‌دهنده، من به‌صورت مستقیم با تسترها و کاربران در ارتباط هستم تا بازخوردها، باگ‌ها و پیشنهادها را جمع‌آوری کنم و برنامه را مرحله‌به‌مرحله بهتر کنم.

---

<div align="center">

### Code, design and development by **The Louis Mahdi**

**Telegram:** `@thelouis_mahdi`

</div>
