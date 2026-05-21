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
  <a href="#persian">فارسی</a>
</p>

![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![FFmpeg](https://img.shields.io/badge/Engine-FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)
![GPU](https://img.shields.io/badge/Acceleration-NVIDIA%20NVENC-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![HEVC](https://img.shields.io/badge/Codec-H.265%20%2F%20HEVC-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Beta-blue?style=for-the-badge)
![Activation](https://img.shields.io/badge/License-Device%20ID-blueviolet?style=for-the-badge)

**Code, design and development by The Louis Mahdi**  
**Telegram:** `@thelouis_mahdi`

</div>

---

<a id="english"></a>

## 🇬🇧 English

## What is VideoX Compressor?

**VideoX Compressor** is a Windows video compression application built to make heavy video files much smaller through a simple graphical interface.

The project focuses on **hardware-accelerated compression**. When a supported NVIDIA GPU is available, VideoX uses **NVIDIA NVENC** to move video encoding work from the CPU to the GPU. This can make compression much faster than CPU-only workflows, especially on laptops and PCs with NVIDIA graphics cards.

The strongest current use case is **low-motion video**, including recorded classes, screen recordings, tutorials, online meetings, slide-based educational videos and university lecture recordings.

For this type of content, VideoX can produce a **dramatic file-size reduction** while keeping the output practical for watching, sharing and archiving.

> VideoX is currently a **Beta product**. It is usable and actively tested, but it is still being improved toward a more polished commercial-level release.

---

## Why VideoX?

| Advantage | Explanation |
|---|---|
| GPU acceleration | Uses NVIDIA NVENC hardware encoding when available. |
| Fast processing | On supported GPUs, encoding can be much faster than CPU-only compression. |
| Huge reduction on low-motion videos | Especially strong for classes, tutorials and screen recordings. |
| Simple workflow | Select videos, choose a preset, choose output folder and start compression. |
| Ready presets | Includes modes for classes, balanced use, gaming, movies and social media. |
| Editable settings | Presets apply recommended values, but users can still adjust parameters manually. |
| Progress and final report | Shows progress, output size, reduction percentage and real processing time. |
| Device-based activation | License is connected to the user device by Device ID. |

---

## Important Changes in the Latest Beta

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
| Metadata reading | Reads FPS, resolution, codec and duration for better reporting and warnings. |
| Disk check | Warns if the output drive may not have enough free space. |
| Log tools | Clear Log, Save Log and automatic log saving. |

---

<a id="screenshots"></a>

## Screenshots

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

## Real Compression Example

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

## Ready Presets

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

## Parameter Ranges

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

---

## Technical Overview

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

## Download & Installation

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

## How to Get a License

VideoX uses a **Device ID based license system**.

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

## How to Use

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

## Beta Status

VideoX Compressor is currently in **Beta**. It is not yet a fully polished commercial product, but it is actively moving in that direction.

Current focus:

- best results on recorded classes and low-motion educational videos
- better stability for batch processing
- better high-motion presets
- improved UI and user experience
- more accurate time estimation
- continuous feedback from testers and real users

As the developer, I stay in direct contact with testers and users to collect feedback, fix bugs and improve the application over time.

---

<a id="persian"></a>

<div dir="rtl" align="right">

# 🇮🇷 فارسی

## معرفی برنامه

**ویدیو ایکس کامپرسور** یک نرم‌افزار ویندوزی برای فشرده‌سازی ویدیو است. هدف برنامه این است که کاربر بدون نوشتن دستورهای پیچیده، بتواند فایل‌های ویدیویی سنگین را به خروجی کم‌حجم‌تر تبدیل کند.

تمرکز اصلی برنامه روی فشرده‌سازی شتاب‌داده‌شده با سخت‌افزار است. اگر سیستم کارت گرافیک انویدیا داشته باشد و شتاب‌دهنده مناسب در دسترس باشد، بخش سنگین پردازش ویدیو از پردازنده مرکزی به کارت گرافیک منتقل می‌شود. این موضوع می‌تواند سرعت فشرده‌سازی را نسبت به حالت پردازنده‌محور به شکل قابل توجهی بهتر کند.

بهترین کاربرد فعلی برنامه برای ویدیوهای کم‌تحرک است؛ مثل کلاس ضبط‌شده، آموزش، جلسه آنلاین، اسکرین‌ریکورد و ویدیوهای پاورپوینتی. در این نوع ویدیوها، برنامه می‌تواند کاهش حجم بسیار چشمگیر ایجاد کند و خروجی همچنان برای مشاهده، ارسال و آرشیو مناسب باقی بماند.

> این برنامه فعلاً در وضعیت بتا قرار دارد. برنامه قابل استفاده و در حال تست است، اما هنوز مسیر توسعه آن برای رسیدن به یک محصول تجاری کامل‌تر ادامه دارد.

---

## چرا این برنامه؟

| مزیت | توضیح |
|---|---|
| شتاب‌دهی سخت‌افزاری | در صورت وجود کارت گرافیک مناسب، پردازش ویدیو با شتاب‌دهنده گرافیکی انجام می‌شود. |
| سرعت بالا | روی سیستم‌های دارای کارت گرافیک مناسب، سرعت پردازش می‌تواند بسیار بهتر از حالت پردازنده‌محور باشد. |
| کاهش حجم چشمگیر | برای کلاس، آموزش و اسکرین‌ریکورد بسیار مناسب است. |
| کاربری ساده | کاربر فقط ویدیو را انتخاب می‌کند، حالت آماده را می‌زند، مسیر خروجی را انتخاب می‌کند و فشرده‌سازی را شروع می‌کند. |
| حالت‌های آماده | برای کلاس، حالت متعادل، گیمینگ، فیلم و شبکه اجتماعی تنظیمات آماده وجود دارد. |
| تنظیمات قابل تغییر | حالت‌های آماده فقط مقدار پیشنهادی می‌دهند و کاربر همچنان می‌تواند تنظیمات را تغییر دهد. |
| گزارش نهایی | حجم قبل و بعد، درصد کاهش حجم، زمان واقعی پردازش و وضعیت فایل‌ها نمایش داده می‌شود. |
| فعال‌سازی دستگاهی | لایسنس بر اساس کد دستگاه فعال می‌شود. |

---

## تغییرات مهم نسخه جدید

| بخش | تغییرات اضافه‌شده یا بهبودیافته |
|---|---|
| پایداری رابط کاربری | پنجره قابل تغییر اندازه، بخش تنظیمات اسکرول‌دار، لاگ قابل تغییر اندازه و اسکرول با موس. |
| امنیت صف پردازش | هنگام فشرده‌سازی، فایل‌ها و تنظیمات قفل می‌شوند تا صف پردازش خراب نشود. |
| حذف پنجره مزاحم | ابزارهای پردازش ویدیو دیگر پنجره جداگانه و مزاحم باز نمی‌کنند. |
| نمایش پیشرفت | نوار پیشرفت برای فایل جاری، کل عملیات و گزارش کنترل‌شده پیشرفت اضافه شد. |
| گزارش نهایی | گزارش شامل حجم ورودی، حجم خروجی، درصد کاهش، تعداد موفق و ناموفق و مسیر خروجی است. |
| خطاهای بهتر | خطاها واضح‌تر شده‌اند و برای رفع مشکل پیشنهاد نمایش داده می‌شود. |
| حالت‌های آماده | حالت کلاس، متعادل، گیمینگ، فیلم و شبکه اجتماعی اضافه شده است. |
| ذخیره تنظیمات | زبان، حالت آماده، مسیر خروجی، اندازه پنجره و تنظیمات سفارشی ذخیره می‌شوند. |
| توقف پردازش | فشرده‌سازی از داخل خود برنامه قابل توقف است. |
| خواندن اطلاعات ویدیو | نرخ فریم، رزولوشن، کدک و مدت ویدیو خوانده می‌شود. |
| بررسی فضای دیسک | اگر فضای مسیر خروجی کم باشد، برنامه هشدار می‌دهد. |
| ابزار لاگ | پاک کردن لاگ، ذخیره لاگ و ذخیره خودکار لاگ اضافه شده است. |

---

## اسکرین‌شات‌ها

### صفحه فعال‌سازی و کد دستگاه

<div align="center">

![صفحه فعال‌سازی و کد دستگاه](screenshots/videox-license-activation.png)

</div>

در این صفحه، کد دستگاه نمایش داده می‌شود و کاربر می‌تواند آن را برای دریافت لایسنس ارسال کند.

### صفحه اصلی تنظیمات

<div align="center">

![صفحه اصلی تنظیمات](screenshots/videox-main-settings.png)

</div>

در صفحه اصلی، کاربر می‌تواند ویدیوها، مسیر خروجی، حالت آماده، فرمت خروجی و پارامترهای فشرده‌سازی را انتخاب کند.

### منوی حالت‌های آماده

<div align="center">

![منوی حالت‌های آماده](screenshots/videox-presets.png)

</div>

حالت‌های آماده باعث می‌شوند کاربر بدون درگیر شدن با جزئیات فنی، تنظیمات مناسب را سریع انتخاب کند.

### صفحه پیشرفت و گزارش نهایی

<div align="center">

![صفحه پیشرفت و گزارش نهایی](screenshots/videox-progress-report.png)

</div>

در این بخش، پیشرفت پردازش، زمان واقعی، حجم خروجی و درصد کاهش حجم نمایش داده می‌شود.

---

## نمونه واقعی فشرده‌سازی کلاس

<div align="center">

![نمونه واقعی فشرده‌سازی کلاس](screenshots/class_compression_example.jpg)

</div>

```text
Original file size: 1.96 GB
Compressed file size: 25 MB
Approximate reduction: 98.7%
```

این نتیجه بیشتر برای ویدیوهای کم‌تحرک مثل کلاس، آموزش، جلسه، اسکرین‌ریکورد و ویدیوهای پاورپوینتی قابل دستیابی است.

---

## حالت‌های آماده

برنامه چند حالت آماده دارد. هر حالت مقدارهای پیشنهادی را اعمال می‌کند، اما کاربر همچنان می‌تواند فرمت خروجی و پارامترها را تغییر دهد.

### ۱. کلاس و اسکرین‌ریکورد

مناسب کلاس ضبط‌شده، آموزش، جلسه و ویدیوهای کم‌تحرک.

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

### ۲. حالت متعادل

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

### ۳. گیمینگ و ویدیوهای پرتحرک

مناسب گیم‌پلی، حرکت سریع دوربین و ویدیوهای پرتحرک.

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

### ۴. فیلم و ویدیوهای سینمایی

مناسب زمانی که حفظ جزئیات تصویر مهم‌تر از رسیدن به کمترین حجم ممکن است.

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

### ۵. شبکه اجتماعی و حجم خیلی کم

مناسب زمانی که کمترین حجم خروجی اولویت اصلی است.

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

| پارامتر | بازه مجاز یا پیشنهادی | توضیح |
|---|---|---|
| تعداد پردازش همزمان | ۱ تا ۴ | در حالت شتاب‌دهی گرافیکی، برنامه ممکن است برای پایداری مقدار را روی ۱ نگه دارد. |
| ارتفاع خروجی | ۱۴۴ به بالا | مقدارهای رایج شامل ۴۸۰، ۷۲۰ و ۱۰۸۰ هستند. |
| نرخ فریم | ۰ به بالا | مقدار ۰ یعنی حفظ نرخ فریم اصلی. برای کلاس مقدار ۲۴ مناسب است و برای ویدیوهای پرتحرک مقدار ۳۰ یا ۶۰ بهتر است. |
| فرمت خروجی | `mp4`, `mkv`, `mov`, `webm`, `avi` | برای استفاده عمومی، فرمت `mp4` پیشنهاد می‌شود. |
| کیفیت حالت گرافیکی | ۱۸ تا ۴۵ | عدد کمتر یعنی کیفیت بهتر و حجم بیشتر. عدد بالاتر یعنی حجم کمتر و کیفیت پایین‌تر. |
| کیفیت حالت پردازنده | ۱۸ تا ۴۵ | عدد کمتر یعنی کیفیت بهتر و حجم بیشتر. عدد بالاتر یعنی حجم کمتر و کیفیت پایین‌تر. |
| کیفیت صدا | مثل `24k`, `32k`, `64k`, `96k` | عدد بیشتر یعنی کیفیت صدای بهتر و حجم بیشتر. |
| کانال صدا | ۱ یا ۲ | مقدار ۱ یعنی مونو و مقدار ۲ یعنی استریو. |

---

## توضیح فنی

این برنامه یک رابط گرافیکی ویندوزی برای فشرده‌سازی ویدیو است و از موتور پردازش ویدیویی شناخته‌شده استفاده می‌کند. برنامه اطلاعات ویدیو را می‌خواند، حالت مناسب را انتخاب می‌کند و سپس فایل خروجی را با تنظیمات انتخاب‌شده می‌سازد.

| بخش | نقش |
|---|---|
| موتور فشرده‌سازی | اجرای پردازش اصلی ویدیو و تولید فایل خروجی. |
| ابزار خواندن اطلاعات ویدیو | خواندن نرخ فریم، رزولوشن، کدک و مدت ویدیو. |
| شتاب‌دهنده گرافیکی | استفاده از کارت گرافیک برای سرعت بیشتر در خروجی‌های رایج. |
| حالت پردازنده | استفاده خودکار وقتی شتاب‌دهنده گرافیکی در دسترس نیست. |
| کدک فشرده‌سازی اصلی | کاهش حجم قوی برای خروجی‌های رایج مثل `mp4`, `mkv`, `mov`. |
| خروجی وب | استفاده از روش مناسب برای خروجی `webm`. |

### رفتار حالت گرافیکی و پردازنده

| فرمت خروجی | حالت پردازش |
|---|---|
| `mp4` | در صورت وجود شتاب‌دهنده مناسب، با کارت گرافیک؛ در غیر این صورت با پردازنده. |
| `mkv` | در صورت وجود شتاب‌دهنده مناسب، با کارت گرافیک؛ در غیر این صورت با پردازنده. |
| `mov` | در صورت وجود شتاب‌دهنده مناسب، با کارت گرافیک؛ در غیر این صورت با پردازنده. |
| `webm` | معمولاً با پردازنده. |
| `avi` | بسته به روش خروجی، با کارت گرافیک یا پردازنده. |

برای استفاده عمومی، فرمت `mp4` پیشنهاد می‌شود.

---

## نصب و اجرا

از بخش انتشارها، آخرین فایل فشرده برنامه را دانلود کنید.

```text
VideoX_Compressor_v1.x_Beta.zip
```

فایل را از حالت فشرده خارج کنید و این فایل را اجرا کنید:

```text
VideoX.exe
```

این پوشه‌ها را حذف نکنید:

```text
ffmpeg/
_internal/
```

پوشه موتور پردازش باید شامل این فایل‌ها باشد:

```text
ffmpeg/bin/ffmpeg.exe
ffmpeg/bin/ffprobe.exe
```

---

## نحوه دریافت لایسنس

برنامه از سیستم لایسنس بر اساس کد دستگاه استفاده می‌کند.

مراحل فعال‌سازی:

1. فایل برنامه را اجرا کنید.
2. در صفحه فعال‌سازی، کد دستگاه را کپی کنید.
3. کد دستگاه را در تلگرام به آیدی زیر ارسال کنید.

```text
@thelouis_mahdi
```

4. بعد از بررسی، فایل لایسنس را دریافت می‌کنید.
5. فایل لایسنس را کنار فایل اجرایی برنامه قرار دهید یا از داخل برنامه انتخاب کنید.
6. روی دکمه بررسی دوباره بزنید.
7. وارد برنامه شوید.

لایسنس مخصوص همان دستگاه است و روی دستگاه دیگر فعال نمی‌شود.

---

## نحوه استفاده

1. فایل فشرده برنامه را دانلود و خارج کنید.
2. فایل اجرایی برنامه را اجرا کنید.
3. برنامه را با فایل لایسنس فعال کنید.
4. ویدیوها را انتخاب کنید یا داخل برنامه بکشید و رها کنید.
5. پوشه خروجی را انتخاب کنید.
6. یک حالت آماده انتخاب کنید یا تنظیمات را دستی تغییر دهید.
7. فرمت خروجی را انتخاب کنید.
8. دکمه شروع فشرده‌سازی را بزنید.
9. پیشرفت پردازش را داخل برنامه ببینید.
10. گزارش نهایی را در بخش لاگ بررسی کنید.

---

## وضعیت بتا

برنامه در حال حاضر در وضعیت بتا قرار دارد. هنوز یک محصول تجاری کاملاً نهایی‌شده نیست، اما به‌صورت فعال در همین مسیر توسعه پیدا می‌کند.

تمرکز فعلی توسعه:

- بهترین نتیجه روی کلاس‌های ضبط‌شده و ویدیوهای کم‌تحرک
- پایداری بهتر برای پردازش چند فایل
- حالت‌های آماده بهتر برای ویدیوهای پرتحرک
- بهبود رابط کاربری و تجربه کاربر
- دقیق‌تر شدن تخمین زمان
- دریافت بازخورد مداوم از تسترها و کاربران واقعی

به‌عنوان توسعه‌دهنده، من به‌صورت مستقیم با تسترها و کاربران در ارتباط هستم تا بازخوردها، باگ‌ها و پیشنهادها را جمع‌آوری کنم و برنامه را مرحله‌به‌مرحله بهتر کنم.

</div>

---

<div align="center">

### Code, design and development by **The Louis Mahdi**

**Telegram:** `@thelouis_mahdi`

</div>
