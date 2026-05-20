<div align="center">

# 🎬 VideoX Compressor

### A professional Windows video compressor powered by FFmpeg, NVIDIA NVENC, CPU fallback, and Device ID activation.

<p>
  <a href="#english">English</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#real-compression-example">Real Compression Test</a> •
  <a href="#settings-guide">Settings Guide</a> •
  <a href="#activation">Activation</a> •
  <a href="#فارسی">فارسی</a>
</p>

![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![FFmpeg](https://img.shields.io/badge/Engine-FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white)
![GPU](https://img.shields.io/badge/GPU-NVIDIA%20NVENC-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![HEVC](https://img.shields.io/badge/Codec-H.265%20%2F%20HEVC-orange?style=for-the-badge)
![Activation](https://img.shields.io/badge/Activation-Device%20ID-blueviolet?style=for-the-badge)

</div>

---

<a id="english"></a>

## 🇬🇧 English

**VideoX Compressor** is a Windows video compression tool designed for users who want to reduce video file size quickly without working with complex FFmpeg commands.

It is especially effective for **recorded classes, screen recordings, tutorials, meetings, slides, and low-motion educational videos**. On these types of videos, VideoX can dramatically reduce file size while keeping the result highly usable.

VideoX automatically uses **NVIDIA NVENC GPU acceleration** when available and falls back to CPU mode when a compatible GPU is not detected.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| Simple Windows GUI | Designed for normal users, not only technical users |
| Persian / English UI | Bilingual interface with built-in hints |
| FFmpeg Engine | Reliable compression powered by FFmpeg |
| NVIDIA NVENC | GPU acceleration for fast encoding when supported |
| CPU Fallback | Automatically works on systems without compatible NVIDIA GPU |
| Multiple Formats | Supports common input files and MP4, MKV, MOV, WEBM, AVI outputs |
| Adjustable Settings | Workers, height, FPS, output format, audio, GPU quality and CPU CRF |
| Time Estimation | Shows estimated processing time |
| Device ID Activation | License activation based on the user device |
| Commercial-style Workflow | Download, activate, select videos, compress |

---

<a id="screenshots"></a>

## 📸 Application Screenshots

### 1. Main Compression Interface

<div align="center">

![VideoX Main UI](screenshots/main_ui_fa.png)

</div>

This screen shows the main compression panel. The user can select input videos, choose output folder, select output format, and adjust compression settings such as FPS, height, GPU quality, CPU CRF, audio bitrate, audio channels, and workers.

### 2. NVIDIA GPU Acceleration in Action

<div align="center">

![GPU Usage](screenshots/gpu_usage.png)

</div>

VideoX can use NVIDIA NVENC hardware acceleration. In this test, the system used an **NVIDIA GeForce GTX 1650 Ti**, and the Windows Task Manager showed the GPU video encode engine running close to full utilization. This is why compression can be much faster than typical CPU-only compression tools.

### 3. Device ID License Activation

<div align="center">

![License UI](screenshots/license_ui.png)

</div>

The activation page shows the user Device ID. The user sends this Device ID to the developer on Telegram and receives a `license.key` file. The license is device-specific and works only on the registered machine.

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

### Result

```text
Approximate size reduction: ~98.7%
```

This type of dramatic compression is especially possible on low-motion videos such as:

- Recorded classes
- Screen recordings
- Tutorials
- Meetings
- Slide presentations
- Educational videos

VideoX is heavily optimized for this type of content.

---

<a id="settings-guide"></a>

## 🎛️ Compression Settings Guide

### Video Type: Recorded Classes / Screen Recording / Meetings / Tutorials

Best for low-motion educational content. This is the default recommended mode.

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

### Video Type: Gaming / High Motion / Fast Camera Movement

Use this mode for videos with fast movement, gameplay, effects, or camera motion.

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

### Video Type: Movies / TV Series / Cinematic Videos

Use this mode when quality and detail preservation matter more than extreme compression.

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

### Video Type: Social Media / Fast Sharing / Ultra Small Size

Use this mode when the smallest possible file size is the priority.

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

### GPU Quality Guide

```text
26 = High Quality
28 = Balanced
30 = Compressed
32 = Heavy Compression
35 = Ultra Small Size

Lower Number = Better Quality / Larger File
Higher Number = Smaller File / Lower Quality
```

### CPU CRF Guide

```text
22-24 = High Quality
25-28 = Balanced
30+ = Heavy Compression

Lower Number = Better Quality
Higher Number = Smaller File
```

### FPS Guide

```text
24 = Movies / Classes / Tutorials
30 = General Videos
60 = Gaming / Fast Motion
0 = Keep Original FPS
```

### Height Guide

```text
1080 = High Quality
720 = Balanced
480 = Ultra Small Size
```

### Audio Guide

```text
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

## ⚠️ Important Notes

- VideoX works best on low-motion videos such as recorded classes and screen recordings.
- High-motion videos need higher quality settings.
- NVIDIA GPU acceleration requires a compatible NVIDIA GPU and driver.
- If NVIDIA NVENC is not available, VideoX uses CPU mode.
- The license works only on the registered device.
- This repository provides the public release package only, not the source code.

---

<a id="فارسی"></a>

## 🇮🇷 فارسی

**VideoX Compressor** یک نرم‌افزار ویندوزی برای فشرده‌سازی ویدیو است که بدون نیاز به کار با دستورهای پیچیده FFmpeg، حجم فایل‌های ویدیویی را کاهش می‌دهد.

این برنامه مخصوصاً برای **کلاس‌های ضبط‌شده، اسکرین‌ریکورد، آموزش، جلسات، پاورپوینت و ویدیوهای کم‌تحرک** بسیار مناسب است. روی این نوع ویدیوها می‌تواند حجم فایل را به‌شدت کاهش دهد و خروجی همچنان قابل استفاده و قابل مشاهده باقی بماند.

اگر سیستم کارت گرافیک NVIDIA مناسب داشته باشد، برنامه از **NVIDIA NVENC** استفاده می‌کند و در غیر این صورت به‌صورت خودکار با CPU کار می‌کند.

### قابلیت‌ها

| قابلیت | توضیح |
|---|---|
| رابط ساده | مناسب کاربر عادی، نه فقط کاربر فنی |
| رابط دو زبانه | فارسی و انگلیسی |
| موتور FFmpeg | فشرده‌سازی پایدار با FFmpeg |
| شتاب‌دهی NVIDIA | استفاده از NVENC در صورت پشتیبانی سیستم |
| حالت CPU | استفاده خودکار از CPU در نبود GPU مناسب |
| فرمت‌های مختلف | پشتیبانی از خروجی MP4، MKV، MOV، WEBM و AVI |
| تنظیمات کاربردی | Workers، Height، FPS، کیفیت، صدا و مسیر خروجی |
| زمان تخمینی | نمایش زمان تقریبی پردازش |
| فعال‌سازی دستگاهی | لایسنس بر اساس Device ID |

### نمونه واقعی فشرده‌سازی کلاس

در تست واقعی روی یک ویدیوی کلاس ضبط‌شده:

```text
حجم فایل اصلی: 1.96 GB
حجم فایل خروجی: 25 MB
کاهش حجم تقریبی: 98.7%
```

این نتیجه بیشتر برای ویدیوهای کم‌تحرک مثل کلاس، جلسه، آموزش و اسکرین‌ریکورد قابل دستیابی است.

### راهنمای تنظیمات فارسی

#### کلاس / آموزش / اسکرین‌ریکورد / جلسه

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

#### گیم‌پلی / ویدیوی پرتحرک

```text
Workers: 1
Height: 1080
FPS: 30 یا 60
Output Format: mp4
GPU Quality: 28
CPU CRF: 25
Audio Bitrate: 64k
Audio Channels: 2
```

#### فیلم / سریال / ویدیوی سینمایی

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

#### شبکه اجتماعی / ارسال سریع / حجم خیلی کم

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
