# VideoX Compressor - Release Notes

## Current Public Beta

```text
VideoX Compressor v1.4.4 Beta - Stable Device ID
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
| v1.4.0 Beta | Pipeline Clarity Update. | Supported history |
| v1.4.1 Beta | Simple and Advanced Mode. | Supported history |
| v1.4.2 Beta | Simple Safe Mode and no-upscale protection. | Supported history |
| v1.4.3 Beta | Simple FPS Tuning. | Supported history |
| v1.4.4 Beta | Stable Device ID. | Current recommended beta |

---

# English Release Notes

## v1.4.4 Beta - Stable Device ID

### Main Goal

Version `v1.4.4` keeps the latest stable Python beta behavior and fixes the Device ID instability issue.

Older beta builds could sometimes generate a different Device ID after changes in network-related system information. This could cause a valid device license to be rejected on the same laptop or PC.

### Root Cause

The older Device ID algorithm depended on values that may change on real user systems, such as:

- computer name / host name
- MAC address
- Wi-Fi adapter state
- LAN adapter state
- Bluetooth adapter state
- VPN adapters
- virtual adapters
- Hyper-V / WSL / VMware / VirtualBox adapters
- Windows random MAC address behavior

Because of this, the same physical device could occasionally appear as a different device.

### Fixed in v1.4.4

- Removed MAC address dependency from Device ID generation.
- Removed computer-name dependency from Device ID generation.
- Uses Windows `MachineGuid` as the main stable identity source.
- Adds a persistent Install ID fallback when Windows `MachineGuid` is not available.
- Saves the fallback Install ID in stable local locations.
- Device ID is no longer affected by GPU, GPU driver, NVIDIA / AMD / Intel selection, Wi-Fi, LAN, Bluetooth, VPN or virtual network adapter changes.
- Keeps the existing license verification workflow.
- Keeps the stable v1.4.3 compression behavior.

### Important License Note

Because the Device ID algorithm is now more stable, users upgrading from older beta builds may need a new `license.key` once after upgrading.

After that, the Device ID should remain stable across normal system changes such as network changes, VPN changes, GPU driver updates or switching between Wi-Fi and LAN.

---

## v1.4.3 Beta - Simple FPS Tuning

### Main Goal

Version `v1.4.3` refined Simple Mode FPS behavior.

### Changes

| Simple Level | FPS |
|---|---|
| High Quality | 30 |
| Medium | 30 |
| Compressed | 25 |
| Very Compressed | 25 |
| Very Very Compressed | 24 |
| Maximum Compression | 24 |

The goal was to keep normal simple settings smooth while allowing stronger compression levels to reduce FPS moderately.

---

## v1.4.2 Beta - Simple Safe Mode

### Main Goal

Version `v1.4.2` improved Simple Mode safety and added no-upscale protection.

### Changes

- Added Fast Mode checkbox in Simple Mode.
- If Fast Mode is enabled, Simple Mode prefers GPU / hardware encoding and faster processing.
- If Fast Mode is disabled, Simple Mode uses CPU-only compression.
- Added no-upscale protection.
- Smaller videos are not enlarged unnecessarily.
- Example: a 480p video will not be upscaled to 720p only because a preset requests 720p.

---

## v1.4.1 Beta - Simple and Advanced Mode

### Main Goal

Version `v1.4.1` added a two-mode user interface.

### Changes

- Added Simple Mode for normal users.
- Added Advanced Mode for full control.
- Simple Mode includes six compression levels:
  - High Quality
  - Medium
  - Compressed
  - Very Compressed
  - Very Very Compressed (quality loss)
  - Maximum Compression
- Advanced Mode preserves the full v1.4.0 settings interface.

---

## v1.4.0 Beta - Pipeline Clarity Update

### Main Goal

Version `v1.4.0` kept the stable `v1.3.9` compression logic and improved the user interface explanations around the real video-processing pipeline.

### New / Improved

- Added clearer UI hints for `Performance Mode`.
- Added clearer UI hints for `Processing Strategy`.
- Added clearer UI hints for `Hardware Decode`.
- Added a `Pipeline Preview` label in the UI.
- Pipeline Preview explains Decode / Scale / Encode.
- UI explains that `Hardware Decode: Off` is safest and can still use GPU encoding.
- UI explains that `High Throughput` mainly helps when processing multiple files.
- UI explains that `Maximum Hardware Acceleration` is most meaningful for NVIDIA with `Hardware Decode: Aggressive`.
- UI explains that AMD AMF and Intel QSV usually mean GPU encoding while scaling may remain CPU-based.

---

## v1.3.9 Beta - NVENC Runtime Test Fix

Version `v1.3.9` fixed an important hardware-detection issue found on a hybrid laptop with AMD + NVIDIA RTX GPU.

- NVIDIA was detected correctly.
- The NVIDIA driver was current.
- FFmpeg listed `hevc_nvenc` and `h264_nvenc`.
- The runtime test failed because the internal test frame was too small.
- VideoX incorrectly selected AMD AMF instead of NVIDIA NVENC.

Fixes:

- NVENC runtime test now uses a safer `1280x720` test input.
- NVIDIA NVENC should appear in GPU Preference when it actually works.
- Dynamic GPU Preference filtering was preserved.
- Legacy NVIDIA FFmpeg fallback was preserved.

---

## v1.3.6 Beta - Stable Legacy FFmpeg Fallback

Version `v1.3.6` replaced the unstable `v1.3.5` build.

The goal was to keep the stable behavior of `v1.3.4 File Queue & Safe Retry` and add Legacy NVIDIA FFmpeg fallback without breaking the UI, logs, buttons or compression workflow.

Version `v1.3.5` was removed / deprecated because it was not stable enough for public use.

Known problems in v1.3.5 included:

- Some UI buttons and controls were missing compared to v1.3.4.
- Log behavior was not consistent with v1.3.4.
- Compression behavior was not reliable enough.
- The implementation changed more than intended instead of only adding Legacy FFmpeg fallback.

---

# Recommended Settings

## Normal Users

```text
Interface Mode: Simple
Compression Level: Medium or Compressed
Fast Mode: On
```

## CPU-only Compatibility

```text
Interface Mode: Simple
Compression Level: Medium or Compressed
Fast Mode: Off
```

## Advanced Safe Mode

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

---

# Required Package Structure

```text
VideoX_Compressor_v1.4.4_Beta_Stable_Device_ID/
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

Do not delete the `ffmpeg` folder.  
Do not delete the `_internal` folder.  
Do not include `license.key` inside the public ZIP package.

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

---

# یادداشت‌های انتشار فارسی

<div dir="rtl" align="right">

## نسخه فعلی عمومی

```text
VideoX Compressor v1.4.4 Beta - Stable Device ID
```

ویدیو ایکس کامپرسور یک برنامه ویندوزی برای فشرده‌سازی ویدیو است. تمرکز برنامه روی فشرده‌سازی ساده، کاربردی و در صورت امکان شتاب‌داده‌شده با سخت‌افزار است.

---

## جدول نسخه‌ها

| نسخه | تمرکز اصلی | وضعیت |
|---|---|---|
| v1.4.0 Beta | شفاف‌سازی مسیر Decode / Scale / Encode. | تاریخچه پشتیبانی‌شده |
| v1.4.1 Beta | حالت ساده و حرفه‌ای. | تاریخچه پشتیبانی‌شده |
| v1.4.2 Beta | حالت ساده امن و جلوگیری از Upscale. | تاریخچه پشتیبانی‌شده |
| v1.4.3 Beta | تنظیم FPS در حالت ساده. | تاریخچه پشتیبانی‌شده |
| v1.4.4 Beta | پایدارسازی Device ID. | نسخه پیشنهادی فعلی |

---

## v1.4.4 Beta - Stable Device ID

### هدف نسخه

نسخه `v1.4.4` آخرین رفتار پایدار نسخه پایتون را حفظ می‌کند و مشکل تغییر گاه‌به‌گاه Device ID را اصلاح می‌کند.

در نسخه‌های قبلی، ممکن بود روی بعضی لپتاپ‌ها یا سیستم‌ها Device ID عوض شود و لایسنس معتبر روی همان دستگاه خطا بدهد.

### علت مشکل

الگوریتم قبلی Device ID به مواردی وابسته بود که ممکن است روی سیستم واقعی تغییر کنند؛ مثل:

- نام کامپیوتر
- MAC Address
- وای‌فای
- LAN
- بلوتوث
- VPN
- آداپتورهای مجازی
- Hyper-V / WSL / VMware / VirtualBox
- Random MAC Address ویندوز

### اصلاحات v1.4.4

- وابستگی به MAC Address حذف شد.
- وابستگی به نام کامپیوتر حذف شد.
- مبنای اصلی Device ID مقدار Windows MachineGuid شد.
- اگر MachineGuid در دسترس نباشد، یک Install ID پایدار ساخته و ذخیره می‌شود.
- تغییر GPU، درایور، وای‌فای، VPN، بلوتوث یا کارت شبکه نباید Device ID را عوض کند.
- مسیر لایسنس قبلی برنامه حفظ شد.
- رفتار فشرده‌سازی پایدار v1.4.3 حفظ شد.

### نکته مهم لایسنس

به دلیل تغییر الگوریتم Device ID، کاربران نسخه‌های قبلی ممکن است بعد از ارتقا به v1.4.4 یک بار به فایل `license.key` جدید نیاز داشته باشند.

بعد از آن، Device ID باید پایدارتر بماند.

---

## تغییرات اخیر قبل از v1.4.4

### v1.4.3

تنظیم FPS حالت ساده:

| سطح | FPS |
|---|---|
| کیفیت بالا | 30 |
| متوسط | 30 |
| فشرده | 25 |
| خیلی فشرده | 25 |
| خیلی خیلی فشرده | 24 |
| فشرده‌ترین حالت ممکن | 24 |

### v1.4.2

- اضافه شدن تیک Fast Mode در حالت ساده.
- اگر Fast Mode روشن باشد، برنامه GPU / پردازش سریع‌تر را ترجیح می‌دهد.
- اگر Fast Mode خاموش باشد، برنامه با CPU Only اجرا می‌شود.
- جلوگیری از Upscale اضافه شد.

### v1.4.1

- حالت Simple اضافه شد.
- حالت Advanced حفظ شد.
- حالت ساده برای کاربر عمومی طراحی شد.

### v1.4.0

- توضیح بهتر Performance Mode.
- توضیح بهتر Processing Strategy.
- توضیح بهتر Hardware Decode.
- اضافه شدن Pipeline Preview.

---

## تنظیمات پیشنهادی

### برای بیشتر کاربران

```text
Interface Mode: Simple
Compression Level: Medium یا Compressed
Fast Mode: On
```

### برای سازگاری بیشتر و CPU-only

```text
Interface Mode: Simple
Compression Level: Medium یا Compressed
Fast Mode: Off
```

---

## ساختار لازم پوشه‌ها

```text
VideoX_Compressor_v1.4.4_Beta_Stable_Device_ID/
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
فایل `license.key` را داخل بسته عمومی منتشر نکنید.

</div>
