# VideoX Compressor - Release Notes

## v1.2.5 Beta - General Safe Diagnostics

### English

VideoX Compressor v1.2.5 Beta - General Safe Diagnostics is the recommended public beta build for testing and limited distribution.

This version keeps the main focus of VideoX: fast and simple video compression for recorded classes, tutorials, screen recordings and low-motion educational videos, while improving diagnostics, user support and hardware compatibility.

### What is new in v1.2.5

- Added General Safe Mode for public testing.
- Added automatic diagnostic report generation when errors happen.
- Added manual Export Bug Report button.
- Added Open Logs button.
- Added GPU Diagnostics with saved report output.
- Improved hardware encoder selection.
- Added better fallback behavior when hardware acceleration fails.
- Added more detailed logs with timestamp, system info, encoder info and FFmpeg error details.
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

### Recommended Public Settings

For most users and public release testing:

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Output Format: mp4
```

### Advanced Speed Test Settings

For systems with stronger GPU hardware:

```text
Performance Mode: High Throughput
Processing Strategy: Maximum Hardware Acceleration
General Safe Mode: On
Hardware Decode: Aggressive
```

If errors happen with the advanced mode, use the recommended public settings above.

### Highlights

- GPU-accelerated compression when compatible hardware is available.
- Support for NVIDIA NVENC, Intel Quick Sync / QSV, AMD AMF and CPU fallback.
- Ready presets for Recorded Class, Balanced, Gaming / High Motion, Movie / Cinematic and Social Media / Ultra Small.
- Editable compression settings including workers, height, FPS, output format, GPU quality, CPU CRF, audio bitrate and audio channels.
- Current-file and total batch progress bars.
- English final report with input size, output size, reduction percentage, success/fail count and real processing time.
- Hidden FFmpeg / FFprobe execution without visible CMD windows.
- Cancel button for stopping active compression from inside the UI.
- Safer queue handling while compression is running.
- Save Settings, Save Log, Clear Log and Open Output Folder options.
- Device ID based license activation.
- Improved FFmpeg error messages with possible fixes.
- Metadata reading for FPS, resolution, codec and duration.
- Disk space warning before compression.

### Best Use Case

This beta is currently best optimized for:

- recorded classes
- screen recordings
- tutorials
- online meetings
- slide-based educational videos
- low-motion lectures

A real recorded class test reduced a video from about 1.96 GB to about 25 MB, which is roughly 98.7% size reduction. Results depend on the source video type, motion level, resolution and selected settings.

### Activation

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

### Important Notes

- This is a Beta release.
- Best results are currently expected on low-motion videos.
- High-motion videos may need different settings than recorded classes.
- Hardware acceleration depends on GPU model, driver, FFmpeg support and selected output format.
- If hardware acceleration is not available, the app falls back to CPU mode.
- Time estimation is approximate and may be less accurate in GPU mode.
- Do not delete the `ffmpeg` or `_internal` folders from the release package.

---

## فارسی

<div dir="rtl" align="right">

## نسخه v1.2.5 Beta - General Safe Diagnostics

نسخه v1.2.5 Beta - General Safe Diagnostics نسخه پیشنهادی برای انتشار عمومی آزمایشی و تست محدود است.

تمرکز اصلی برنامه همچنان فشرده‌سازی سریع و ساده ویدیوهای کلاس ضبط‌شده، آموزش، اسکرین‌ریکورد و ویدیوهای کم‌تحرک است. در این نسخه، قابلیت‌های عیب‌یابی، گزارش خطا، سازگاری سخت‌افزاری و پشتیبانی از کاربران بهتر شده است.

### تغییرات جدید در نسخه v1.2.5

- حالت General Safe Mode برای تست عمومی اضافه شد.
- اگر خطا رخ دهد، برنامه می‌تواند گزارش عیب‌یابی خودکار بسازد.
- دکمه Export Bug Report اضافه شد.
- دکمه Open Logs اضافه شد.
- دکمه GPU Diagnostics علاوه بر نمایش داخل برنامه، فایل گزارش هم ذخیره می‌کند.
- انتخاب شتاب‌دهنده سخت‌افزاری بهتر شد.
- اگر شتاب‌دهنده سخت‌افزاری خطا بدهد، برنامه بهتر به مسیر جایگزین برمی‌گردد.
- لاگ‌ها شامل تاریخ، مشخصات سیستم، اطلاعات شتاب‌دهنده، تنظیمات و خطای موتور پردازش می‌شوند.
- فایل‌های گزارش برای ارسال کاربر و بررسی خطا آماده‌تر شدند.

### گزارش‌های عیب‌یابی

اگر هنگام فشرده‌سازی خطا رخ دهد، برنامه می‌تواند یک گزارش کامل ذخیره کند که شامل این موارد است:

- نسخه برنامه
- تاریخ و ساعت محلی و جهانی
- اطلاعات ویندوز و سیستم
- مسیر ابزارهای پردازش ویدیو
- فهرست شتاب‌دهنده‌های ویدیویی موجود
- نتیجه تست شتاب‌دهنده‌ها
- تنظیمات انتخاب‌شده
- شتاب‌دهنده انتخاب‌شده
- فایل ورودی فعلی
- خطای موتور پردازش
- لاگ فعلی برنامه

محل پیش‌فرض ذخیره لاگ‌ها:

```text
C:\Users\<User>\AppData\Local\TheLouisMahdi\VideoXCompressor\logs
```

### تنظیمات پیشنهادی برای انتشار عمومی

برای بیشتر کاربران و تست عمومی:

```text
Performance Mode: Stable
Processing Strategy: Auto Balanced
General Safe Mode: On
Hardware Decode: Off
Output Format: mp4
```

### تنظیمات تست سرعت برای سیستم‌های قوی‌تر

برای سیستم‌هایی که سخت‌افزار گرافیکی قوی‌تری دارند:

```text
Performance Mode: High Throughput
Processing Strategy: Maximum Hardware Acceleration
General Safe Mode: On
Hardware Decode: Aggressive
```

اگر در حالت سریع خطا رخ داد، از تنظیمات پیشنهادی عمومی استفاده کنید.

### نکات مهم نسخه

- فشرده‌سازی شتاب‌داده‌شده در صورت وجود سخت‌افزار سازگار.
- پشتیبانی از مسیرهای سخت‌افزاری انویدیا، اینتل، ای‌ام‌دی و حالت پردازنده.
- حالت‌های آماده برای کلاس، حالت متعادل، گیمینگ، فیلم و شبکه اجتماعی.
- تنظیمات قابل تغییر شامل تعداد پردازش همزمان، ارتفاع خروجی، نرخ فریم، فرمت خروجی، کیفیت حالت گرافیکی، کیفیت حالت پردازنده، کیفیت صدا و کانال صدا.
- نوار پیشرفت برای فایل جاری و کل عملیات.
- گزارش نهایی انگلیسی شامل حجم ورودی، حجم خروجی، درصد کاهش، تعداد موفق و ناموفق و زمان واقعی پردازش.
- اجرای ابزارهای پردازش ویدیو بدون باز شدن پنجره مزاحم.
- دکمه توقف برای قطع پردازش از داخل برنامه.
- مدیریت امن‌تر صف پردازش.
- ذخیره تنظیمات، ذخیره لاگ، پاک کردن لاگ و باز کردن پوشه خروجی.
- فعال‌سازی بر اساس کد دستگاه.
- پیام‌های خطای بهتر و قابل فهم‌تر.
- خواندن اطلاعات ویدیو مثل نرخ فریم، رزولوشن، کدک و مدت.
- هشدار فضای دیسک قبل از شروع فشرده‌سازی.

### بهترین کاربرد فعلی

این نسخه فعلاً بیشتر برای موارد زیر بهینه شده است:

- کلاس ضبط‌شده
- اسکرین‌ریکورد
- آموزش
- جلسه آنلاین
- ویدیوهای پاورپوینتی
- ویدیوهای درسی کم‌تحرک

در یک تست واقعی روی ویدیوی کلاس ضبط‌شده، حجم فایل از حدود 1.96 گیگابایت به حدود 25 مگابایت رسید. نتیجه نهایی به نوع ویدیو، میزان حرکت تصویر، رزولوشن و تنظیمات انتخاب‌شده بستگی دارد.

### فعال‌سازی

بعد از باز کردن برنامه:

1. کد دستگاه را کپی کنید.
2. آن را در تلگرام به آیدی زیر ارسال کنید.

```text
@thelouis_mahdi
```

3. فایل مخصوص لایسنس همان دستگاه را دریافت کنید.
4. فایل لایسنس را کنار فایل اجرایی برنامه قرار دهید یا از داخل برنامه انتخاب کنید.
5. روی دکمه بررسی دوباره بزنید و وارد برنامه شوید.

لایسنس مخصوص همان دستگاه است و روی دستگاه دیگر فعال نمی‌شود.

### نکات مهم

- این نسخه در مرحله بتا قرار دارد.
- بهترین نتیجه فعلی روی ویدیوهای کم‌تحرک انتظار می‌رود.
- ویدیوهای پرتحرک ممکن است به تنظیمات متفاوتی نسبت به کلاس ضبط‌شده نیاز داشته باشند.
- فعال شدن شتاب‌دهنده سخت‌افزاری به مدل کارت، درایور، پشتیبانی موتور پردازش و فرمت خروجی بستگی دارد.
- اگر شتاب‌دهنده سخت‌افزاری در دسترس نباشد، برنامه با پردازنده ادامه می‌دهد.
- تخمین زمان تقریبی است و در حالت گرافیکی ممکن است دقیق نباشد.
- پوشه‌های `ffmpeg` و `_internal` را از بسته برنامه حذف نکنید.

</div>
