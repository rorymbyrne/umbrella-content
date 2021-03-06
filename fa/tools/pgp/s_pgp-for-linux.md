---
index: 10
title: PGP برای لینوکس
---
# راهنمای PGP برای ابزار لینوکس 

## راهنمای PGP برای ابزار لینوکس
ایمیل رمزگذاری شده برای لینوکس

** درسی برای خواندن:
- [ایمیل](umbrella://communications/email)**
** کامپیوترمورد نیاز : ** اتصال به اینترنت، رایانه ای که لینوکس را اجرا می کند، یک حساب ایمیل 
** نسخه مورد استفاده در این راهنمای: **
- لینوکس: دبیان 7.0 ("Wheezy")
- Mozilla Thunderbird 24.8.1  
- Enigmail 1.6
- GPG4Win 1.4.18
** مجوز: ** نرم افزار رایگان؛ ترکیبی از مجوزهای نرم افزاری رایگان
** سطح: ** خبره
** خواندن سایر موارد: ** [https://www.gnupg.org/documentation/guides.html](https://www.gnupg.org/documentation/guides.html)
** زمان مورد نیاز: ** 30-60 دقیقه

** استفاده از PGP به شما توانایی زیر را خواهد داد: **
- توانایی حفاظت از ارتباطات ایمیل خود از خوانده شدن توسط هر کسی به جز دریافت کنندگان مورد نظر خودتان
- توانایی اثبات اینکه یک ایمیل از یک فرد مشخص آمده است به جای پیام جعلی فرستاده شده توسط فرستنده دیگری (در غیر این صورت ساختگی بودن ایمیل بسیار آسان است). اگر هدف شما نظارت یا اطلاعات غلط باشید، هر دو اینها دارای اهمیت هستند.

** توجه: ** اگر نگران هستید که ایمیل های رمزگذاری شده PGP پس از آسیب پذیری ها در ماه مه 2018، ممکن است امن نباشند، بخش Efail از درس پیشرفته [ایمیل](umbrella://communications/email) را بخوانید.

### 1.0 قبل از شروع

برای استفاده از Privilege Good Privacy (PGP)، شما نیاز به نصب برخی از نرم افزار اضافی که با برنامه ایمیل فعلی شما کار می کنند دارید. شما همچنین باید یک کلید خصوصی ایجاد کنید و نگه دارید. کلید خصوصی چیزی است که شما برای رمزگشایی ایمیلهای ارسال شده به خود استفاده می کنید و به صورت دیجیتالی ایمیل هایی را که ارسال می کنید برای نشان دادن اینکه واقعا از شما آمده اند، امضا می کنید. در نهایت، شما یاد خواهید گرفت که چگونه کلید عمومی خود را به اشتراک بگذارید - یک تکه کوچک از اطلاعاتی است که دیگران باید بدانند قبل از اینکه آنها بتوانند ایمیل رمزگذاری شده به شما را ارسال کنند و بتوانند برای تأیید ایمیلهایی که ارسال می کنند استفاده کنند.

این راهنما به شما چگونگی استفاده از PGP را با یک سیستم عامل لینوکس با استفاده از موزیلا تاندربرد، یک برنامه محبوب منبع باز ایمیل گرافیکی را نشان می دهد.

شما در حال حاضر نمیتوانید به طور مستقیم از PGP با سرویس وب پست الکترونیک مانند Gmail، Hotmail، Yahoo! ایمیل یا Outlook Live استفاده کنید. شما هنوز هم می توانید از آدرس پست الکترونیک خود استفاده کنید شما فقط باید آن را با برنامه Thunderbird در رایانه خود پیکربندی کنید.

** توجه داشته باشید که هر دو طرف مکالمه ایمیل باید از نرم افزار سازگار با PGP برای کار استفاده کنند. **

مردم معمولا از این تنها در دستگاه های شخصی خود، و نه در دستگاه های مشترک استفاده می کنند. خوشبختانه PGP برای اکثر رایانه های رومیزی و دستگاه های تلفن همراه در دسترس است و شما می توانید به این راهنما برای راه اندازی نسخه خود تکیه کنید.

### 2.0 نصب Thunderbird، GnuPG و Enigmail

PGP یک استاندارد باز است که بدان معنی است که بیش از یک قطعه نرم افزار می تواند از آن استفاده کند. نرم افزاری که ما برای PGP استفاده می کنیم GnuPG نامیده می شود. ما همچنین اضافه کردن یک افزونه به Thunderbird به نام Enigmail، که به شما اجازه می دهد از GnuPGP از Thunderbird استفاده کنید. دستورالعمل های زیر نیاز به راحتی با خط فرمان دارند.

اگر از توزیع مبتنی بر Red Hat مانند Red Hat یا Fedora Core استفاده می کنید، ترمینال را باز کنید و این دستورات را اجرا کنید:

_sudo yum install gnupg thunderbird thunderbird-enigmail_

اگر از توزیع مبتنی بر اوبونتو مانند اوبونتو یا لینوکس مینت استفاده می کنید، یک ترمینال را باز کرده و این دستورات را تایپ کنید تا مطمئن شوید نرم افزار درست نصب شده است:

_sudo apt-get install gnupg thunderbird enigmail_

اگر از توزیع Debian استفاده می کنید، می بینید که Thunderbird به نام Icedove نام دارد. به طور کلی، مانند دبیان، این به دلایلی کاملا منطقی، اما تا حدودی مبهم است. به غیر از نام، دقیقا همان برنامه است: ما Icedove را دوباره ذکر نمی کنیم، اما شما می توانید جایگزین "Thunderbird" را با Icedove در بقیه این راهنما جایگزین کنید، و همه چیز باید هم اکنون کار کند.

برای نصب آن از این دستور در ترمینال استفاده کنید:

_sudo apt-get install gnupg icedove enigmail_

### 2.1 پیکربندی Thunderbird

حالا که Thunderbird را نصب کرده اید، آن را مانند برنامه دیگری که در دستگاه خود نصب می کنید باز کنید (ممکن است آن را از یک لیست از برنامه ها در یک منو انتخاب کنید یا نام آن را به یک جستجو در نرم افزار تایپ کنید). شما اولین جادوگر اجرا را خواهید دید.
! [تصویر](tool_pgplin1.png)

برای تنظیم آدرس ایمیل موجود خود، روی «پرش از این و استفاده از ایمیل موجود من» کلیک کنید و سپس نام، آدرس ایمیل و گذرواژه خود را برای حساب ایمیل خود وارد کنید.
! [تصویر](tool_pgplin2.png)

اگر از یک سرویس پست الکترونیکی محبوب رایگان مانند Gmail استفاده کنید، Thunderbird باید زمانی که روی «ادامه» کلیک می کنید، تنظیمات ایمیل شما را به صورت خودکار تشخیص دهد.

** اگر با استفاده از دو پارامتر احراز هویت با Google (و بسته به نوع تهدید شما، احتمالا باید!) از رمز عبور استاندارد Gmail خود با Thunderbird استفاده نکنید. در عوض، شما باید یک رمز عبور جدید برای برنامه مخصوص Thunderbird برای دسترسی به حساب Gmail خود ایجاد کنید. برای انجام این کار [راهنمای خود گوگل](https://support.google.com/mail/answer/1173270؟hl=en) را مشاهده کنید. **
! [تصویر](tool_pgplin3.png)

اگر این کار را نکنید، ممکن است لازم باشد تنظیمات IMAP و SMTP خود را به صورت دستی تنظیم کنید. اگر نمیدانید چطور این کار را انجام دهید، با ارائه دهنده ایمیل خود صحبت کنید یا از شخصی که با ارائه دهنده ایمیل شما آشناست (از یک شخص IT در محل کار یا یک دوست فنی که از همان ISP همانند شما استفاده میکند، بپرسید)؛ لازم نیست بدانید که چگونه از PGP استفاده کنید، اما می توانید از آنها بپرسید «آیا تنظیمات IMAP و SMTP برای آدرس ایمیل من را می دانید؟»).

### 2.2 پیکربندی Enigmail

Enigmail یک افزونه برای Thunderbird است که رمزنگاری و رمزگشایی ایمیل های رمزگذاری شده توسط PGP را انجام می دهد و باعث می شود که مدیریت کلید های خصوصی و عمومی کمی ساده تر شود. اگر شما آخرین نسخه Enigmail دارید، باید با Enigmail Setup Wizard ارائه شود.
! [تصویر](tool_pgplin4.png)

اگر شما آن را نمی بینید، می توانید از این گزینه منو از Thunderbird استفاده کنید تا آن ظاهر شود. بر روی سه خط افقی ("منو همبرگر") در سمت راست پنجره Thunderbird کلیک کنید.
! [تصویر](tool_pgplin5.png)

این اولین گزینه ای است که Enigmail به شما ارائه می دهد: سه گزینه برای مدیریت زمانی که ایمیل شما رمزگذاری شود.
! [تصویر](tool_pgplin6.png)

گزینه پیش فرض این است که ایمیل ها را رمزگذاری کند اگر کلید "عمومی" شخص دیگری را دارید، Enigmail ایمیلی که شما ارسال می کنید را رمزگذاری می کند اما گر کلید عمومی گیرنده را در اختیار نداشته باشید ایمیل ها را رمزگذاری نشده باقی میگذارد. شما همچنین می توانید تمام ایمیل های خود را با کلیدهای PGP رمزگذاری کنید، بدین معنی که شما باید کلیدهای عمومی را برای افرادی که قبلا آنها را ندیده اید پیدا کنید یا رمزگذاری خودکار را کاملا خاموش کنید و تنها از PGP استفاده کنید

ما نمی دانیم گزینه مناسب برای شما کدام است، اما گزینه «رمزگذاری خودکار مناسب» را انتخاب کنید که انتخاب خوبی باشد. اگر شک دارید،  "به طور پیش فرض پیام های من را رمزگذاری نکنید" را انتخاب کنید.

روی دکمه «بعدی» کلیک کنید.
! [تصویر](tool_pgplin6.png)

اکنون شما گزینه ای برای امضای همه ایمیل های خروجی دیجیتالی دارید. امضای ایمیل خود با PGP به گیرنده اجازه می دهد تا بررسی کند که شما پیام را ارسال کرده اید و محتویات پیام را با آن دستکاری نشده است. برای فعال کردن این ویژگی روی دکمه "پیام های من به طور پیش فرض امضا شود" را فشار دهید.

با این حال، بدی این کار این است که به هر کسی که به شما ایمیل می فرستد اعلام میکنید کنید که از PGP استفاده می کنید. [در برخی از نقاط جهان](www.cryptolaw.org/) (از جمله چین، ایران، بلاروس و برخی از کشورهای خاورمیانه) استفاده از رمزگذاری بدون مجوز، حتی برای استفاده شخصی، غیرقانونی است، بنابراین شما ممکن است دلایل بسیار خوبی داشته باشید اجازه ندهید دیگران بدانند شما از PGP استفاده می کنید.

دکمه "بعدی" را کلیک کنید.

حالا گزینه ای برای Enigmail ایجاد تغییراتی در تنظیمات موزیلا Thunderbird میبینید.
! [تصویر](tool_pgplin7.png)

اگر بر روی دکمه جزئیات کلیک کنید می توانید بررسی کنید که چه تغییراتی وجود دارد.

گزینه های زیر را می توانید بدون تیک (reenabled)، برای یک گذار بدون درز بیشتر، اگر PGP / Mime به طور پیش فرض استفاده میکنید (ما بعدا آن را تنظیم می کنیم):
- متن متفرقه را غیرفعال کنید
- بدنه پیام را به صورت متن ساده مشاهده کنید
- پیام های HTML را ایجاد نکنید

گزینه نهایی از مشکلات بالقوه رمزگذاری و رمزگشایی ایمیل شما جلوگیری می کند. توجه داشته باشید که انتخاب این کادر توانایی ارسال متن زاویه دار، زیر خط دار یا رنگی را حذف می کند. پس از بررسی تغییرات، روی دکمه باشه کلیک کنید.

حالا شما شروع به ایجاد کلید خصوصی و کلید عمومی خواهید کرد.

### 2.3 ایجاد کلید عمومی و کلید خصوصی

نصب و راه اندازی افزونه Enigmail کامل شده است. حالا گزینه ای برای ایجاد جفت کلید عمومی و خصوصی خود دارید. این فرض می کند که قبلا یک کلید خصوصی ایجاد نکرده اید.
! [تصویر](tool_pgplin8.png)

روی دکمه «بعدی» کلیک کنید.

مگر اینکه قبلا بیش از یک حساب ایمیل را پیکربندی کرده باشید، Enigmail حساب ایمیلی که شما قبلا پیکربندی کرده اید را انتخاب میکند. اولین چیزی که باید انجام دهید عبارتست از یک عبارت عبور قوی برای کلید خصوصی خود. برای اطلاعات بیشتر در مورد چگونگی انجام این کار، ** [درسهای گذرواژه](umbrella://information/passwords)** را ببینید.

Enigmail برخی از اطلاعات مربوط به کلید خصوصی و همچنین تنظیمات پیکربندی را نمایش می دهد. توصیه می کنیم کلید های 4096 بیتی ایجاد کنید. روی دکمه «بعدی» کلیک کنید.
! [تصویر](tool_pgplin9.png)

** کلید شما در یک زمان خاص منقضی می شود هنگامی که این اتفاق می افتد، افراد دیگر استفاده از آن را به طور کامل برای ایمیل های جدید به شما متوقف میکنند، هر چند شما ممکن است هیچ هشدار و یا توضیح در مورد چرایی آن نبینید. بنابراین، ممکن است بخواهید تقویم خود را علامت بزنید و یک ماه یا بیشتر قبل از تاریخ انقضاء، به این موضوع توجه کنید. **

ممکن است طول عمر یک کلید موجود را با دادن تاریخ جدید و بعد از تاریخ انقضای آن، افزایش دهیم، یا اینکه با ایجاد کلید جدید از ابتدا، بتوان آن را با یک کلید جدید جایگزین کرد. هر دو فرآیند ممکن است نیاز به تماس با افرادی که به شما ایمیل می کنند داشته باشد و اطمینان حاصل کنید که کلید به روز شده شما را دریافت کنند. نرم افزار در حال حاضر در اتوماسیون آن بسیار خوب نیست. بنابراین یک یادآوری برای خودتان ایجاد کنید؛ اگر فکر نمی کنید که بتوانید آن را مدیریت کنید، می توانید کلیدی را تنظیم کنید تا هرگز منقضی  نشود، اما در این صورت ممکن است افراد دیگر هنگام اتصال به شما در آینده حتی اگر دیگر آن کلید خصوصی را نداشته باشید یا دیگر از PGP استفاده نکنید، از آن استفاده کنند.

Enigmail کلیدی را تولید می کند و زمانی که آن کامل می شود، یک پنجره کوچک باز می شود که از شما می خواهد یک گواهی لغو را ایجاد کنید. این گواهی نامه لغو مهم است زیرا شما اجازه می دهید کلید خصوصی و کلید عمومی نامعتبر باشد. مهم است که توجه داشته باشید که صرفا پاک کردن کلید خصوصی، کلید عمومی را نامعتبر نمیکند و ممکن است منجر به ارسال ایمیل های رمزگذاری شده به شما شود که نمی توانید آنها را رمزگشایی کنید.
! [تصویر](tool_pgplin10.png)

روی دکمه "تولید گواهی" کلیک کنید.

پنجره ای باز می شود تا شما بتوانید گواهینامه لغو را ذخیره کنید. در حالی که می توانید فایل را در رایانه خود ذخیره کنید، توصیه می کنیم فایل را در یک درایو USB ذخیره کنید که هیچ استفاده دیگری از آن نداشته و درایو را در یک مکان امن ذخیره کنید. ما همچنین توصیه می کنیم گواهی لغو از کامپیوتر با کلید ها، فقط برای جلوگیری از لغو ناخواسته، حذف کنید

حتی بهتر، این فایل را روی یک دیسک رمزگذاری شده جداگانه ذخیره کنید. محل ذخیره سازی این فایل را انتخاب کنید و دکمه "ذخیره" را کلیک کنید.

در حال حاضر Enigmail به شما اطلاعات بیشتری در مورد ذخیره سازی در پرونده گواهی احیای مجدد داده خواهد شد. روی دکمه باشه کلیک کنید.

در نهایت کار شما با تولید کلید خصوصی و کلید عمومی تمام می شود. روی دکمه پایان کلیک کنید.

### 2.4 گام های اختیاری

### 2.4.1 نشان دادن کلید های ID طولانی

گام های بعدی کاملا اختیاری است، اما هنگام استفاده از OpenPGP و Enigmail می توانند مفید باشند. به طور خلاصه، شناسه کلید بخش کوچکی از اثر انگشت است. هنگامی که نوبت به تایید اینکه یک کلید عمومی متعلق به یک فرد خاص است، اثر انگشت بهترین راه است. تغییر نمایش پیش فرض باعث می شود تا اثر انگشت گواهی هایی را که می دانید در مورد آنها بخوانید. روی دکمه پیکربندی، سپس گزینه Enigmail، سپس مدیریت کلید کلیک کنید.
! [تصویر](tool_pgplin11.png)

یک پنجره دو ستون را نشان می دهد: نام و شناسه کلید.
! [تصویر](tool_pgplin12.png)

در سمت راست یک دکمه کوچک وجود دارد. برای پیکربندی ستونها روی این دکمه کلیک کنید. گزینه کلیدID را را غیرفعال کنید و بر روی گزینه اثر انگشت کلیک کنید.
! [تصویر](tool_pgplin13.png)

اکنون عرض ستون اثر انگشت را با حرکت دادن ماوس به خطوط بین عنوان هر ستون تغییر دهید (یعنی فقط به سمت چپ هدر «کلید ID» در بالای لیست کلید ها) و کشیدن خط به سمت چپ. حرکت را به سمت چپ ادامه دهید تا بتوانید تمام شناسه کلید را ببینید، مانند این:

حالا ستونها به صورت زیر هستند:
! [تصویر](tool_pgplin14.png)

اکنون شما برای ارسال و دریافت ایمیل به طور منظم و رمزگذاری شده تنظیم شده اید. بعد از مراحل به سمت پیدا کردن مردم برای تبادل ایمیل با استفاده از رمز عبور بروید.

** با استفاده از PGP ایمیل شما به طور کامل رمزگذاری نمی شود، بنابراین اطلاعات فرستنده و گیرنده رمزگذاری نشده باقی میماند. رمزگذاری اطلاعات فرستنده و گیرنده ایمیل را از بین می برد. استفاده از Thunderbird با افزونه Enigmail به شما یک راه آسان برای رمزگذاری و رمزگشایی محتوای ایمیل شما را ارائه می دهد. **

### 3.0 اجازه دادن به دیگران که بدانند شما از PGP استفاده می کنید

** a) اجازه دهید مردم بدانند شما از PGP استفاده میکنید، به وسیله ایمیل**

شما به راحتی می توانید کلید عمومی خود را به فرد دیگری ارسال کنید و یک کپی را به عنوان یک پیوست ارسال کنید.

با کلیک بر روی دکمه "نوشتن" در موزیلا تاندربرد.

یک آدرس و یک موضوع را پر کنید، شاید چیزی شبیه «کلید عمومی من»، روی منوی Enigmail کلیک کنید و گزینه "پیوست کردن کلید عمومی من" را انتخاب کنید.
! [تصویر](tool_pgplin15.png)

شما هم اکنون می توانید ایمیل کنید و گیرنده قادر به دانلود و استفاده از کلید عمومی که شما ارسال کرده اید، است.

** اگر این روش استفاده شود، ایده خوبی است که گیرنده بتواند اثر انگشت کلید عمومی خود را بر روی برخی دیگر از ارتباطات تأیید کند، در صورتی که ایمیل در حال تعقیب و جاسوسی باشد. **

** b) اجازه دهید مردم بدانند شما از PGP استفاده می کنید، از طریق وبسایت **

علاوه بر خبر دادن به افراد از طریق ایمیل، می توانید کلید عمومی خود را در وب سایت خود پست کنید. ساده ترین راه این است که فایل را آپلود کرده و لینک آن را بگذارید. این راهنما به چگونگی انجام این کارها نمی پردازد، اما شما باید بدانید چگونه  گواهی را به عنوان یک فایل برای استفاده در آینده صادر کنید.

روی دکمه پیکربندی، سپس گزینه Enigmail، سپس مدیریت کلید کلیک کنید.

گواهی نامه خود را برجسته کنید، سپس با کلیک راست بر روی آن، منو را ظاهر کنید و صادر کردن کلیدها به فایل را انتخاب کنید.
! [تصویر](tool_pgplin16.png)

یک پنجره کوچک با سه دکمه ظاهر می شود. روی دکمه "صادر کردن فقط کلید عمومی " کلیک کنید.
! [تصویر](tool_pgplin17.png)


** اطمینان حاصل کنید که شما بر روی دکمه "صادر کردن کلید های مخفی" کلیک نمی کنید، زیرا صادر کردن کلید مخفی می تواند به دیگران اجازه دهد تا شما را مجذوب خود کند اگر بتوانید رمز عبور شما را حدس بزنند. **

اکنون یک پنجره باز خواهد شد تا بتوانید فایل را ذخیره کنید. به منظور یافتن راحت تر آن در آینده ، لطفا فایل را در پوشه اسناد ذخیره کنید.

حالا شما می توانید از این فایل هر طور که می خواهید، استفاده کنید.

** ج) آپلود به یک سرور کلید**

Keyservers برای جستجو و دانلود کلیدهای عمومی کار را آسان تر می کند. اکثر سرویس دهنده های مدرن همگام سازی می شوند، به این معنی که کلید عمومی آپلود شده به یک سرور در نهایت به تمام سرورها میرسند.

اگرچه آپلود کلید عمومی خود در سرور کلید می تواند راهی مناسب برای اطلاع دادن به مردم در مورد  گواهی عمومی PGP شما باشد، باید بدانید که با توجه به ماهیت نحوه کارکرد کلید ها، هیچ راهی برای پاک کردن کلیدهای عمومی بعد از آپلود نیست ، شما فقط می توانید آنها را لغو کنید.

** قبل از آپلود کلید عمومی خود به سرور کلید، خوب است که لحظه ای فکر کنید که آیا می خواهید تمام دنیا بداند که شما یک کلید عمومی دارید بدون اینکه بتوانید این اطلاعات را بعدا حذف کنید. **

اگر انتخاب می کنید که کلید عمومی خود را به سرورهای کلید ارسال کنید، به پنجره Enigmail مدیریت کلید بروید.

با کلیک بر روی آیتم های منو سرورکلید و گزینه "بارگذاری کلیدهای عمومی" را انتخاب کنید.
! [تصویر](tool_pgplin18.png)

### 3.1 پیدا کردن افراد دیگری که از PGP استفاده می کنند

** الف) دریافت کلید عمومی از طریق ایمیل **

ممکن است یک کلید عمومی برای شما به عنوان ضمیمه ایمیل ارسال شود.
! [تصویر](tool_pgplin19.png)

ضمیمه را در پایین پنجره ببینید. بر روی پیوست کلیک راست کرده و گزینه وارد کردن کلید  OpenPGP را انتخاب کنید. یک پنجره کوچک باز می شود و به شما نتایج وارد کردن را می دهد. روی دکمه باشه کلیک کنید.

اگر دوباره پنجره مدیریت کلید Enigmail را باز کنید، می توانید نتیجه را بررسی کنید. کلید PGP شما درشت است زیرا شما کلید خصوصی و کلید عمومی را دارید. کلید عمومی که شما تازه وارد کرده اید درشت نیست زیرا همراه با کلید خصوصی نیست.
! [تصویر](tool_pgplin20.png)

** ب) دریافت کلید عمومی به عنوان یک فایل **

ممکن است که شما یک کلید عمومی را با دانلود آن از یک وبسایت یا کسی ممکن است آن را از طریق نرم افزار چت  برای شما ارسال کند. در مواردی مانند این، فرض کنید که فایل را به پوشه دانلودها بارگیری کرده اید.

مدیر کلید Enigmail را باز کنید و روی منوی «فایل» کلیک کنید. "وارد کردن کلید از فایل" را انتخاب کنید.

کلید عمومی ممکن است پسوند نام فایل های مختلف مانند .asc، .pgp، یا .gpg داشته باشد. فایل را انتخاب کرده و روی دکمه «باز کردن» کلیک کنید. یک پنجره کوچک باز خواهد شد، و به شما نتایج وارد کردن را می دهد. روی دکمه باشه کلیک کنید.

** ج) گرفتن یک کلید عمومی از یک سرور کلید **

سرورکلید می تواند یک راه بسیار مفید برای به دست آوردن کلیدهای عمومی باشد. سعی کنید کلید عمومی را جستجو کنید. مدیریت کلید را باز کنید سپس روی منوی "سرور کلید" کلیک کنید و "جستجو برای کلید ها" را انتخاب کنید.
! [تصویر](tool_pgplin21.png)

یک پنجره کوچک با یک فیلد جستجو ظاهر خواهد شد. شما می توانید آن را با یک آدرس ایمیل کامل، یک آدرس ایمیل جزئی یا یک نام جستجو کنید. در این مورد، شما گواهی هایی حاوی "eff.org" را جستجو خواهید کرد.
! [تصویر](tool_pgplin22.png)

یک پنجره بزرگتر با گزینه های زیادی ظاهر میشود. اگر شما پایین بروید متوجه خواهید شد که برخی از گواهینامه ها به صورت نوشته کج و خاکستری هستند. این گواهینامه هایی هستند که به صورت خود لغو شده یا منقضی شده اند.
! [تصویر](tool_pgplin23.png)

برای مثال، کلید عمومی Danny O'Brien را در اختیار شما قرار می دهیم، او یک گواهی منقضی شده یا لغو شده و یک گواهی معتبر دارد. گواهی معتبر را با کلیک بر روی کادر در سمت چپ انتخاب کنید و سپس دکمه باشه را فشار دهید.
! [تصویر](tool_pgplin24.png)

در بعضی موارد ممکن است فرد دارای بیش از یک گواهی باشد که همه آنها معتبر هستند. توجه داشته باشید که هر کسی می تواند یک گواهی عمومی را برای هر شخص دیگری آپلود کند و یکی از این کلید ها ممکن است متعلق به فردی باشد که دارای آدرس ایمیل مربوط به آن است. در این مورد تأیید اثر انگشت بسیار مهم است.

اگر شما موفق شوید یک پنجره اطلاع رسانی کوچک به شما نشان می دهد، و مدیر کلید Enigmail شما گواهی های اضافه شده را به شما نشان می دهد:
! [تصویر](tool_pgplin25.png)

### 4.0 ارسال ایمیل رمزگذاری شده PGP

حالا شما اولین ایمیل رمز شده خود را به گیرنده ارسال خواهید کرد. در پنجره اصلی Mozilla Thunderbird روی دکمه «نوشتن» کلیک کنید. یک پنجره جدید باز خواهد شد.

پیام خود را بنویسید و یک گیرنده را وارد کنید. برای این آزمون، گیرنده ای را انتخاب کنید که کلید عمومی او را را داشته باشید. Enigmail این را شناسایی کرده و به طور خودکار ایمیل را رمزگذاری می کند (شما می توانید بگویید که با کلید طلایی در پایین سمت راست ایمیل رمزگذاری شده است).
! [تصویر](tool_pgplin26.png)

** توجه داشته باشید که موضوع رمزگذاری نخواهد شد، بنابراین چیزی بی خطر را انتخاب کنید، مانند "سلام" **

وقتی دکمه "ارسال" را کلیک میکنید، یک پنجره برای وارد کردن گذرواژه کلید PGP شما داده می شود. به یاد داشته باشید این با رمز عبور ایمیل شما متفاوت است!

رمز عبور خود را وارد کنید و سپس دکمه "باشه" را فشار دهید و ایمیل شما رمزگذاری و ارسال خواهد شد.

بدنه ایمیل رمزگذاری شده و تبدیل شده است. مثلا متن ما بالا، به این تبدیل شد:
! [تصویر](tool_pgplin27.png)

### 4.1 دریافت ایمیل رمزگذاری شده PGP

بیایید آنچه رخ می دهد زمانی که شما ایمیل رمز شده دریافت میکنید را بررسی کنیم. اول، بر روی پیام کلیک کنید.

یک پنجره کوچک باز می شود که از شما کلید رمز PGP درخواست می کند. به یاد داشته باشید: رمز عبور ایمیل خود را وارد نکنید. بر روی دکمه باشه کلیک کنید.
! [تصویر](tool_pgplin28.png)

اکنون پیام به صورت رمزنشده نشان داده می شود
! [تصویر](tool_pgplin29.png)

### 5.0 لغو کلید PGP

** a) لغو کلید PGP خود از طریق رابط Enigmail **

کلید های PGP تولید شده توسط Enigmail به طور خودکار پس از پنج سال منقضی می شوند. بنابراین اگر تمام فایل های خود را از دست بدهید، می توانید امیدوار باشید که مردم بعد از اینکه انقضای این کلید به پایان برسد، از شما کلید دیگری را درخواست میکنند.

شما ممکن است دلیل خوبی برای غیرفعال کردن کلید PGP قبل از پایان یافتن انقضای  آن داشته باشید. شاید شما میخواهید یک کلید جدید PGP قوی ایجاد کنید. ساده ترین راه برای لغو کلید PGP خود در Enigmail از طریق مدیریت کلید Enigmail است. روی کلید PGP خود راست کلیک کنید (آن را به شکل پررنگ)، و گزینه "لغو کلید" را انتخاب کنید.
! [تصویر](tool_pgplin30.png)

یک پنجره بالا می آید و به شما اجازه می دهد تا بفهمید چه اتفاقی می افتد و درخواست تایید شما را می دهد. روی دکمه "لغو کلید" کلیک کنید.
! [تصویر](tool_pgplin31.png)

پنجره رمز عبور باز می شود، رمز عبور خود را برای کلید PGP وارد کنید و دکمه "باشه" را کلیک کنید.

اکنون یک پنجره جدید باز می شود تا شما بتوانید بدانید که موفق شدید.بر روی دکمه باشه کلیک کنید.

هنگامی که شما به پنجره مدیریت Enigmail برگردید، تغییری در کلید PGP خواهید یافت. اکنون خاکستری شده و خط نوشتن آن کج شده است.
! [تصویر](tool_pgplin32.png)

** ب) لغو کلید PGP با یک گواهی لغو **

همانطور که قبلا ذکر شد، کلیدهای PGP تولید شده توسط Enigmail به طور خودکار بعد از پنج سال منقضی می شوند. بنابراین اگر تمام فایلهای خود را از دست بدهید، می توانید اطمینان حاصل کنید که مردم بعد از اینکه کلیدی منقضی شود، از شما کلید دیگری درخواست کنند.

همانطور که قبلا ذکر شد، شما ممکن است دلیل خوبی برای غیرفعال کردن کلید PGP قبل از اتمام انقضای آن داشته باشید.

به طور مشابه، دیگران ممکن است دلایل خوبی برای لغو یک کلید موجود داشته باشند.

شما ممکن است یک گواهی لغو ارسال از طرف دوستان را به عنوان یک اخطار دریافت کنید که میخواهند کلید خود را لغو کنند.

در بخش قبلی شما ممکن است متوجه شده باشید که Enigmail گواهی لغو را به صورت داخلی در هنگام استفاده از کلید مدیریت Enigmail برای لغو کلید تولید و وارد میکند. از آنجا که شما قبلا گواهینامه لغو را دارید، از همان اولی که قبلا تولید کرده اید را برای لغو کلید خود استفاده می کنید.

با مدیریت کلید Enigmail شروع کرده و با کلیک بر روی منوی "فایل" و "وارد کردن کلید از فایل" را انتخاب کنید.
! [تصویر](tool_pgplin33.png)

یک پنجره باز خواهد شد، بنابراین شما می توانید گواهی لغو را انتخاب کنید. روی فایل کلیک کنید و دکمه "بازکردن" را کلیک کنید. شما یک اعلان دریافت خواهید کرد که گواهی موفقیت آمیز وارد شده است و کلید لغو شده است. بر روی دکمه باشه کلیک کنید.
! [تصویر](tool_pgplin34.png)

هنگامی که شما بر روی دکمه "باشه" کلیک میکنید، به مدیریت کلید Enigmail بازگردانده می شوید و گواهینامه ای را که لغو کرده اید به رنگ خاکستری و با خط متن کج  مشاهده می کنید.
! [تصویر](tool_pgplin35.png)

اگر کلیدی که شما لغو کرده اید، مربوط به خودتان است و قبلا کلید عمومی خود را به سرورهای کلید آپلود کرده اید، شما خواهید توانست کلید لغو شده را دوباره به سرور اصلی بازگردانید تا دیگران دیگر از آن استفاده نکنند.

اکنون که تمام ابزارهای مناسب را دارید، سعی کنید نامه الکترونیکی رمز شده با PGP خود را ارسال کنید.