<div align="center">

# 🎬 VideoX Compressor

### GPU-accelerated Windows video compression powered by FFmpeg, NVIDIA NVENC, CPU fallback, and Device ID activation.

<p>
  <a href="#english">English</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#real-compression-example">Real Test</a> •
  <a href="#settings-guide">Settings Guide</a> •
  <a href="#beta-status">Beta Status</a> •
  <a href="#activation">Activation</a> •
  <a href="#فارسی">فارسی</a>
</p>

![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![FFmpeg](https://img.shields.io/badge/Engine-FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)
![GPU](https://img.shields.io/badge/GPU-NVIDIA%20NVENC-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![HEVC](https://img.shields.io/badge/Codec-H.265%20%2F%20HEVC-orange?style=for-the-badge)
![Beta](https://img.shields.io/badge/Status-Beta-blue?style=for-the-badge)
![Activation](https://img.shields.io/badge/Activation-Device%20ID-blueviolet?style=for-the-badge)

</div>

---

<a id="english"></a>

## 🇬🇧 English

**VideoX Compressor** is a Windows video compression tool designed to reduce video file size quickly without forcing users to write FFmpeg commands manually.

The main idea behind VideoX is **hardware-accelerated compression**: when a compatible NVIDIA GPU is available, the app uses **NVIDIA NVENC** to offload video encoding from the CPU to the GPU. This can make compression much faster than typical CPU-only workflows, especially on laptops and PCs with supported NVIDIA graphics cards.

VideoX is currently strongest on **recorded classes, screen recordings, tutorials, meetings, slides, and low-motion educational videos**. On this type of content, it can dramatically reduce file size while keeping the output highly usable.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| GPU Acceleration | Uses NVIDIA NVENC hardware encoding when available |
| CPU Fallback | Works with CPU mode when a compatible NVIDIA GPU is not available |
| FFmpeg Engine | Uses FFmpeg under the hood for reliable compression |
| Simple Windows GUI | Designed for normal users, not only technical users |
| Persian / English UI | Bilingual interface with built-in hints |
| Multiple Formats | Supports common input files and MP4, MKV, MOV, WEBM, AVI outputs |
| Adjustable Settings | Workers, height, FPS, output format, audio, GPU quality and CPU CRF |
| Device ID Activation | License activation based on the registered device |
| Real Use Case | Optimized first for recorded classes and low-motion educational videos |

---

<a id="screenshots"></a>

## 📸 Application Screenshots

### Main Compression Interface

<div align="center">

![VideoX Main UI](screenshots/main_ui_fa.png)

</div>

The main panel lets the user select videos, choose output folder, select output format, and tune compression settings such as workers, height, FPS, GPU quality, CPU CRF, audio bitrate and audio channels.

### NVIDIA GPU Acceleration in Action

<div align="center">

![GPU Usage](screenshots/gpu_usage.png)

</div>

In this test, VideoX used **NVIDIA GeForce GTX 1650 Ti** and pushed the GPU video encode engine close to full utilization. This shows the accelerator nature of the app: supported GPUs can process video compression much faster than CPU-only encoding.

### Device ID License Activation

<div align="center">

![License UI](screenshots/license_ui.png)

</div>

The activation screen displays the user Device ID. The user sends this Device ID on Telegram and receives a device-specific `license.key` file.

---

<a id="real-compression-example"></a>

## 🚀 Real Compression Example

### Recorded Class Compression Test

<div align="center">

![Class Compression Example](screenshots/class_compression_example.jpg)

</div>

This real test was performed on a recorded class video.

| Item | Size |
|---|---:|
| Original recorded class video | 1.96 GB |
| Compressed output | 25 MB |

```text
Approximate size reduction: ~98.7%
```

This level of compression is especially realistic for low-motion videos such as recorded classes, screen recordings, meetings, slides, tutorials and educational videos.

---

<a id="settings-guide"></a>

## 🎛️ Compression Settings Guide

### Recorded Classes / Screen Recording / Meetings / Tutorials

Best for low-motion educational content. This is the current main optimization target.

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

### Gaming / High Motion / Fast Camera Movement

Use higher FPS and better quality settings. Very low FPS such as 24 may cause motion to feel less smooth on high-motion videos.

```text
Workers: 1
Height: 1080
FPS: 30 or 60
Output Format: mp4
GPU Quality: 28
CPU CRF: 25
Audio Bitrate: 64k
Audio Channels: 2
```

### Movies / TV Series / Cinematic Videos

Use this mode when detail preservation matters more than extreme compression.

```text
Workers: 1
Height: 1080
FPS: 24
Output Format: mp4
GPU Quality: 27
CPU CRF: 24
Audio Bitrate: 96k
Audio Channels: 2
```

### Social Media / Fast Sharing / Ultra Small Size

Use this mode when the smallest possible size is the priority.

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

### Quality Guides

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
24 = Movies / Classes / Tutorials
30 = General Videos
60 = Gaming / Fast Motion
0 = Keep Original FPS

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

## ⚙️ GPU / CPU Behavior

| Output Format | Processing Mode |
|---|---|
| MP4 | GPU if NVIDIA NVENC is available, otherwise CPU |
| MKV | GPU if NVIDIA NVENC is available, otherwise CPU |
| MOV | GPU if NVIDIA NVENC is available, otherwise CPU |
| WEBM | CPU mode |
| AVI | GPU/CPU depending on available encoder |

For general use, **MP4** is recommended.

---

<a id="beta-status"></a>

## 🧪 Beta Status & Development Roadmap

VideoX Compressor is currently in an **early beta stage**. It is not yet a fully polished commercial product, but it is being developed step by step in that direction.

The current version is already useful for its main target: **recorded classes and low-motion educational videos**. Other content types such as gaming, cinematic footage, fast camera movement and high-motion videos still need more testing and better presets.

### Known Limitations in the Current Beta

- High-motion videos may feel less smooth if compressed at 24 FPS.
- Some motion-heavy videos may show frame dropping, motion judder or reduced smoothness when aggressive settings are used.
- ETA calculation is not fully accurate yet and does not perfectly reflect real GPU acceleration speed.
- On GPU systems, the real processing time may be much faster than the displayed estimated time.
- Multi-file batch processing can sometimes be unstable, especially with multiple workers.
- For maximum stability in the current beta, `Workers: 1` is recommended.
- Current presets are best tuned for recorded classes, tutorials and screen recordings.

### Planned Improvements

- More accurate ETA calculation with GPU-aware speed estimation.
- Better high-motion presets for gaming, cinematic footage and fast camera movement.
- More stable batch processing for multiple files.
- Better worker management for different laptop/desktop hardware levels.
- Warnings when FPS is too low for high-motion videos.
- Improved UI explanations for GPU mode, CPU mode and preset selection.
- Continuous testing with real users and program testers.

As the developer, I stay in direct contact with program testers and users to collect feedback, fix bugs and improve the application over time.

---

<a id="download"></a>

## 📦 Download

Go to the **Releases** section and download:

```text
VideoX_Compressor_v1.0.0.zip
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

---

<a id="activation"></a>

## 🔐 License Activation

After opening the software, the app shows your **Device ID**.

Send the Device ID on Telegram:

```text
@thelouis_mahdi
```

After verification, you will receive a `license.key` file.

Place `license.key` next to `VideoX.exe` or select it from inside the app.

### Activation Steps

1. Run `VideoX.exe`.
2. Copy your Device ID.
3. Send it to `@thelouis_mahdi` on Telegram.
4. Receive `license.key`.
5. Put `license.key` next to the EXE file or select it inside the app.
6. Recheck license.
7. Enter the program.

---

## 🚀 How to Use

1. Download the ZIP file from Releases.
2. Extract the ZIP file.
3. Run `VideoX.exe`.
4. Activate the software with `license.key`.
5. Select input videos.
6. Choose output folder.
7. Select output format.
8. Choose settings based on video type.
9. Click **Start Compress**.
10. Wait for the process to finish.

---

<a id="فارسی"></a>

## 🇮🇷 فارسی

**VideoX Compressor** یک نرم‌افزار ویندوزی برای فشرده‌سازی ویدیو است که بدون نیاز به کار با دستورهای پیچیده FFmpeg، حجم فایل‌های ویدیویی را کاهش می‌دهد.

ایده اصلی VideoX استفاده از **شتاب‌دهی سخت‌افزاری GPU** است. اگر سیستم کارت گرافیک NVIDIA مناسب داشته باشد، برنامه از **NVIDIA NVENC** برای پردازش سریع‌تر استفاده می‌کند و اگر GPU مناسب موجود نباشد، به‌صورت خودکار با CPU کار می‌کند.

نقطه قوت اصلی نسخه فعلی، ویدیوهای کم‌تحرک مثل **کلاس ضبط‌شده، اسکرین‌ریکورد، آموزش، جلسه و پاورپوینت** است. روی این نوع ویدیوها، VideoX می‌تواند حجم فایل را به‌شدت کاهش دهد و خروجی همچنان قابل استفاده باقی بماند.

### قابلیت‌ها

| قابلیت | توضیح |
|---|---|
| شتاب‌دهی GPU | استفاده از NVIDIA NVENC برای افزایش سرعت پردازش |
| حالت CPU | استفاده خودکار از CPU در نبود GPU مناسب |
| موتور FFmpeg | فشرده‌سازی پایدار با FFmpeg |
| رابط ساده | مناسب کاربر عادی، نه فقط کاربر فنی |
| رابط دو زبانه | فارسی و انگلیسی |
| فرمت‌های مختلف | پشتیبانی از خروجی MP4، MKV، MOV، WEBM و AVI |
| تنظیمات کاربردی | Workers، Height، FPS، کیفیت، صدا و مسیر خروجی |
| فعال‌سازی دستگاهی | لایسنس بر اساس Device ID |

### نمونه واقعی فشرده‌سازی کلاس

```text
حجم فایل اصلی: 1.96 GB
حجم فایل خروجی: 25 MB
کاهش حجم تقریبی: 98.7%
```

این نتیجه بیشتر برای ویدیوهای کم‌تحرک مثل کلاس، جلسه، آموزش و اسکرین‌ریکورد قابل دستیابی است.

### وضعیت بتا و مسیر توسعه

VideoX Compressor در حال حاضر در مرحله **بتا و نسخه اولیه** قرار دارد. این پروژه هنوز یک محصول تجاری کاملاً نهایی‌شده نیست، اما به‌مرور در همین مسیر توسعه پیدا می‌کند.

نسخه فعلی برای هدف اصلی خود، یعنی فشرده‌سازی ویدیوهای کلاس، آموزش، جلسه و اسکرین‌ریکورد، عملکرد بسیار خوبی دارد. با این حال، برای ویدیوهای پرتحرک مثل گیم‌پلی، فیلم سینمایی، حرکت سریع دوربین و ویدیوهای motion بالا هنوز نیاز به تست و بهینه‌سازی بیشتر دارد.

#### محدودیت‌های فعلی

- در ویدیوهای پرتحرک، FPS پایین مثل 24 ممکن است باعث کاهش نرمی حرکت شود.
- در بعضی ویدیوهای motion بالا ممکن است حس حذف فریم، پرش تصویر یا frame dropping دیده شود.
- زمان تخمینی فعلی هنوز دقیق نیست و اثر واقعی GPU را کامل در نظر نمی‌گیرد.
- روی سیستم‌های دارای GPU، زمان واقعی پردازش ممکن است خیلی کمتر از زمان تخمینی نمایش‌داده‌شده باشد.
- پردازش چند فایل همزمان گاهی ناپایدار است.
- برای پایداری بیشتر در نسخه فعلی، مقدار `Workers: 1` پیشنهاد می‌شود.
- Presetهای فعلی بیشتر برای کلاس ضبط‌شده، آموزش و اسکرین‌ریکورد بهینه شده‌اند.

#### مسیر بهبود

- دقیق‌تر شدن تخمین زمان با درنظرگرفتن سرعت واقعی GPU.
- ساخت presetهای بهتر برای گیم‌پلی، فیلم و ویدیوهای پرتحرک.
- پایدارتر شدن batch processing و پردازش چند فایل همزمان.
- مدیریت بهتر Workers بر اساس سخت‌افزار سیستم.
- اضافه شدن هشدار برای انتخاب FPS پایین در ویدیوهای پرموشن.
- توضیح بهتر تفاوت GPU mode و CPU mode در UI و README.
- تست مداوم با کاربران و تسترهای برنامه.

به‌عنوان توسعه‌دهنده برنامه، من به‌صورت مداوم با تسترها و کاربران در ارتباط هستم تا بازخوردها، باگ‌ها و پیشنهادها را جمع‌آوری کنم و برنامه را مرحله‌به‌مرحله بهتر کنم.

### دریافت لایسنس

بعد از اجرای برنامه، یک **Device ID** نمایش داده می‌شود.

برای دریافت لایسنس، این کد را در تلگرام به آیدی زیر ارسال کنید:

```text
@thelouis_mahdi
```

بعد از دریافت فایل `license.key`، آن را کنار فایل اجرایی برنامه قرار دهید یا از داخل برنامه انتخاب کنید.

### نکات مهم

- پوشه `ffmpeg` را حذف نکنید.
- پوشه `_internal` را حذف نکنید.
- لایسنس فقط روی همان دستگاه فعال می‌شود.
- در صورت پایان اعتبار لایسنس، در تلگرام پیام دهید.
- این ریپو فقط فایل انتشار عمومی برنامه را ارائه می‌کند و شامل سورس کد نیست.

---

<div align="center">

### Designed and developed by **The Louis Mahdi**

**Telegram:** `@thelouis_mahdi`

</div>
