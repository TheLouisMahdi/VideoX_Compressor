# VideoX Compressor - Release Notes

## Current Public Beta

```text
VideoX Compressor v1.4.4 Beta - Stable Device ID
```

VideoX Compressor is a Windows video compression application focused on simple, practical and hardware-accelerated compression for recorded classes, tutorials, screen recordings, online meetings, low-motion lecture videos and everyday videos that need smaller file size.

The project is still in **Beta**. The strongest current results are usually on low-motion educational videos and screen recordings. Results depend on source video type, bitrate, motion level, resolution, hardware, driver version and selected settings.

---

## Important License Compatibility Notice

Starting from **VideoX Compressor v1.4.4 Beta - Stable Device ID**, the Device ID and license-generation structure has changed.

This means:

- Licenses generated for versions before `v1.4.4` are deprecated.
- Public beta builds before `v1.4.4` should be considered legacy / deprecated for licensing.
- Users upgrading from older beta builds may need a new `license.key` once.
- From `v1.4.4` onward, licenses should be generated using the updated v1.4.4 license admin tools.
- The old beta license flow should not be used for new users.

The reason for this change is stability. Older beta builds could generate a different Device ID after changes in network-related system information. Version `v1.4.4` removes unstable Device ID dependencies such as MAC address and computer name.

---

## Version Timeline

| Version | Release Focus | Status |
|---|---|---|
| v1.2.5 Beta | General Safe Diagnostics, bug reports, safer public testing. | Deprecated for licensing |
| v1.2.6 Beta | Already-compressed video warning and bitrate analysis. | Deprecated for licensing |
| v1.2.7 Beta | Cleanup of failed, cancelled or corrupted output files. | Deprecated for licensing |
| v1.2.8 Beta | Smart Recompression for already-compressed sources. | Deprecated for licensing |
| v1.2.9 Beta | Smart Size Target for better real size reduction. | Deprecated for licensing |
| v1.3.0 Beta | GPU Quality slider. | Deprecated for licensing |
| v1.3.1 Beta | Help buttons for GPU Quality and CPU CRF. | Deprecated for licensing |
| v1.3.2 Beta | CPU CRF slider. | Deprecated for licensing |
| v1.3.3 Beta | RTL Persian help popup fix. | Deprecated for licensing |
| v1.3.4 Beta | File queue panel and safe retry behavior. | Deprecated for licensing |
| v1.3.5 Beta | Legacy NVIDIA FFmpeg fallback attempt. | Removed / unstable |
| v1.3.6 Beta | Stable Legacy FFmpeg Fallback rebuilt on v1.3.4. | Deprecated for licensing |
| v1.3.7 Beta | Manual GPU Preference selection. | Deprecated for licensing |
| v1.3.8 Beta | Dynamic GPU Preference filtering. | Deprecated for licensing |
| v1.3.9 Beta | NVENC runtime test fix for hybrid laptops. | Deprecated for licensing |
| v1.4.0 Beta | Pipeline Clarity Update. | Deprecated for licensing |
| v1.4.1 Beta | Simple and Advanced Mode. | Deprecated for licensing |
| v1.4.2 Beta | Simple Safe Mode and no-upscale protection. | Deprecated for licensing |
| v1.4.3 Beta | Simple FPS Tuning. | Deprecated for licensing |
| v1.4.4 Beta | Stable Device ID and updated license structure. | Current recommended beta |

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
- Keeps the stable v1.4.3 compression behavior.
- Introduces the updated v1.4.4 license-generation structure.

### License Change in v1.4.4

From this version onward, licenses must be generated using the updated v1.4.4 license admin panel or CLI generator.

Old beta licenses and old license-generation tools are now deprecated because they were based on the older Device ID behavior.

Users who upgrade from older beta builds may need a new `license.key` once. After the new license is generated for v1.4.4, the Device ID should remain more stable across normal system changes.

---

## v1.4.3 Beta - Simple FPS Tuning

Version `v1.4.3` refined Simple Mode FPS behavior.

| Simple Level | FPS |
|---|---|
| High Quality | 30 |
| Medium | 30 |
| Compressed | 25 |
| Very Compressed | 25 |
| Very Very Compressed | 24 |
| Maximum Compression | 24 |

---

## v1.4.2 Beta - Simple Safe Mode

- Added Fast Mode checkbox in Simple Mode.
- If Fast Mode is enabled, Simple Mode prefers GPU / hardware encoding and faster processing.
- If Fast Mode is disabled, Simple Mode uses CPU-only compression.
- Added no-upscale protection.
- Smaller videos are not enlarged unnecessarily.

---

## v1.4.1 Beta - Simple and Advanced Mode

- Added Simple Mode for normal users.
- Added Advanced Mode for full control.
- Simple Mode includes six compression levels.
- Advanced Mode preserves the full v1.4.0 settings interface.

---

## v1.4.0 Beta - Pipeline Clarity Update

- Added clearer UI hints for `Performance Mode`.
- Added clearer UI hints for `Processing Strategy`.
- Added clearer UI hints for `Hardware Decode`.
- Added `Pipeline Preview`.
- Explained Decode / Scale / Encode behavior more clearly.

---

## v1.3.9 Beta - NVENC Runtime Test Fix

Version `v1.3.9` fixed an important hardware-detection issue found on hybrid GPU laptops.

- NVENC runtime test now uses a safer `1280x720` test input.
- NVIDIA NVENC should appear in GPU Preference when it actually works.
- Dynamic GPU Preference filtering was preserved.
- Legacy NVIDIA FFmpeg fallback was preserved.

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

3. Receive your device-specific `license.key` file generated with the v1.4.4 license tools.
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

## اطلاعیه مهم درباره لایسنس

از نسخه **v1.4.4 Beta - Stable Device ID** به بعد، ساختار Device ID و ساخت لایسنس تغییر کرده است.

یعنی:

- لایسنس‌های ساخته‌شده برای نسخه‌های قبل از `v1.4.4` منسوخ هستند.
- نسخه‌های قبل از `v1.4.4` از نظر لایسنس‌دهی قدیمی محسوب می‌شوند.
- کاربران نسخه‌های قبلی ممکن است بعد از ارتقا یک بار به `license.key` جدید نیاز داشته باشند.
- از این نسخه به بعد، لایسنس باید با پنل یا ابزار جدید v1.4.4 ساخته شود.
- ابزارهای قدیمی ساخت لایسنس دیگر برای کاربران جدید پیشنهاد نمی‌شوند.

دلیل این تغییر، پایدار کردن Device ID است. در نسخه‌های قبلی، Device ID ممکن بود با تغییرات شبکه، VPN، وای‌فای، بلوتوث یا آداپتورهای مجازی عوض شود.

---

## جدول نسخه‌ها

| نسخه | تمرکز اصلی | وضعیت |
|---|---|---|
| v1.4.0 Beta | شفاف‌سازی مسیر Decode / Scale / Encode. | منسوخ از نظر لایسنس |
| v1.4.1 Beta | حالت ساده و حرفه‌ای. | منسوخ از نظر لایسنس |
| v1.4.2 Beta | حالت ساده امن و جلوگیری از Upscale. | منسوخ از نظر لایسنس |
| v1.4.3 Beta | تنظیم FPS در حالت ساده. | منسوخ از نظر لایسنس |
| v1.4.4 Beta | پایدارسازی Device ID و ساختار جدید لایسنس. | نسخه پیشنهادی فعلی |

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
- رفتار فشرده‌سازی پایدار v1.4.3 حفظ شد.
- ساختار جدید ساخت لایسنس برای v1.4.4 معرفی شد.

### نکته مهم لایسنس

به دلیل تغییر الگوریتم Device ID، کاربران نسخه‌های قبلی ممکن است بعد از ارتقا به v1.4.4 یک بار به فایل `license.key` جدید نیاز داشته باشند.

بعد از آن، Device ID باید پایدارتر بماند.

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
