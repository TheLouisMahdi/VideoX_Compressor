<div align="center">

# 🎬 VideoX Compressor

### Hardware-accelerated Windows video compression for recorded classes, tutorials, screen recordings and low-motion videos.

<p>
  <a href="#english">English</a> •
  <a href="#quick-start-en">Quick Start</a> •
  <a href="#activation-en">Activation</a> •
  <a href="#settings-en">Settings Guide</a> •
  <a href="#pipeline-en">Pipeline Guide</a> •
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

VideoX focuses on practical compression for recorded classes, tutorials, screen recordings, online meetings, slide-based educational videos, low-motion lecture videos and already-compressed videos that need smaller output size.

Depending on the system, VideoX can try **NVIDIA NVENC**, **Intel QSV / Quick Sync**, **AMD AMF**, or fall back to CPU mode. It uses FFmpeg and FFprobe internally.

> Current public beta: **VideoX Compressor v1.4.0 Beta - Pipeline Clarity Update**

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
| Pipeline preview | Explains the real Decode / Scale / Encode path before compression. |
| Legacy NVIDIA fallback | Can use a legacy NVIDIA FFmpeg build for older NVIDIA driver compatibility. |
| CPU fallback | Uses CPU mode when hardware acceleration is unavailable or unstable. |
| Smart Size Target | Improves size reduction on already-compressed videos. |
| File queue | Shows selected input files before compression. |
| Output validation | Checks output files and deletes invalid/corrupted partial outputs. |
| Diagnostic reports | Saves useful logs for debugging hardware and FFmpeg issues. |

---

## What is new after v1.2.5?

Version `v1.2.5` introduced General Safe Diagnostics. Newer builds up to `v1.4.0` improved UI stability, compression behavior, hardware selection, NVIDIA compatibility and pipeline clarity.

| Area | Added / Improved |
|---|---|
| Smart Size Target | Better size reduction for already-compressed or low-bitrate videos. |
| Output validation | Detects invalid, corrupted or incomplete outputs. |
| Cleanup | Deletes failed, cancelled or corrupted output files. |
| GPU / CPU sliders | GPU Quality and CPU CRF are controlled with sliders from 18 to 45. |
| Help buttons | `!` buttons explain GPU Quality and CPU CRF. |
| RTL Persian help | Persian help popups are right-to-left. |
| File queue panel | Selected input files are shown clearly before compression. |
| Safe retry | Hardware failures can retry once with CPU fallback. |
| Legacy NVIDIA FFmpeg | Adds `ffmpeg/legacy-nvidia` for older NVIDIA driver compatibility. |
| GPU Preference | User can choose between detected hardware paths. |
| Dynamic GPU filtering | Only hardware options that pass runtime tests are shown. |
| NVENC runtime fix | Fixes NVIDIA being hidden because the internal test frame was too small. |
| Pipeline Clarity | Explains what Performance Mode, Processing Strategy and Hardware Decode really change. |

---

<a id="screenshots-en"></a>

## Screenshots

### License / Device ID Activation

<div align="center">

![VideoX License Activation](screenshots/license.png)

</div>

### Main Compression Settings

<div align="center">

![VideoX Main Settings](screenshots/english-menu.png)

</div>

### File Queue and Removable Input List

<div align="center">

![VideoX File Queue](screenshots/file_selection.png)

</div>

### Progress and Final Report

<div align="center">

![VideoX Compression Report](screenshots/example.png)

</div>

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

<a id="pipeline-en"></a>

## Pipeline Clarity Guide

VideoX v1.4.0 adds clearer explanations for the main pipeline controls. These settings do **not** all do the same thing.

### Performance Mode

Performance Mode controls **how many files may be processed in parallel**, not the visual quality of a single file.

| Option | What it does | Best use |
|---|---|---|
| Stable | Safer mode. Processes one hardware job at a time. | Public release, weak systems, long videos, first test. |
| High Throughput | May allow up to 2 hardware jobs in parallel when a supported hardware encoder is active. | Multiple files in queue on stronger systems. |

Important notes:

- High Throughput does not directly improve output quality.
- High Throughput may not make a single file faster.
- High Throughput can increase GPU/CPU load and may be less stable if the system is busy.

### Processing Strategy

Processing Strategy controls how aggressively VideoX tries to move the pipeline toward hardware.

| Option | What it really means |
|---|---|
| Auto Balanced | Recommended default. Uses hardware encoding when available, but keeps safer CPU decode/scale behavior unless needed. |
| Maximum Hardware Acceleration | Tries to move more of the pipeline to hardware. This is most meaningful for NVIDIA when Hardware Decode is Aggressive. |
| CPU Only | Disables GPU encoding and forces CPU encoding. |

Important notes:

- Maximum Hardware Acceleration is strongest on NVIDIA with Aggressive Hardware Decode.
- On AMD AMF or Intel QSV, this usually still means **GPU encode with CPU scaling**, not a fully GPU-based pipeline.
- CPU Only overrides hardware encoding even if GPU Preference is set to NVIDIA, Intel or AMD.

### Hardware Decode

Hardware Decode controls the **decode side** of the pipeline. It does not automatically disable or enable GPU encoding.

| Option | Decode | Scale | Encode |
|---|---|---|---|
| Off | CPU | CPU | GPU or CPU depending on selected encoder |
| Auto | FFmpeg hardware auto when possible | Usually CPU | GPU or CPU depending on selected encoder |
| Aggressive | NVIDIA CUDA decode when NVIDIA is selected | NVIDIA CUDA scale only in NVIDIA + Maximum Hardware Acceleration mode | NVIDIA NVENC |

Important notes:

- `Hardware Decode: Off` is the safest mode and still allows GPU encoding.
- `Hardware Decode: Auto` tries hardware decoding but usually keeps scaling on CPU.
- `Hardware Decode: Aggressive` is mainly useful for NVIDIA. It may enable CUDA decode and CUDA scaling.
- If aggressive decode/scale fails, VideoX can retry with safer CPU scaling.

### GPU Preference

VideoX shows only hardware options that pass real runtime tests.

Possible options:

```text
Auto Best Available
NVIDIA NVENC
Intel QSV
AMD AMF
CPU Only
```

| Option | Meaning |
|---|---|
| Auto Best Available | VideoX selects the best runtime-tested hardware path. |
| NVIDIA NVENC | Prefer NVIDIA hardware encoding when available. Modern FFmpeg is tested first; legacy NVIDIA FFmpeg may be tested if needed. |
| Intel QSV | Prefer Intel Quick Sync / QSV when available. |
| AMD AMF | Prefer AMD AMF when available. |
| CPU Only | Force CPU encoding. |

### Pipeline Preview

VideoX v1.4.0 shows a pipeline preview in the UI. It explains the expected processing path, for example:

```text
Decode: CPU | Scale: CPU | Encode: hevc_amf / AMD
```

or:

```text
Decode: NVIDIA CUDA | Scale: NVIDIA CUDA | Encode: hevc_nvenc / NVIDIA
```

This helps users understand whether the selected settings really move the full pipeline to GPU, or only use GPU for encoding.

---

## GPU Preference and Hybrid Laptops

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

For speed testing on stronger NVIDIA systems:

```text
Performance Mode: High Throughput
Processing Strategy: Maximum Hardware Acceleration
Hardware Decode: Aggressive
GPU Preference: NVIDIA NVENC
```

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

For AMD, Maximum Hardware Acceleration currently mainly means hardware encoding with AMD AMF. Scaling usually remains CPU-based.

---

## Diagnostic Logs and Bug Reports

If an error happens, VideoX can save diagnostic information that helps identify the problem.

Reports may include:

- app version
- local and UTC timestamp
- Windows and system information
- modern FFmpeg path
- legacy NVIDIA FFmpeg path
- available encoders
- runtime encoder test results
- NVIDIA driver information
- selected GPU Preference
- selected encoder
- FFmpeg profile used
- pipeline preview
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
VideoX_Compressor_v1.4.0_Beta_Pipeline_Clarity_Update.zip
```

Extract the ZIP file and run:

```text
VideoX.exe
```

Required folder structure:

```text
VideoX_Compressor_v1.4.0_Beta_Pipeline_Clarity_Update/
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

> نسخه فعلی بتا: **VideoX Compressor v1.4.0 Beta - Pipeline Clarity Update**

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
| اسلایدر کیفیت GPU و CPU | مقدار کیفیت با نوار قابل تغییر است. |
| دکمه راهنما | کنار کیفیت GPU و CPU دکمه `!` برای توضیح ساده اضافه شده است. |
| متن فارسی راست‌به‌چپ | توضیحات فارسی راهنما راست‌چین و راست‌به‌چپ شده‌اند. |
| لیست فایل‌های ورودی | فایل‌های انتخاب‌شده داخل پنل مشخص نمایش داده می‌شوند. |
| تلاش دوباره امن | اگر پردازش سخت‌افزاری خطا بدهد، برنامه یک بار با پردازنده دوباره تلاش می‌کند. |
| FFmpeg لگسی انویدیا | برای سازگاری بهتر با درایورهای قدیمی‌تر انویدیا اضافه شده است. |
| GPU Preference | کاربر می‌تواند مسیر پردازش را انتخاب کند. |
| فیلتر پویا GPU | فقط گزینه‌هایی نمایش داده می‌شوند که تست واقعی را پاس کنند. |
| اصلاح تست NVENC | مشکل پنهان شدن اشتباه NVIDIA به دلیل کوچک بودن فریم تست اصلاح شد. |
| شفاف‌سازی Pipeline | اثر Performance Mode، Processing Strategy و Hardware Decode واضح‌تر شد. |

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

## راهنمای شفاف Pipeline

نسخه v1.4.0 توضیح می‌دهد هر گزینه دقیقاً چه بخشی از مسیر پردازش را تغییر می‌دهد.

### Performance Mode

این گزینه بیشتر روی **تعداد فایل‌هایی که همزمان پردازش می‌شوند** اثر دارد، نه کیفیت خروجی.

| گزینه | اثر واقعی | کاربرد بهتر |
|---|---|---|
| Stable | حالت امن‌تر. معمولاً یک پردازش سخت‌افزاری همزمان انجام می‌دهد. | انتشار عمومی، سیستم ضعیف، ویدیوهای طولانی. |
| High Throughput | در صورت وجود شتاب‌دهنده مناسب، ممکن است تا دو فایل را همزمان پردازش کند. | چند فایل در صف روی سیستم قوی‌تر. |

نکته: High Throughput الزاماً یک فایل تکی را سریع‌تر نمی‌کند و ممکن است فشار بیشتری به سیستم وارد کند.

### Processing Strategy

این گزینه مشخص می‌کند برنامه چقدر تلاش کند مسیر پردازش را به سخت‌افزار منتقل کند.

| گزینه | معنی واقعی |
|---|---|
| Auto Balanced | حالت پیشنهادی. از GPU برای Encode استفاده می‌کند، ولی مسیر امن‌تر را حفظ می‌کند. |
| Maximum Hardware Acceleration | بیشترین اثر را روی NVIDIA همراه با Hardware Decode Aggressive دارد. برای AMD و Intel معمولاً بیشتر به معنی GPU Encode با Scale روی CPU است. |
| CPU Only | پردازش گرافیکی را برای Encode غیرفعال می‌کند و برنامه با CPU ادامه می‌دهد. |

### Hardware Decode

این گزینه سمت Decode را کنترل می‌کند. خاموش بودن آن به معنی خاموش شدن GPU Encode نیست.

| گزینه | Decode | Scale | Encode |
|---|---|---|---|
| Off | CPU | CPU | GPU یا CPU بسته به Encoder انتخاب‌شده |
| Auto | تلاش خودکار FFmpeg برای Decode سخت‌افزاری | معمولاً CPU | GPU یا CPU |
| Aggressive | برای NVIDIA می‌تواند CUDA Decode فعال کند | فقط در NVIDIA + Maximum Hardware Acceleration می‌تواند CUDA Scale شود | NVIDIA NVENC |

نکته‌های مهم:

- `Hardware Decode: Off` امن‌ترین حالت است و همچنان می‌تواند از GPU برای Encode استفاده کند.
- `Hardware Decode: Auto` تلاش می‌کند Decode را سخت‌افزاری کند، اما معمولاً Scale روی CPU می‌ماند.
- `Hardware Decode: Aggressive` بیشتر برای NVIDIA معنی‌دار است.
- اگر مسیر aggressive خطا بدهد، برنامه می‌تواند با مسیر امن‌تر دوباره تلاش کند.

### GPU Preference

برنامه فقط گزینه‌هایی را نشان می‌دهد که تست واقعی زمان اجرا را پاس کنند.

```text
Auto Best Available
NVIDIA NVENC
Intel QSV
AMD AMF
CPU Only
```

### Pipeline Preview

در نسخه v1.4.0 برنامه یک پیش‌نمایش مسیر پردازش نمایش می‌دهد؛ مثلاً:

```text
Decode: CPU | Scale: CPU | Encode: hevc_amf / AMD
```

یا:

```text
Decode: NVIDIA CUDA | Scale: NVIDIA CUDA | Encode: hevc_nvenc / NVIDIA
```

این بخش کمک می‌کند کاربر بفهمد فقط Encode روی GPU است یا Decode و Scale هم واقعاً به GPU منتقل شده‌اند.

---

## نکته برای لپتاپ‌های دو گرافیکه

روی لپتاپ‌هایی که دو کارت گرافیک دارند، ویندوز ممکن است پردازش را طبق تنظیمات خودش بین گرافیک‌ها جابه‌جا کند.

برای نتیجه بهتر، این فایل‌ها را در Windows Graphics Settings روی High Performance قرار دهید:

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

برای تست سرعت روی سیستم انویدیا قوی‌تر:

```text
Performance Mode: High Throughput
Processing Strategy: Maximum Hardware Acceleration
Hardware Decode: Aggressive
GPU Preference: NVIDIA NVENC
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

در AMD، حالت Maximum Hardware Acceleration فعلاً بیشتر به معنی Encode سخت‌افزاری است و Scale معمولاً روی CPU می‌ماند.

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
- پیش‌نمایش Pipeline
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
VideoX_Compressor_v1.4.0_Beta_Pipeline_Clarity_Update.zip
```

بعد از خارج کردن از حالت فشرده، این فایل را اجرا کنید:

```text
VideoX.exe
```

ساختار لازم پوشه‌ها:

```text
VideoX_Compressor_v1.4.0_Beta_Pipeline_Clarity_Update/
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
- شفاف‌تر شدن مسیر واقعی Decode / Scale / Encode
- تلاش دوباره و بازگشت امن‌تر هنگام خطا
- رابط کاربری ساده‌تر برای کاربران غیرتخصصی
- دریافت بازخورد از تسترها و کاربران واقعی

</div>

---

<div align="center">

### Code, design and development by **The Louis Mahdi**

**Telegram:** `@thelouis_mahdi`

</div>
