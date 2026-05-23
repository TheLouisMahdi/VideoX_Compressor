# VideoX Compressor - Release Notes

## Current Public Beta

```text
VideoX Compressor v1.3.5 Beta - Legacy NVIDIA FFmpeg Fallback
```

VideoX Compressor is a Windows video compression application focused on simple, practical and hardware-accelerated compression for recorded classes, tutorials, screen recordings, online meetings, low-motion lecture videos and everyday videos that need smaller file size.

The project is still in **Beta**. The strongest current results are usually on low-motion educational videos and screen recordings. Results depend on source video type, bitrate, motion level, resolution, hardware, driver version and selected settings.

---

## Version Timeline

| Version | Release Focus |
|---|---|
| v1.2.5 Beta | General Safe Diagnostics, bug reports, safer public testing. |
| v1.2.6 Beta | Already-compressed video warning and bitrate analysis. |
| v1.2.7 Beta | Cleanup of failed, cancelled or corrupted output files. |
| v1.2.8 Beta | Smart Recompression for already-compressed sources. |
| v1.2.9 Beta | Smart Size Target for better real size reduction. |
| v1.3.0 Beta | GPU Quality slider. |
| v1.3.1 Beta | Help buttons for GPU Quality and CPU CRF. |
| v1.3.2 Beta | CPU CRF slider. |
| v1.3.3 Beta | RTL Persian help popup fix. |
| v1.3.4 Beta | File queue panel and safe retry behavior. |
| v1.3.5 Beta | Legacy NVIDIA FFmpeg fallback for older NVIDIA drivers. |

---

# English Release Notes

## v1.3.5 Beta - Legacy NVIDIA FFmpeg Fallback

### Main Goal

This version improves hardware compatibility, especially on laptops and systems with older NVIDIA drivers where the NVIDIA GPU is detected but NVENC fails at runtime.

### New Features

- Added support for two FFmpeg profiles:
  - `ffmpeg/modern`
  - `ffmpeg/legacy-nvidia`
- Added Legacy NVIDIA FFmpeg fallback.
- Added NVIDIA driver version diagnostics.
- Added warnings for old NVIDIA drivers.
- Added stronger warning for very old NVIDIA drivers.
- Improved GPU Diagnostics output.
- Improved encoder selection logic.
- Improved fallback order:
  - Modern NVIDIA NVENC
  - Legacy NVIDIA NVENC
  - Intel QSV
  - AMD AMF
  - CPU fallback
- Logs which FFmpeg profile is selected.
- Keeps Intel, AMD and CPU paths on the modern FFmpeg build when possible.

### Required Package Structure

```text
VideoX_Compressor_v1.3.5_Beta_Legacy_NVIDIA_Fallback/
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

### Notes

- Legacy FFmpeg is used only when modern NVIDIA NVENC fails and legacy NVENC passes the runtime test.
- If both modern and legacy NVENC fail, VideoX falls back to Intel QSV, AMD AMF or CPU mode.
- For very old NVIDIA drivers, updating the driver is still recommended.
- Do not delete the `ffmpeg` folder.
- Do not delete the `_internal` folder.

---

## v1.3.4 Beta - File Queue & Safe Retry

### Main Goal

This version improves file handling, makes the selected input files visible to users and improves behavior when hardware encoding fails during compression.

### New Features

- Added visible file queue panel.
- Selected files are shown before compression.
- Each selected file has an `X` button for removal before starting.
- Input changes are locked while compression is running.
- Added safe retry behavior for hardware encoder failures.
- If hardware output fails or becomes invalid, VideoX can retry the same file once with CPU fallback.
- If one or more files fail, the final status is shown as `Finished with errors` instead of simply `Finished`.
- Improved final warning messages when compression finishes with failed files.

### Fixed / Improved

- Better handling of long videos on sensitive hardware paths such as Intel QSV.
- Better user control before starting compression.
- Better distinction between successful and partially failed sessions.

---

## v1.3.3 Beta - RTL Help Hotfix

### Main Goal

This version fixes Persian help popup direction and readability.

### New Features / Fixes

- Persian GPU Quality help text is rendered right-to-left.
- Persian CPU CRF help text is rendered right-to-left.
- Persian popup title is right-aligned.
- Tahoma font is used for Persian help text.
- RTL markers are used internally to reduce mixed Persian/English text problems.

---

## v1.3.2 Beta - CPU CRF Slider

### Main Goal

This version makes CPU compression quality easier to understand and control.

### New Features

- CPU CRF changed from a free numeric entry to a slider.
- Allowed CPU CRF range: `18` to `45`.
- Current CPU CRF value is shown next to the slider.
- CPU CRF slider updates automatically when a preset changes.
- Stored CPU CRF values outside the allowed range are clamped automatically.
- The CPU CRF help button remains available.

### CPU CRF Guide

| Range | Meaning |
|---|---|
| 18 to 24 | High quality, larger file. |
| 25 to 30 | Balanced mode. |
| 31 to 34 | Smaller file, good for classes and tutorials. |
| 35 to 45 | Strong compression, higher quality-loss risk. |

---

## v1.3.1 Beta - Quality Help Buttons

### Main Goal

This version improves usability for non-technical users.

### New Features

- Added `!` help button next to GPU Quality.
- Added `!` help button next to CPU CRF.
- Each button opens a separate help popup.
- Help popup includes an `OK` button.
- Help popup includes a close `X` button.
- Help text explains quality and file size trade-offs.
- Separate English and Persian help texts are included.

---

## v1.3.0 Beta - GPU Quality Slider

### Main Goal

This version makes GPU quality easier to control from the UI.

### New Features

- GPU Quality changed from a free numeric entry to a slider.
- Allowed GPU Quality range: `18` to `45`.
- Current GPU Quality value is shown next to the slider.
- GPU Quality slider updates automatically when a preset changes.
- Stored GPU Quality values outside the allowed range are clamped automatically.

### GPU Quality Guide

| Range | Meaning |
|---|---|
| 18 to 25 | Very high quality, larger file. |
| 26 to 32 | Balanced quality and size. |
| 33 to 36 | Smaller file, good for classes and low-motion videos. |
| 37 to 45 | Strong compression, higher quality-loss risk. |

---

## v1.2.9 Beta - Smart Size Target

### Main Goal

This version improves real size reduction on videos that are already compressed or already low-bitrate.

### New Features

- Smart Recompression was improved into Smart Size Target.
- For already-compressed videos, VideoX can target a smaller total bitrate instead of relying only on free CQ/CRF behavior.
- Default goal is around half-size output when possible.
- More aggressive settings can move toward smaller outputs, but quality risk increases.
- Original height is kept by default.
- FPS can be kept original when FPS is set to `0`.
- Audio can be reduced to smaller settings such as `32k mono` when appropriate.
- Uses bitrate controls such as video bitrate target, maxrate and buffer size when Smart Size Target is active.

### Notes

- Half-size output is more realistic for already-compressed sources.
- Quarter-size output may be possible only with stronger compression and higher quality-loss risk.
- VideoX avoids automatic heavy downscaling such as forcing 480p unless the user chooses lower height manually.

---

## v1.2.8 Beta - Smart Recompression

### Main Goal

This version improves behavior when quality-based encoding creates an output close to or larger than the original file.

### New Features

- Added Smart Recompression for already-compressed sources.
- Detects already-compressed videos using bitrate and bits-per-pixel-frame analysis.
- Applies a safer bitrate cap for video when suitable.
- Reduces audio size when possible.
- Keeps height by default to avoid obvious visual loss.
- Logs Smart Recompression status, source bitrate, target bitrate and audio target.

---

## v1.2.7 Beta - Cleanup Hotfix

### Main Goal

This version prevents broken or useless files from staying in the output folder and keeps the log folder cleaner.

### New Features / Fixes

- Deletes failed or incomplete output files.
- Deletes cancelled partial outputs.
- Deletes invalid or corrupted output files after validation failure.
- Deletes incomplete output before retrying a safer path.
- Uses ffprobe-based validation after FFmpeg finishes.
- Checks whether output has readable duration and video stream.
- Clears old VideoX logs before each new compression session.

### Notes

This version reduces confusion for users because failed jobs no longer leave broken output files behind.

---

## v1.2.6 Beta - Already-Compressed Warning

### Main Goal

This version adds warnings and analysis for videos that are already heavily compressed.

### New Features

- Detects already-compressed or low-bitrate source videos.
- Warns users before compression when large size reduction may not be possible.
- Shows source video bitrate, total bitrate and audio bitrate.
- Calculates bits per pixel per frame as a compression-density signal.
- Suggests quality-safe settings without forcing 480p downscaling.
- Logs output bitrate after compression.
- Logs whether video bitrate was reduced or increased.
- Warns when output size is close to the input size.

### Notes

For already-compressed videos, further compression may require lower bitrate or stronger quality settings. A very large reduction is not always possible without visible quality loss.

---

## v1.2.5 Beta - General Safe Diagnostics

### Main Goal

This version introduced the first public-oriented safe diagnostics workflow.

### New Features

- Added General Safe Mode for public testing.
- Added automatic diagnostic report generation when errors happen.
- Added manual Export Bug Report button.
- Added Open Logs button.
- Added GPU Diagnostics with saved report output.
- Improved hardware encoder selection.
- Added better fallback behavior when hardware acceleration fails.
- Added detailed logs with timestamp, system info, encoder info and FFmpeg error details.
- Added support-oriented log files that users can send for debugging.

### Diagnostic Reports

If the app fails during compression, it can automatically save a diagnostic report containing:

- app version
- local and UTC timestamp
- Windows and system information
- FFmpeg and FFprobe paths
- available video encoders
- runtime encoder test results
- selected settings
- selected encoder
- current input file
- FFmpeg error output
- current UI log

Default log location:

```text
C:\Users\<User>\AppData\Local\TheLouisMahdi\VideoXCompressor\logs
```

---

# Recommended Settings

## Normal Users

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

## Older NVIDIA Laptops

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
Output Format: mp4
```

Then run GPU Diagnostics. If modern NVENC fails and legacy NVIDIA FFmpeg works, VideoX can use the legacy NVIDIA path.

## Already-Compressed Videos

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

---

# Activation

After opening the app:

1. Copy your Device ID.
2. Send it on Telegram to:

```text
@thelouis_mahdi
```

3. Receive your device-specific `license.key` file.
4. Place `license.key` next to `VideoX.exe`, or select it from inside the app.
5. Click Recheck and enter the program.

Each license is device-specific and works only on the registered device.

---

# Important Notes

- This is a Beta release.
- Best results are currently expected on low-motion videos.
- High-motion videos may need different settings than recorded classes.
- Hardware acceleration depends on GPU model, driver, FFmpeg support and selected output format.
- If hardware acceleration is not available, the app falls back to CPU mode.
- Legacy NVIDIA FFmpeg is only used when modern NVIDIA NVENC fails and the legacy path passes runtime tests.
- Very old NVIDIA drivers should still be updated when possible.
- Time estimation is approximate and may be less accurate in GPU mode.
- Do not delete the `ffmpeg` folder.
- Do not delete the `_internal` folder.
- Do not include `license.key` inside the public ZIP package.

---

# یادداشت‌های انتشار فارسی

<div dir="rtl" align="right">

## نسخه فعلی عمومی

```text
VideoX Compressor v1.3.5 Beta - Legacy NVIDIA FFmpeg Fallback
```

ویدیو ایکس کامپرسور یک برنامه ویندوزی برای فشرده‌سازی ویدیو است. تمرکز برنامه روی فشرده‌سازی ساده، کاربردی و در صورت امکان شتاب‌داده‌شده با سخت‌افزار است.

برنامه هنوز در وضعیت **بتا** قرار دارد. بهترین نتیجه فعلی معمولاً روی کلاس‌های ضبط‌شده، آموزش‌ها، اسکرین‌ریکوردها، جلسات آنلاین و ویدیوهای کم‌تحرک دیده می‌شود.

---

## جدول نسخه‌ها

| نسخه | تمرکز اصلی |
|---|---|
| v1.2.5 Beta | عیب‌یابی امن، گزارش خطا و آماده‌سازی برای تست عمومی. |
| v1.2.6 Beta | هشدار برای ویدیوهای از قبل فشرده‌شده و تحلیل بیت‌ریت. |
| v1.2.7 Beta | پاک‌سازی خروجی خراب، ناقص یا کنسل‌شده. |
| v1.2.8 Beta | فشرده‌سازی هوشمندتر برای فایل‌های از قبل فشرده‌شده. |
| v1.2.9 Beta | هدف‌گذاری حجمی هوشمند برای کاهش واقعی‌تر حجم. |
| v1.3.0 Beta | اسلایدر کیفیت گرافیکی. |
| v1.3.1 Beta | دکمه راهنما برای کیفیت GPU و CPU. |
| v1.3.2 Beta | اسلایدر کیفیت CPU. |
| v1.3.3 Beta | اصلاح راست‌به‌چپ پنجره راهنمای فارسی. |
| v1.3.4 Beta | لیست فایل‌های ورودی و تلاش دوباره امن. |
| v1.3.5 Beta | پشتیبانی از FFmpeg لگسی برای درایورهای قدیمی‌تر انویدیا. |

---

## v1.3.5 Beta - Legacy NVIDIA FFmpeg Fallback

### هدف نسخه

این نسخه برای سازگاری بهتر با سیستم‌هایی ساخته شده که کارت گرافیک انویدیا دارند، اما به دلیل قدیمی بودن درایور یا ناسازگاری زمان اجرا، مسیر NVENC با FFmpeg جدید باز نمی‌شود.

### تغییرات

- پشتیبانی از دو پروفایل FFmpeg اضافه شد:
  - `ffmpeg/modern`
  - `ffmpeg/legacy-nvidia`
- اگر انویدیا وجود داشته باشد ولی NVENC با نسخه مدرن خطا بدهد، برنامه نسخه لگسی را تست می‌کند.
- اگر نسخه لگسی موفق باشد، فقط برای NVIDIA NVENC از همان استفاده می‌شود.
- نسخه درایور انویدیا در عیب‌یابی بررسی می‌شود.
- اگر درایور قدیمی باشد، برنامه هشدار می‌دهد.
- اگر درایور خیلی قدیمی باشد، برنامه هشدار جدی می‌دهد که آپدیت درایور لازم است.
- ترتیب fallback بهتر شد: انویدیا مدرن، انویدیا لگسی، اینتل، ای‌ام‌دی، پردازنده.
- در لاگ نوشته می‌شود کدام پروفایل FFmpeg انتخاب شده است.

### ساختار لازم پوشه‌ها

```text
VideoX_Compressor_v1.3.5_Beta_Legacy_NVIDIA_Fallback/
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

---

## v1.3.4 Beta - File Queue & Safe Retry

### هدف نسخه

این نسخه مدیریت فایل‌های ورودی را واضح‌تر کرد و رفتار برنامه هنگام خطای شتاب‌دهنده سخت‌افزاری را بهتر کرد.

### تغییرات

- پنل لیست فایل‌های انتخاب‌شده اضافه شد.
- فایل‌های ورودی قبل از شروع فشرده‌سازی قابل مشاهده هستند.
- کنار هر فایل دکمه `X` برای حذف از لیست ورودی اضافه شد.
- هنگام فشرده‌سازی، تغییر فایل‌ها قفل می‌شود.
- اگر خروجی سخت‌افزاری خراب یا نامعتبر شود، برنامه یک بار با پردازنده دوباره تلاش می‌کند.
- اگر یک یا چند فایل fail شوند، وضعیت نهایی به شکل `Finished with errors` نمایش داده می‌شود.

---

## v1.3.3 Beta - RTL Help Hotfix

- متن فارسی راهنمای کیفیت GPU راست‌به‌چپ شد.
- متن فارسی راهنمای کیفیت CPU راست‌به‌چپ شد.
- عنوان پنجره فارسی راست‌چین شد.
- فونت فارسی به Tahoma تغییر کرد.
- برای جلوگیری از قاطی شدن متن فارسی و انگلیسی از نشانه RTL استفاده شد.

---

## v1.3.2 Beta - CPU CRF Slider

- CPU CRF از فیلد عددی آزاد به اسلایدر تبدیل شد.
- بازه مجاز CPU CRF از 18 تا 45 مشخص شد.
- مقدار فعلی کنار اسلایدر نمایش داده می‌شود.
- با تغییر Preset، اسلایدر هم به‌روزرسانی می‌شود.
- مقدارهای خارج از بازه خودکار اصلاح می‌شوند.

---

## v1.3.1 Beta - Quality Help Buttons

- کنار GPU Quality دکمه `!` اضافه شد.
- کنار CPU CRF دکمه `!` اضافه شد.
- با کلیک روی هرکدام، پنجره راهنمای جداگانه باز می‌شود.
- راهنما توضیح می‌دهد عدد کمتر یا بیشتر چه اثری روی کیفیت و حجم دارد.
- متن راهنما برای فارسی و انگلیسی جداست.

---

## v1.3.0 Beta - GPU Quality Slider

- GPU Quality از فیلد عددی آزاد به اسلایدر تبدیل شد.
- بازه مجاز GPU Quality از 18 تا 45 مشخص شد.
- مقدار فعلی کنار اسلایدر نمایش داده می‌شود.
- با تغییر Preset، اسلایدر هم به‌روزرسانی می‌شود.
- مقدارهای خارج از بازه خودکار اصلاح می‌شوند.

---

## v1.2.9 Beta - Smart Size Target

- برای ویدیوهای از قبل فشرده‌شده، هدف‌گذاری حجمی بهتر شد.
- برنامه فقط با کیفیت آزاد جلو نمی‌رود و می‌تواند بیت‌ریت خروجی را هدف‌گذاری کند.
- هدف عادی حدود نصف حجم است، اگر از نظر کیفیت ممکن باشد.
- در تنظیمات تهاجمی‌تر، حجم کمتر ممکن است، اما ریسک افت کیفیت بیشتر می‌شود.
- رزولوشن به‌صورت خودکار به 480p کاهش داده نمی‌شود.
- اگر FPS روی 0 باشد، نرخ فریم اصلی حفظ می‌شود.
- صدا می‌تواند برای کاهش حجم بیشتر، کم‌حجم‌تر شود.

---

## v1.2.8 Beta - Smart Recompression

- تشخیص ویدیوهای از قبل فشرده‌شده بهتر شد.
- بیت‌ریت ویدیو، بیت‌ریت کل، بیت‌ریت صدا و تراکم فشرده‌سازی بررسی می‌شود.
- در صورت مناسب بودن، برنامه بیت‌ریت ویدیو را با احتیاط پایین‌تر هدف‌گذاری می‌کند.
- ارتفاع تصویر به‌صورت خودکار پایین آورده نمی‌شود تا افت واضح کیفیت کمتر شود.

---

## v1.2.7 Beta - Cleanup Hotfix

- اگر پردازش fail شود، خروجی ناقص پاک می‌شود.
- اگر کاربر Cancel بزند، خروجی نیمه‌کاره پاک می‌شود.
- اگر فایل خروجی ساخته شود ولی با ffprobe معتبر نباشد، حذف می‌شود.
- لاگ‌های قدیمی قبل از شروع پردازش جدید پاک می‌شوند.
- خروجی با مدت زمان و وجود ویدیو استریم بررسی می‌شود.

---

## v1.2.6 Beta - Already-Compressed Warning

- اگر ویدیو از قبل خیلی فشرده باشد، برنامه قبل از شروع هشدار می‌دهد.
- بیت‌ریت ویدیو، بیت‌ریت کل و بیت‌ریت صدا نمایش داده می‌شود.
- بعد از پایان، بیت‌ریت خروجی هم گزارش می‌شود.
- اگر خروجی تقریباً هم‌حجم ورودی باشد، برنامه توضیح می‌دهد که فایل از قبل فشرده بوده یا تنظیمات بیش از حد کیفیت را حفظ کرده‌اند.

---

## v1.2.5 Beta - General Safe Diagnostics

- حالت General Safe Mode اضافه شد.
- گزارش عیب‌یابی خودکار هنگام خطا اضافه شد.
- دکمه Export Bug Report اضافه شد.
- دکمه Open Logs اضافه شد.
- GPU Diagnostics با خروجی ذخیره‌شونده اضافه شد.
- انتخاب شتاب‌دهنده سخت‌افزاری بهتر شد.
- لاگ‌ها شامل تاریخ، مشخصات سیستم، اطلاعات شتاب‌دهنده، تنظیمات و خطاهای FFmpeg شدند.

---

## تنظیمات پیشنهادی

### برای بیشتر کاربران

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

### برای لپتاپ‌های قدیمی‌تر انویدیا

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
Output Format: mp4
```

بعد از آن GPU Diagnostics را اجرا کنید. اگر NVENC مدرن خطا بدهد و مسیر لگسی موفق شود، برنامه می‌تواند از FFmpeg لگسی انویدیا استفاده کند.

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

---

## فعال‌سازی

1. کد دستگاه را کپی کنید.
2. آن را در تلگرام به آیدی زیر ارسال کنید.

```text
@thelouis_mahdi
```

3. فایل `license.key` مخصوص همان دستگاه را دریافت کنید.
4. فایل لایسنس را کنار `VideoX.exe` قرار دهید یا از داخل برنامه انتخاب کنید.
5. روی Recheck بزنید و وارد برنامه شوید.

لایسنس مخصوص همان دستگاه است و روی دستگاه دیگر فعال نمی‌شود.

---

## نکات مهم

- این نسخه در مرحله بتا قرار دارد.
- بهترین نتیجه فعلی روی ویدیوهای کم‌تحرک انتظار می‌رود.
- نتیجه فشرده‌سازی به نوع ویدیو، بیت‌ریت، میزان حرکت تصویر، رزولوشن، سخت‌افزار و تنظیمات بستگی دارد.
- اگر شتاب‌دهنده سخت‌افزاری در دسترس نباشد، برنامه با پردازنده ادامه می‌دهد.
- FFmpeg لگسی فقط وقتی استفاده می‌شود که مسیر مدرن انویدیا خطا بدهد و مسیر لگسی تست زمان اجرا را پاس کند.
- برای درایورهای خیلی قدیمی انویدیا، آپدیت درایور همچنان پیشنهاد می‌شود.
- پوشه‌های `ffmpeg` و `_internal` را حذف نکنید.
- فایل `license.key` را داخل بسته عمومی منتشر نکنید.

</div>
