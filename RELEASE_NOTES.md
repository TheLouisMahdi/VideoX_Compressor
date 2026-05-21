# VideoX Compressor - Release Notes

## v1.2.0 Beta

### English

VideoX Compressor v1.2.0 Beta is a Windows video compression release focused on GPU-accelerated compression, recorded classes, screen recordings, tutorials and low-motion educational videos.

This version improves usability, stability and the overall product experience compared with the earlier beta builds.

### Highlights

- GPU-accelerated compression with NVIDIA NVENC when available.
- CPU fallback when a compatible NVIDIA GPU is not available.
- Ready presets for Recorded Class, Balanced, Gaming / High Motion, Movie / Cinematic and Social Media / Ultra Small.
- Editable compression settings including workers, height, FPS, output format, GPU quality, CPU CRF, audio bitrate and audio channels.
- Progress bars for current file and total batch progress.
- English final report with input size, output size, reduction percentage, success/fail count and processing time.
- Hidden FFmpeg / FFprobe execution without visible CMD windows.
- Cancel button for stopping active compression from inside the UI.
- Safer queue handling: files and settings are locked while compression is running.
- Save settings, save log, clear log and open output folder options.
- Device ID based license activation.
- Improved FFmpeg error messages with possible fixes.
- ffprobe metadata reading for FPS, resolution, codec and duration.
- Disk space warning before compression.

### Best Use Case

This beta is currently best optimized for:

- recorded classes
- screen recordings
- tutorials
- online meetings
- slide-based educational videos
- low-motion lectures

A real recorded class test reduced a video from about 1.96 GB to about 25 MB, which is roughly 98.7% size reduction. Results depend on the source video type and selected settings.

### Known Notes

- The project is still in beta and is not yet a fully polished commercial product.
- High-motion videos may need different settings than recorded classes.
- GPU mode is currently most stable with Workers set to 1.
- Time estimation is approximate and may be less accurate in GPU mode.
- Best results are currently expected on low-motion videos.

---

## فارسی

نسخه v1.2.0 Beta برنامه VideoX Compressor یک نسخه آزمایشی برای فشرده‌سازی ویدیو در ویندوز است. تمرکز اصلی این نسخه روی فشرده‌سازی سریع‌تر با کمک کارت گرافیک، کلاس‌های ضبط‌شده، اسکرین‌ریکورد، آموزش‌ها و ویدیوهای کم‌تحرک است.

این نسخه نسبت به نسخه‌های بتای قبلی، پایداری، تجربه کاربری و ظاهر محصول را بهتر می‌کند.

### نکات مهم نسخه

- فشرده‌سازی شتاب‌داده‌شده با کارت گرافیک در صورت وجود سخت‌افزار مناسب.
- استفاده از پردازنده در صورت نبود کارت گرافیک مناسب.
- حالت‌های آماده برای کلاس، حالت متعادل، گیمینگ، فیلم و شبکه اجتماعی.
- تنظیمات قابل تغییر شامل تعداد پردازش همزمان، ارتفاع خروجی، نرخ فریم، فرمت خروجی، کیفیت حالت گرافیکی، کیفیت حالت پردازنده، کیفیت صدا و کانال صدا.
- نوار پیشرفت برای فایل جاری و کل عملیات.
- گزارش نهایی انگلیسی شامل حجم ورودی، حجم خروجی، درصد کاهش، تعداد موفق و ناموفق و زمان پردازش.
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

در یک تست واقعی روی ویدیوی کلاس ضبط‌شده، حجم فایل از حدود 1.96 گیگابایت به حدود 25 مگابایت رسید. نتیجه نهایی به نوع ویدیو و تنظیمات انتخاب‌شده بستگی دارد.

### نکات شناخته‌شده

- پروژه هنوز در مرحله بتا است و محصول تجاری کاملاً نهایی محسوب نمی‌شود.
- ویدیوهای پرتحرک ممکن است به تنظیمات متفاوتی نسبت به کلاس ضبط‌شده نیاز داشته باشند.
- حالت گرافیکی در نسخه فعلی با مقدار Workers برابر 1 پایدارتر است.
- تخمین زمان تقریبی است و در حالت گرافیکی ممکن است دقیق نباشد.
- بهترین نتیجه فعلی روی ویدیوهای کم‌تحرک انتظار می‌رود.
