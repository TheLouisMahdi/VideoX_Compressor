# VideoX Compressor - Release Notes

## v1.2.0 Beta

### English

VideoX Compressor v1.2.0 Beta is a Windows video compression release focused on fast, simple and GPU-accelerated compression for recorded classes, screen recordings, tutorials and low-motion educational videos.

This release improves the product experience compared with the earlier beta builds by adding a more stable interface, better progress reporting, safer queue handling, clearer logs, device-based activation and a more practical compression workflow for everyday users.

### Maintenance Update

This release package was updated with a small hotfix after testing on another laptop and desktop system.

Fixed issue:

- Fixed a file selection and drag-and-drop bug where selected videos were not added to the input queue on some systems.
- Fixed a drag-and-drop error related to the internal queue state.
- The input queue now correctly updates after selecting or dropping videos.
- The log now confirms when files are added to the queue.

If you downloaded an older build of this same beta release and the app does not add selected videos, download the latest ZIP package from this release again.

### Highlights

- GPU-accelerated compression with NVIDIA NVENC when available.
- CPU fallback when a compatible NVIDIA GPU is not available.
- Ready presets for Recorded Class, Balanced, Gaming / High Motion, Movie / Cinematic and Social Media / Ultra Small.
- Editable compression settings including workers, height, FPS, output format, GPU quality, CPU CRF, audio bitrate and audio channels.
- Current-file and total batch progress bars.
- English final report with input size, output size, reduction percentage, success/fail count and real processing time.
- Hidden FFmpeg / FFprobe execution without visible CMD windows.
- Cancel button for stopping active compression from inside the UI.
- Safer queue handling: files and settings are locked while compression is running.
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
- GPU mode is currently most stable with Workers set to 1.
- Time estimation is approximate and may be less accurate in GPU mode.
- Do not delete the `ffmpeg` or `_internal` folders from the release package.

---

## فارسی

<div dir="rtl" align="right">

نسخه v1.2.0 Beta برنامه VideoX Compressor یک نسخه آزمایشی برای فشرده‌سازی ویدیو در ویندوز است. تمرکز این نسخه روی فشرده‌سازی سریع، ساده و شتاب‌داده‌شده برای کلاس‌های ضبط‌شده، اسکرین‌ریکورد، آموزش‌ها و ویدیوهای کم‌تحرک است.

این نسخه نسبت به نسخه‌های بتای قبلی، تجربه کاربری، پایداری رابط کاربری، گزارش پیشرفت، مدیریت صف پردازش، لاگ‌ها، فعال‌سازی و روند کلی فشرده‌سازی را بهتر می‌کند.

### به‌روزرسانی اصلاحی

بعد از تست روی یک لپتاپ و یک سیستم دیگر، همین بسته انتشار با یک اصلاح کوچک به‌روزرسانی شد.

مشکل رفع‌شده:

- باگ انتخاب فایل و کشیدن و رها کردن فایل‌ها رفع شد.
- در بعضی سیستم‌ها، فایل انتخاب می‌شد اما به صف ورودی اضافه نمی‌شد.
- خطای مربوط به وضعیت داخلی صف هنگام کشیدن و رها کردن فایل‌ها رفع شد.
- بعد از اضافه شدن فایل، صف ورودی درست به‌روزرسانی می‌شود.
- داخل لاگ برنامه، اضافه شدن فایل‌ها به صف نمایش داده می‌شود.

اگر نسخه قبلی همین انتشار را دانلود کرده بودید و برنامه فایل‌های انتخاب‌شده را اضافه نمی‌کرد، فایل فشرده جدید همین Release را دوباره دانلود کنید.

### نکات مهم نسخه

- فشرده‌سازی شتاب‌داده‌شده با کارت گرافیک در صورت وجود سخت‌افزار مناسب.
- استفاده از پردازنده در صورت نبود کارت گرافیک مناسب.
- حالت‌های آماده برای کلاس، حالت متعادل، گیمینگ، فیلم و شبکه اجتماعی.
- تنظیمات قابل تغییر شامل تعداد پردازش همزمان، ارتفاع خروجی، نرخ فریم، فرمت خروجی، کیفیت حالت گرافیکی، کیفیت حالت پردازنده، کیفیت صدا و کانال صدا.
- نوار پیشرفت برای فایل جاری و کل عملیات.
- گزارش نهایی انگلیسی شامل حجم ورودی، حجم خروجی، درصد کاهش، تعداد موفق و ناموفق و زمان واقعی پردازش.
- اجرای ابزارهای پردازش ویدیو بدون باز شدن پنجره مزاحم.
- دکمه توقف برای قطع پردازش از داخل برنامه.
- قفل شدن فایل‌ها و تنظیمات هنگام پردازش برای جلوگیری از خراب شدن صف.
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
- حالت گرافیکی در نسخه فعلی با مقدار یک برای پردازش همزمان پایدارتر است.
- تخمین زمان تقریبی است و در حالت گرافیکی ممکن است دقیق نباشد.
- پوشه‌های `ffmpeg` و `_internal` را از بسته برنامه حذف نکنید.

</div>
