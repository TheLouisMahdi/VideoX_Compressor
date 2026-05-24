# VideoX Compressor - Release Notes

## Current Public Beta

```text
VideoX Compressor v1.4.0 Beta - Pipeline Clarity Update
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
| v1.3.7 Beta | Manual GPU Preference selection. | Supported history |
| v1.3.8 Beta | Dynamic GPU Preference filtering. | Supported history |
| v1.3.9 Beta | NVENC runtime test fix for hybrid laptops. | Supported history |
| v1.4.0 Beta | Pipeline Clarity Update. | Current recommended beta |

---

# English Release Notes

## v1.4.0 Beta - Pipeline Clarity Update

### Main Goal

Version `v1.4.0` keeps the stable `v1.3.9` compression logic and improves the user interface explanations around the real video-processing pipeline.

This release does **not** redesign the stable compression workflow. It clarifies what the main hardware-related settings actually do so users can better understand whether VideoX is using CPU decode, hardware decode, CPU scaling, CUDA scaling, GPU encoding or CPU encoding.

### What Was Preserved From v1.3.9

- Stable v1.3.9 compression workflow.
- Dynamic GPU Preference filtering.
- NVENC runtime test fix for hybrid laptops.
- Legacy NVIDIA FFmpeg fallback.
- Modern FFmpeg and legacy NVIDIA FFmpeg profiles.
- File queue panel and removable input list.
- Safe retry behavior.
- Output validation and cleanup.
- GPU Quality slider.
- CPU CRF slider.
- General Safe Mode and diagnostic reports.
- English-only logs and error messages inside the program.

### New / Improved in v1.4.0

- Added clearer UI hints for `Performance Mode`.
- Added clearer UI hints for `Processing Strategy`.
- Added clearer UI hints for `Hardware Decode`.
- Added a `Pipeline Preview` label in the UI.
- Pipeline Preview explains the expected path:
  - Decode
  - Scale
  - Encode
- The preview updates when these settings change:
  - Performance Mode
  - Processing Strategy
  - GPU Preference
  - Hardware Decode
  - Output Format
- UI now explains that `Hardware Decode: Off` is the safest mode and can still use GPU encoding.
- UI now explains that `High Throughput` mainly helps when processing multiple files, not necessarily one single file.
- UI now explains that `Maximum Hardware Acceleration` is most meaningful for NVIDIA with `Hardware Decode: Aggressive`.
- UI now explains that AMD AMF and Intel QSV usually mean GPU encoding while scaling may still remain CPU-based.

### Pipeline Control Details

#### Performance Mode

| Option | Real Effect |
|---|---|
| Stable | Safer mode. Usually processes one hardware job at a time. |
| High Throughput | May allow up to 2 hardware jobs in parallel when hardware acceleration is available. |

Important notes:

- This option does not directly change output quality.
- It may not make a single file faster.
- It can increase GPU/CPU load when several files are queued.

#### Processing Strategy

| Option | Real Effect |
|---|---|
| Auto Balanced | Recommended default. Uses hardware encoding when available while keeping safer behavior. |
| Maximum Hardware Acceleration | Tries to move more of the pipeline to hardware. Most meaningful for NVIDIA + Aggressive Hardware Decode. |
| CPU Only | Disables GPU encoding and forces CPU encoding. |

Important notes:

- On NVIDIA with Aggressive Hardware Decode, this can use CUDA decode and CUDA scaling.
- On AMD AMF or Intel QSV, it usually still means GPU encode with CPU scaling.
- CPU Only overrides GPU Preference.

#### Hardware Decode

| Option | Decode | Scale | Encode |
|---|---|---|---|
| Off | CPU | CPU | GPU or CPU depending on selected encoder |
| Auto | FFmpeg hardware auto when possible | Usually CPU | GPU or CPU depending on selected encoder |
| Aggressive | Mainly NVIDIA CUDA when NVIDIA is selected | NVIDIA CUDA only in NVIDIA + Maximum Hardware Acceleration mode | NVIDIA NVENC |

Important notes:

- `Hardware Decode: Off` is the safest mode.
- `Hardware Decode: Off` does **not** mean GPU encoding is disabled.
- `Hardware Decode: Aggressive` is mainly useful on NVIDIA systems.
- If aggressive decode/scale fails, VideoX can retry using a safer path.

### Example Pipeline Preview

```text
Decode: CPU | Scale: CPU | Encode: hevc_amf / AMD
```

```text
Decode: NVIDIA CUDA | Scale: NVIDIA CUDA | Encode: hevc_nvenc / NVIDIA
```

This makes it easier to understand whether the selected settings are using full GPU pipeline or only GPU encoding.

### Recommended Settings

For most users:

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

For stronger NVIDIA systems when testing maximum acceleration:

```text
Performance Mode: High Throughput
Processing Strategy: Maximum Hardware Acceleration
Hardware Decode: Aggressive
GPU Preference: NVIDIA NVENC
```

If errors happen, return to:

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
Hardware Decode: Off
```

### Required Package Structure

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

---

## v1.3.9 Beta - NVENC Runtime Test Fix

### Main Goal

Version `v1.3.9` fixed an important hardware-detection issue found after testing `v1.3.8` on a hybrid laptop with **AMD + NVIDIA RTX 4060 Laptop GPU**.

The NVIDIA GPU was detected correctly, the NVIDIA driver was current, and FFmpeg listed `hevc_nvenc` and `h264_nvenc`, but the runtime test failed. As a result, VideoX did not show NVIDIA in GPU Preference and selected AMD AMF instead.

### Fixed in v1.3.9

- Updated NVENC runtime test dimensions.
- Runtime test now uses a safer HD-sized test input.
- Runtime test uses `1280x720` instead of a very small frame.
- Runtime test uses a more compatible pixel format for NVENC.
- NVIDIA NVENC should appear in GPU Preference when it actually works.
- Dynamic GPU Preference filtering from v1.3.8 was preserved.
- Manual GPU Preference selection from v1.3.7 was preserved.
- Stable Legacy NVIDIA FFmpeg fallback from v1.3.6 was preserved.

---

## v1.3.8 Beta - Dynamic GPU Preference & Runtime Filtering

- Added dynamic GPU Preference filtering.
- GPU Preference list shows only hardware paths that pass runtime tests.
- Always keeps `Auto Best Available` and `CPU Only`.
- Shows `NVIDIA NVENC`, `Intel QSV` or `AMD AMF` only if the related runtime test passes.
- Hardware status text above the progress bar updates when GPU Preference changes.

---

## v1.3.7 Beta - GPU Preference Selection

- Added GPU Preference option to the UI.
- User can choose between available processing preferences:
  - Auto Best Available
  - NVIDIA NVENC
  - Intel QSV
  - AMD AMF
  - CPU Only
- NVIDIA preference tests modern NVENC first, then Legacy NVIDIA FFmpeg if needed.
- CPU Only disables hardware encoding.

---

## v1.3.6 Beta - Stable Legacy FFmpeg Fallback

Version `v1.3.6` replaced the unstable `v1.3.5` build.

The goal was to keep the stable behavior of `v1.3.4 File Queue & Safe Retry` and add Legacy NVIDIA FFmpeg fallback without breaking the UI, logs, buttons or compression workflow.

### Important Notice About v1.3.5

Version `v1.3.5 Beta - Legacy NVIDIA FFmpeg Fallback` was removed / deprecated because it was not stable enough for public use.

Known problems in v1.3.5 included:

- Some UI buttons and controls were missing compared to v1.3.4.
- Log behavior was not consistent with v1.3.4.
- Compression behavior was not reliable enough.
- The implementation changed more than intended instead of only adding Legacy FFmpeg fallback.

---

## v1.3.4 Beta - File Queue & Safe Retry

- Added visible file queue panel.
- Selected files are shown before compression.
- Each selected file has an `X` button for removal before starting.
- Input changes are locked while compression is running.
- Added safe retry behavior for hardware encoder failures.
- If hardware output fails or becomes invalid, VideoX can retry the same file once with CPU fallback.
- If one or more files fail, the final status is shown as `Finished with errors` instead of simply `Finished`.

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
- Hardware acceleration depends on GPU model, driver, FFmpeg support and selected output format.
- If hardware acceleration is not available, the app falls back to CPU mode.
- Legacy NVIDIA FFmpeg is only used when modern NVIDIA NVENC fails and the legacy path passes runtime tests.
- Very old NVIDIA drivers should still be updated when possible.
- Do not delete the `ffmpeg` folder.
- Do not delete the `_internal` folder.
- Do not include `license.key` inside the public ZIP package.

---

# یادداشت‌های انتشار فارسی

<div dir="rtl" align="right">

## نسخه فعلی عمومی

```text
VideoX Compressor v1.4.0 Beta - Pipeline Clarity Update
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
| v1.3.7 Beta | انتخاب دستی GPU Preference. | تاریخچه پشتیبانی‌شده |
| v1.3.8 Beta | فیلتر پویا برای GPU Preference. | تاریخچه پشتیبانی‌شده |
| v1.3.9 Beta | اصلاح تست Runtime برای NVENC. | تاریخچه پشتیبانی‌شده |
| v1.4.0 Beta | شفاف‌سازی مسیر Decode / Scale / Encode. | نسخه پیشنهادی فعلی |

---

## v1.4.0 Beta - Pipeline Clarity Update

### هدف نسخه

نسخه `v1.4.0` منطق پایدار نسخه `v1.3.9` را حفظ می‌کند و توضیحات رابط کاربری را برای تنظیمات مربوط به مسیر پردازش ویدیو بهتر می‌کند.

هدف این نسخه این است که کاربر دقیق‌تر بفهمد گزینه‌های `Performance Mode`، `Processing Strategy` و `Hardware Decode` واقعاً چه چیزی را تغییر می‌دهند.

### موارد حفظ‌شده از v1.3.9

- مسیر فشرده‌سازی پایدار v1.3.9.
- فیلتر پویا GPU Preference.
- اصلاح تست Runtime برای NVENC روی لپتاپ‌های دو گرافیکه.
- FFmpeg لگسی انویدیا.
- صف فایل‌ها و دکمه حذف فایل.
- تلاش دوباره امن.
- بررسی و پاک‌سازی خروجی خراب.
- اسلایدرهای GPU Quality و CPU CRF.
- گزارش عیب‌یابی.

### تغییرات اضافه‌شده در v1.4.0

- توضیح دقیق‌تر برای `Performance Mode`.
- توضیح دقیق‌تر برای `Processing Strategy`.
- توضیح دقیق‌تر برای `Hardware Decode`.
- اضافه شدن `Pipeline Preview` در رابط کاربری.
- نمایش مسیر تقریبی:
  - Decode
  - Scale
  - Encode
- توضیح اینکه `Hardware Decode: Off` امن‌ترین حالت است و همچنان می‌تواند از GPU برای Encode استفاده کند.
- توضیح اینکه `High Throughput` بیشتر برای پردازش چند فایل همزمان است.
- توضیح اینکه `Maximum Hardware Acceleration` بیشترین اثر را روی NVIDIA همراه با `Hardware Decode: Aggressive` دارد.
- توضیح اینکه در AMD AMF و Intel QSV معمولاً Encode روی GPU است ولی Scale می‌تواند روی CPU باقی بماند.

### توضیح گزینه‌ها

#### Performance Mode

| گزینه | اثر واقعی |
|---|---|
| Stable | حالت امن‌تر؛ معمولاً یک پردازش سخت‌افزاری همزمان انجام می‌دهد. |
| High Throughput | در صورت وجود شتاب‌دهنده مناسب، ممکن است تا دو پردازش همزمان را فعال کند. |

نکته: این گزینه مستقیماً کیفیت خروجی را تغییر نمی‌دهد و ممکن است یک فایل تکی را سریع‌تر نکند.

#### Processing Strategy

| گزینه | اثر واقعی |
|---|---|
| Auto Balanced | حالت پیشنهادی؛ از سخت‌افزار برای Encode استفاده می‌کند ولی مسیر امن‌تر را حفظ می‌کند. |
| Maximum Hardware Acceleration | تلاش می‌کند بخش بیشتری از مسیر را سخت‌افزاری کند؛ بیشترین اثر را روی NVIDIA + Aggressive دارد. |
| CPU Only | پردازش گرافیکی برای Encode را غیرفعال می‌کند و برنامه با CPU ادامه می‌دهد. |

#### Hardware Decode

| گزینه | Decode | Scale | Encode |
|---|---|---|---|
| Off | CPU | CPU | GPU یا CPU بسته به Encoder انتخاب‌شده |
| Auto | تلاش خودکار FFmpeg برای Decode سخت‌افزاری | معمولاً CPU | GPU یا CPU |
| Aggressive | عمدتاً NVIDIA CUDA وقتی NVIDIA انتخاب شده باشد | فقط در NVIDIA + Maximum Hardware Acceleration می‌تواند CUDA Scale شود | NVIDIA NVENC |

نکته: خاموش بودن Hardware Decode به معنی خاموش شدن GPU Encode نیست.

### نمونه Pipeline Preview

```text
Decode: CPU | Scale: CPU | Encode: hevc_amf / AMD
```

```text
Decode: NVIDIA CUDA | Scale: NVIDIA CUDA | Encode: hevc_nvenc / NVIDIA
```

---

## v1.3.9 Beta - NVENC Runtime Test Fix

نسخه `v1.3.9` مشکل پنهان شدن اشتباه NVIDIA را اصلاح کرد. در بعضی لپتاپ‌های دو گرافیکه، کارت انویدیا و درایور به‌درستی تشخیص داده می‌شدند، اما تست داخلی به دلیل کوچک بودن فریم تست خطا می‌داد و برنامه به اشتباه NVIDIA را از لیست GPU Preference حذف می‌کرد.

اصلاحات:

- تست Runtime برای NVENC با ابعاد امن‌تر انجام شد.
- تست از `1280x720` استفاده کرد.
- فرمت پیکسلی سازگارتر برای NVENC استفاده شد.
- اگر NVIDIA واقعاً قابل استفاده باشد، باید در GPU Preference نمایش داده شود.

---

## v1.3.8 Beta - Dynamic GPU Preference

- فقط مسیرهایی نمایش داده می‌شوند که تست Runtime را پاس کنند.
- گزینه‌های Auto و CPU Only همیشه باقی می‌مانند.
- گزینه‌های NVIDIA، Intel و AMD فقط در صورت موفق بودن تست واقعی نمایش داده می‌شوند.
- متن وضعیت سخت‌افزار با تغییر GPU Preference به‌روزرسانی می‌شود.

---

## v1.3.7 Beta - GPU Preference Selection

- گزینه GPU Preference به رابط کاربری اضافه شد.
- کاربر می‌تواند Auto، NVIDIA، Intel، AMD یا CPU Only را انتخاب کند.
- حالت CPU Only همه مسیرهای GPU را برای Encode غیرفعال می‌کند.

---

## v1.3.6 Beta - Stable Legacy FFmpeg Fallback

نسخه `v1.3.6` جایگزین نسخه ناپایدار `v1.3.5` شد. این نسخه بر پایه `v1.3.4` ساخته شد و قابلیت FFmpeg لگسی انویدیا را بدون خراب شدن رابط کاربری، لاگ‌ها و مسیر فشرده‌سازی اضافه کرد.

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
- برای درایورهای خیلی قدیمی انویدیا، آپدیت درایور همچنان پیشنهاد می‌شود.
- پوشه‌های `ffmpeg` و `_internal` را حذف نکنید.
- فایل `license.key` را داخل بسته عمومی منتشر نکنید.

</div>
