# VideoX Compressor - Release Notes

## Current Public Beta

```text
VideoX Compressor v1.3.9 Beta - NVENC Runtime Test Fix
```

VideoX Compressor is a Windows video compression application focused on simple, practical and hardware-accelerated compression for recorded classes, tutorials, screen recordings, online meetings, low-motion lecture videos and everyday videos that need smaller file size.

The project is still in **Beta**. The strongest current results are usually on low-motion educational videos and screen recordings. Results depend on source video type, bitrate, motion level, resolution, hardware, driver version and selected settings.

---

## Version Timeline

| Version | Release Focus | Status |
|---|---|---|
| v1.2.5 Beta | General Safe Diagnostics, bug reports, safer public testing. | Supported history |
| v1.2.6 Beta | Already-compressed video warning and bitrate analysis. | Supported history |
| v1.2.7 Beta | Cleanup of failed, cancelled or corrupted output files. | Supported history |
| v1.2.8 Beta | Smart Recompression for already-compressed sources. | Supported history |
| v1.2.9 Beta | Smart Size Target for better real size reduction. | Supported history |
| v1.3.0 Beta | GPU Quality slider. | Supported history |
| v1.3.1 Beta | Help buttons for GPU Quality and CPU CRF. | Supported history |
| v1.3.2 Beta | CPU CRF slider. | Supported history |
| v1.3.3 Beta | RTL Persian help popup fix. | Supported history |
| v1.3.4 Beta | File queue panel and safe retry behavior. | Stable base |
| v1.3.5 Beta | Legacy NVIDIA FFmpeg fallback attempt. | Deprecated / removed because it was not stable |
| v1.3.6 Beta | Stable Legacy FFmpeg Fallback rebuilt on v1.3.4. | Stable base with legacy fallback |
| v1.3.7 Beta | Manual GPU Preference selection. | Superseded by v1.3.8 |
| v1.3.8 Beta | Dynamic GPU Preference filtering. | Superseded by v1.3.9 |
| v1.3.9 Beta | NVENC runtime test fix for hybrid laptops. | Current recommended beta |

---

# English Release Notes

## v1.3.9 Beta - NVENC Runtime Test Fix

### Main Goal

Version `v1.3.9` fixes an important hardware-detection issue found after testing `v1.3.8` on a hybrid laptop with **AMD + NVIDIA RTX 4060 Laptop GPU**.

The NVIDIA GPU was detected correctly, the NVIDIA driver was current, and FFmpeg listed `hevc_nvenc` and `h264_nvenc`, but the runtime test failed. As a result, VideoX did not show NVIDIA in GPU Preference and selected AMD AMF instead.

### Root Cause

The internal NVENC runtime test used a very small synthetic test frame.

Some NVIDIA NVENC paths, especially on hybrid laptops or with certain FFmpeg/NVIDIA runtime combinations, reject very small frame dimensions during encoder initialization.

This made VideoX think that NVIDIA NVENC was unusable even when the NVIDIA GPU and driver were valid.

### Fixed in v1.3.9

- Updated NVENC runtime test dimensions.
- Runtime test now uses a safer HD-sized test input.
- Runtime test uses `1280x720` instead of a very small frame.
- Runtime test uses a more compatible pixel format for NVENC.
- NVIDIA NVENC should now appear in GPU Preference when it actually works.
- The app should no longer incorrectly hide NVIDIA only because the test frame was too small.
- Dynamic GPU Preference filtering from v1.3.8 is preserved.
- Manual GPU Preference selection from v1.3.7 is preserved.
- Stable Legacy NVIDIA FFmpeg fallback from v1.3.6 is preserved.
- v1.3.4 UI, file queue, logs and compression workflow are preserved.

### Expected Behavior After the Fix

On a valid NVIDIA system, VideoX should be able to show:

```text
Auto Best Available
NVIDIA NVENC
AMD AMF
CPU Only
```

or, depending on the system:

```text
Auto Best Available
NVIDIA NVENC
Intel QSV
CPU Only
```

The exact list depends on runtime tests. VideoX should only show hardware options that pass a real encoder test.

### Notes for Hybrid GPU Laptops

On laptops with two GPUs, Windows may still route processes differently depending on system settings.

For best results, set these files to **High Performance** in Windows Graphics Settings:

```text
VideoX.exe
ffmpeg/modern/bin/ffmpeg.exe
ffmpeg/legacy-nvidia/bin/ffmpeg.exe
```

NVIDIA Control Panel alone may not be enough because the actual encoding process is performed by `ffmpeg.exe`.

---

## v1.3.8 Beta - Dynamic GPU Preference & Runtime Filtering

### Main Goal

Version `v1.3.8` improved GPU selection on systems with multiple graphics devices.

### New Features

- Added dynamic GPU Preference filtering.
- GPU Preference list shows only hardware paths that pass runtime tests.
- Always keeps:
  - `Auto Best Available`
  - `CPU Only`
- Shows `NVIDIA NVENC` only if NVENC passes runtime tests.
- Shows `Intel QSV` only if QSV passes runtime tests.
- Shows `AMD AMF` only if AMF passes runtime tests.
- The hardware status text above the progress bar updates when GPU Preference changes.
- The status text shows selected encoder, vendor and FFmpeg profile.
- Saved GPU Preference automatically falls back to Auto if that hardware is not available on the current system.

---

## v1.3.7 Beta - GPU Preference Selection

### Main Goal

Version `v1.3.7` added manual GPU Preference selection for systems where Auto mode did not pick the desired hardware path.

### New Features

- Added GPU Preference option to the UI.
- User can choose between available processing preferences:
  - Auto Best Available
  - NVIDIA NVENC
  - Intel QSV
  - AMD AMF
  - CPU Only
- Auto mode keeps the previous automatic hardware selection behavior.
- NVIDIA preference tests modern NVENC first, then Legacy NVIDIA FFmpeg if needed.
- Intel preference tests Intel QSV directly.
- AMD preference tests AMD AMF directly.
- CPU Only disables hardware encoding.
- Logs selected preference, selected encoder, vendor, FFmpeg profile and whether Legacy NVIDIA was used.

---

## v1.3.6 Beta - Stable Legacy FFmpeg Fallback

### Main Goal

Version `v1.3.6` replaced the unstable `v1.3.5` build.

The goal of this release was to keep the stable behavior of `v1.3.4 File Queue & Safe Retry` and add Legacy NVIDIA FFmpeg fallback without breaking the UI, logs, buttons or compression workflow.

### Important Notice About v1.3.5

Version `v1.3.5 Beta - Legacy NVIDIA FFmpeg Fallback` was removed / deprecated because it was not stable enough for public use.

Known problems in the v1.3.5 build included:

- Some UI buttons and controls were missing compared to v1.3.4.
- Log behavior was not consistent with the stable v1.3.4 version.
- Compression behavior was not reliable enough.
- The implementation changed more than intended instead of only adding Legacy FFmpeg fallback.

For this reason, `v1.3.6` and later builds should be used instead of `v1.3.5`.

### What Was Preserved From v1.3.4

- Stable v1.3.4 UI layout.
- File queue panel.
- Removable input files with `X` button before compression.
- Compression workflow from v1.3.4.
- GPU Quality slider.
- CPU CRF slider.
- `!` help buttons for quality settings.
- RTL Persian help popup fix.
- Smart Size Target.
- Already-compressed video warning.
- Output validation.
- Failed / invalid / cancelled output cleanup.
- Safe retry behavior.
- Final report behavior.
- General Safe Mode and diagnostic reports.

### New / Improved in v1.3.6

- Added stable support for two FFmpeg profiles:
  - `ffmpeg/modern`
  - `ffmpeg/legacy-nvidia`
- Modern FFmpeg is tested first.
- If NVIDIA GPU is detected but modern NVENC fails, VideoX tests the Legacy NVIDIA FFmpeg build.
- If Legacy NVIDIA FFmpeg passes the runtime test, it can be used only for NVIDIA NVENC encoding.
- If both modern and legacy NVENC fail, VideoX falls back to Intel QSV, AMD AMF or CPU mode.
- Added clearer GPU Diagnostics output for FFmpeg profiles.
- Added NVIDIA driver version diagnostics.
- Added warning for old NVIDIA drivers.
- Added stronger warning for very old NVIDIA drivers.
- Logs which FFmpeg profile is selected.
- Keeps the stable v1.3.4 compression pipeline intact.
- Avoids removing useful recent logs too aggressively; recent logs are kept for troubleshooting.

---

## v1.3.5 Beta - Legacy NVIDIA FFmpeg Fallback

### Status

```text
Deprecated / Removed
```

### Reason

Version `v1.3.5` was an attempt to add Legacy NVIDIA FFmpeg fallback, but it was not stable enough. It introduced regressions compared to the stable `v1.3.4` build.

The version is documented here for transparency, but it is not recommended for release or public distribution.

---

## v1.3.4 Beta - File Queue & Safe Retry

### Main Goal

This version improved file handling, made selected input files visible to users and improved behavior when hardware encoding failed during compression.

### New Features

- Added visible file queue panel.
- Selected files are shown before compression.
- Each selected file has an `X` button for removal before starting.
- Input changes are locked while compression is running.
- Added safe retry behavior for hardware encoder failures.
- If hardware output fails or becomes invalid, VideoX can retry the same file once with CPU fallback.
- If one or more files fail, the final status is shown as `Finished with errors` instead of simply `Finished`.

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
GPU Preference: Auto Best Available
GPU Quality: 32 to 36
CPU CRF: 30 to 34
```

## Hybrid GPU Laptops

For laptops with integrated graphics plus NVIDIA, Intel or AMD dedicated GPU:

```text
GPU Preference: Auto Best Available
```

If Auto does not choose the desired path, select the detected hardware manually:

```text
GPU Preference: NVIDIA NVENC
GPU Preference: Intel QSV
GPU Preference: AMD AMF
GPU Preference: CPU Only
```

Only hardware options that pass runtime tests should appear in the list.

## Older NVIDIA Laptops

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Workers: 1
Output Format: mp4
GPU Preference: Auto Best Available or NVIDIA NVENC
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

# Required Package Structure

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
VideoX Compressor v1.3.9 Beta - NVENC Runtime Test Fix
```

ویدیو ایکس کامپرسور یک برنامه ویندوزی برای فشرده‌سازی ویدیو است. تمرکز برنامه روی فشرده‌سازی ساده، کاربردی و در صورت امکان شتاب‌داده‌شده با سخت‌افزار است.

برنامه هنوز در وضعیت **بتا** قرار دارد. بهترین نتیجه فعلی معمولاً روی کلاس‌های ضبط‌شده، آموزش‌ها، اسکرین‌ریکوردها، جلسات آنلاین و ویدیوهای کم‌تحرک دیده می‌شود.

---

## جدول نسخه‌ها

| نسخه | تمرکز اصلی | وضعیت |
|---|---|---|
| v1.2.5 Beta | عیب‌یابی امن، گزارش خطا و آماده‌سازی برای تست عمومی. | تاریخچه پشتیبانی‌شده |
| v1.2.6 Beta | هشدار برای ویدیوهای از قبل فشرده‌شده و تحلیل بیت‌ریت. | تاریخچه پشتیبانی‌شده |
| v1.2.7 Beta | پاک‌سازی خروجی خراب، ناقص یا کنسل‌شده. | تاریخچه پشتیبانی‌شده |
| v1.2.8 Beta | فشرده‌سازی هوشمندتر برای فایل‌های از قبل فشرده‌شده. | تاریخچه پشتیبانی‌شده |
| v1.2.9 Beta | هدف‌گذاری حجمی هوشمند برای کاهش واقعی‌تر حجم. | تاریخچه پشتیبانی‌شده |
| v1.3.0 Beta | اسلایدر کیفیت گرافیکی. | تاریخچه پشتیبانی‌شده |
| v1.3.1 Beta | دکمه راهنما برای کیفیت GPU و CPU. | تاریخچه پشتیبانی‌شده |
| v1.3.2 Beta | اسلایدر کیفیت CPU. | تاریخچه پشتیبانی‌شده |
| v1.3.3 Beta | اصلاح راست‌به‌چپ پنجره راهنمای فارسی. | تاریخچه پشتیبانی‌شده |
| v1.3.4 Beta | لیست فایل‌های ورودی و تلاش دوباره امن. | پایه پایدار |
| v1.3.5 Beta | تلاش اولیه برای FFmpeg لگسی انویدیا. | حذف‌شده / ناپایدار |
| v1.3.6 Beta | نسخه پایدار قابلیت FFmpeg لگسی بر پایه v1.3.4. | پایه پایدار با قابلیت لگسی |
| v1.3.7 Beta | انتخاب دستی GPU Preference. | جایگزین‌شده با v1.3.8 |
| v1.3.8 Beta | فیلتر پویا برای GPU Preference. | جایگزین‌شده با v1.3.9 |
| v1.3.9 Beta | اصلاح تست Runtime برای NVENC. | نسخه پیشنهادی فعلی |

---

## v1.3.9 Beta - NVENC Runtime Test Fix

### هدف نسخه

نسخه `v1.3.9` یک مشکل مهم در تشخیص کارت گرافیک انویدیا را که بعد از تست نسخه `v1.3.8` روی لپتاپ‌های هیبریدی دیده شد، اصلاح می‌کند.

در یک سیستم دارای AMD و NVIDIA RTX 4060 Laptop GPU، کارت انویدیا، درایور و انکودرهای `hevc_nvenc` و `h264_nvenc` دیده می‌شدند، اما تست زمان اجرای NVENC خطا می‌داد و برنامه به اشتباه NVIDIA را از لیست GPU Preference حذف می‌کرد و AMD AMF را انتخاب می‌کرد.

### علت مشکل

تست داخلی NVENC با ابعاد تصویر بسیار کوچک انجام می‌شد.

بعضی مسیرهای NVIDIA NVENC، مخصوصاً روی لپتاپ‌های دو گرافیکه یا در بعضی ترکیب‌های FFmpeg و درایور NVIDIA، ابعاد خیلی کوچک را برای شروع انکودر قبول نمی‌کنند.

در نتیجه برنامه تصور می‌کرد NVIDIA NVENC قابل استفاده نیست، در حالی که مشکل از طراحی تست بود.

### اصلاحات نسخه v1.3.9

- ابعاد تست Runtime برای NVENC اصلاح شد.
- تست داخلی حالا از ورودی HD امن‌تر استفاده می‌کند.
- تست به جای فریم خیلی کوچک، از `1280x720` استفاده می‌کند.
- فرمت پیکسلی سازگارتر برای NVENC استفاده می‌شود.
- اگر NVIDIA واقعاً قابل استفاده باشد، باید در GPU Preference نمایش داده شود.
- برنامه دیگر نباید فقط به خاطر کوچک بودن فریم تست، NVIDIA را پنهان کند.
- فیلتر پویا GPU Preference از v1.3.8 حفظ شد.
- انتخاب دستی GPU Preference از v1.3.7 حفظ شد.
- FFmpeg لگسی انویدیا از v1.3.6 حفظ شد.
- رابط کاربری، صف فایل، لاگ‌ها و مسیر فشرده‌سازی پایدار v1.3.4 حفظ شد.

### رفتار مورد انتظار بعد از اصلاح

روی سیستم NVIDIA معتبر، برنامه باید بتواند گزینه NVIDIA را در لیست نشان دهد؛ مثلاً:

```text
Auto Best Available
NVIDIA NVENC
AMD AMF
CPU Only
```

یا بسته به سخت‌افزار:

```text
Auto Best Available
NVIDIA NVENC
Intel QSV
CPU Only
```

لیست دقیق به تست زمان اجرا بستگی دارد و برنامه فقط گزینه‌هایی را نشان می‌دهد که تست واقعی را پاس کنند.

### نکته برای لپتاپ‌های دو گرافیکه

روی لپتاپ‌هایی که دو کارت گرافیک دارند، ویندوز ممکن است پردازش را طبق تنظیمات خودش بین گرافیک‌ها جابه‌جا کند.

برای نتیجه بهتر، این فایل‌ها را در Windows Graphics Settings روی High Performance قرار دهید:

```text
VideoX.exe
ffmpeg/modern/bin/ffmpeg.exe
ffmpeg/legacy-nvidia/bin/ffmpeg.exe
```

تنظیم NVIDIA Control Panel به تنهایی همیشه کافی نیست؛ چون پردازش اصلی توسط `ffmpeg.exe` انجام می‌شود.

---

## v1.3.8 Beta - Dynamic GPU Preference & Runtime Filtering

- فیلتر پویا برای GPU Preference اضافه شد.
- در لیست GPU Preference فقط مسیرهایی نمایش داده می‌شوند که تست Runtime را پاس کنند.
- گزینه‌های `Auto Best Available` و `CPU Only` همیشه باقی می‌مانند.
- گزینه‌های NVIDIA، Intel یا AMD فقط در صورت موفق بودن تست واقعی نمایش داده می‌شوند.
- متن وضعیت سخت‌افزار بالای Progress Bar با تغییر GPU Preference به‌روزرسانی می‌شود.
- اگر تنظیم ذخیره‌شده قبلی روی سیستم جدید در دسترس نباشد، برنامه به Auto برمی‌گردد.

---

## v1.3.7 Beta - GPU Preference Selection

- گزینه GPU Preference به رابط کاربری اضافه شد.
- کاربر می‌تواند مسیر پردازش را انتخاب کند:
  - Auto Best Available
  - NVIDIA NVENC
  - Intel QSV
  - AMD AMF
  - CPU Only
- حالت Auto مثل قبل بهترین مسیر قابل استفاده را انتخاب می‌کند.
- اگر NVIDIA انتخاب شود، ابتدا NVENC مدرن و سپس در صورت نیاز مسیر لگسی تست می‌شود.
- اگر Intel یا AMD انتخاب شود، همان مسیر مستقیم تست می‌شود.
- حالت CPU Only تمام مسیرهای GPU را غیرفعال می‌کند.

---

## v1.3.6 Beta - Stable Legacy FFmpeg Fallback

نسخه `v1.3.6` جایگزین نسخه ناپایدار `v1.3.5` شد.

این نسخه بر پایه رفتار پایدار `v1.3.4 File Queue & Safe Retry` ساخته شد و قابلیت FFmpeg لگسی انویدیا را بدون خراب شدن رابط کاربری، لاگ‌ها، دکمه‌ها یا مسیر فشرده‌سازی اضافه کرد.

موارد مهم حفظ‌شده از v1.3.4:

- رابط کاربری پایدار.
- لیست فایل‌های ورودی.
- دکمه حذف فایل با `X`.
- اسلایدرهای کیفیت GPU و CPU.
- دکمه‌های راهنما.
- اصلاح راست‌به‌چپ فارسی.
- Smart Size Target.
- بررسی خروجی و پاک‌سازی فایل خراب.
- تلاش دوباره امن.
- گزارش نهایی و گزارش عیب‌یابی.

موارد اضافه‌شده:

- پشتیبانی از `ffmpeg/modern` و `ffmpeg/legacy-nvidia`.
- تست نسخه لگسی اگر NVENC مدرن خطا بدهد.
- بررسی نسخه درایور انویدیا.
- هشدار برای درایور قدیمی یا خیلی قدیمی.
- نمایش پروفایل FFmpeg انتخاب‌شده در لاگ.

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
GPU Preference: Auto Best Available
GPU Quality: 32 to 36
CPU CRF: 30 to 34
```

### برای لپتاپ‌های دو گرافیکه

ابتدا این حالت را تست کنید:

```text
GPU Preference: Auto Best Available
```

اگر Auto مسیر موردنظر را انتخاب نکرد، یکی از گزینه‌های موجود را دستی انتخاب کنید:

```text
GPU Preference: NVIDIA NVENC
GPU Preference: Intel QSV
GPU Preference: AMD AMF
GPU Preference: CPU Only
```

فقط گزینه‌هایی نمایش داده می‌شوند که تست Runtime را پاس کنند.

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

## ساختار لازم پوشه‌ها

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
