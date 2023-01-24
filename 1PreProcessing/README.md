### Business Understanding

اتاق فرار در واقع یک بازی گروهی، هیجانی و فکریست که می تواند بین 3 الی 8 نفر بازیکن داشته باشد.
این بازی متشکل از یک یا چندین اتاق می باشد و هر گروهی که وارد بازی شود، باید در یک مدت زمان مشخص از اتاق خارج شود.
برای رهایی یافتن از اتاق، گروه باید معماهای موجود در اتاق را حل کرده، قفل ها را باز کرده و قبل از 60 دقیقه از بازی بیرون بیاید.
اگر احیاناً گروه در حل قسمتی از معما یا قفل به مشکل بخورد، مدیر بازی از طریق روش های موجود برای گروه راهنمایی ارسال خواهد کرد.
اتاق فرار دارای تم و داستان مشخص است و اتاق فرار طاعون دارای تم ترسناک می باشد.

نام این اتاق فرار طاعون است که دارای ژانری ترسناک بوده و محوریت داستان در بیمارستانی متروکه اتفاق می افتد.

عکس اول هم در واقع همان پوستر اصلی بازی و عکس دوم نمایی از یکی از اتاق های درون بازی است.

هدف از تحقیق روی این داده ها، شناخت بازیکنان و همچنین شناسایی عوامل موثر بر پیروزی بر بازی است.

----
### Data Understanding

ستون "Number" نشان دهنده تعداد افراد شرکت کننده داخل هر نوبت از بازی است. این ستون مقادیر بین 3 تا 8 داشته و یک متغیر کمی گسسته است.

ستون "Male" نشان دهنده تعداد مردان هر گروه و ستون "Female" نیز نشان دهنده تعداد بانوان هر گروه است که هر دو متغیری کمی گسسته اند.

ستون "M/T" نشان دهنده نسبت جمعیت مردان به جمعیت کل گروه است و ستون "F/T" نیز نشان دهنده نسبت تعداد بانوان هر گروه به تعداد کل افراد گروه است.
هر دو متغیر، متغیری کمی پیوسته بوده و مقادیری بین 0 تا 1 را می توانند داشته باشند.

ستون "M-F" ترکیبی از 4 ستون بالا بوده و نشان دهنده تفاضل مرد و زن است. این متغیر پیوسته بوده و مقداری بین -1 تا +1 خواهد پذیرفت. هرچه داده به +1 نزدیکتر باشد،
یعنی مردان آن گروه بیشتر بوده و هر مقدار به -1 نزدیک باشد، یعنی زنان آن گروه بیشتر هستند.

ستون "Ave_Age" نشان دهنده میانگین سنی هر گروه شرکت کننده است و متغیری پیوسته می باشد.

ستون "Prev_Ed" نشان دهنده تحصیلات غالب هر گروه است. 9=زیر دیپلم / 12=دیپلم / 14=کاردانی / 16=کارشناسی / 18=کارشناسی ارشد / 21=دکتری

ستون "Ave_Exp" نشان دهنده میانگین تجربه افراد هر گروه است و متغیری پیوسته می باشد.

ستون "Sum_Exp" نشان دهنده مجموع تجربه افراد گروه است که متغیری گسسته است.

ستون "Ave_Fear" نشان دهنده میانگین ترسی است که افراد هر گروه درون بازی احساس کرده اند و مقداری پیوسته بین 0 تا 100 می تواند داشته باشد.
داده ی 100 یعنی بیشترین ترس ممکن را تجربه کرده اند و داده ی 0 بدین معنیست که فرد اصلا نترسیده است.

ستون "Hint" نشان دهنده راهنمایی هاییست که مدیر بازی برای گروه ارسال می کند تا گروه در روند اجرای بازی به مشکل نخورد. این متغیر گسسته است.

ستون "Ans" همانند ستون Hint می باشد؛ فقط با این تفاوت که این ستون نشان دهنده جواب مستقیم هر معما یا قفل می باشد.
این متغیر نیز گسسته است و همواره مقداری بین 0 تا 4 دارد.

ستون "Plague" نشان دهنده اینست که گروه قبلا در بازی طاعون شرکت کرده است یا خیر. 1=بله / 0=خیر

ستون "Time" نشان دهنده ساعتی می باشد که گروه وارد بازی شده است.

ستون "Turn" نشان دهنده نوبتی می باشد که گروه وارد بازی شده است.

ستون "Progress" نشان دهنده میزان پیشروی گروه در بازی است. اگر داده ی این ستون بین 0 تا 99 باشد، یعنی گروه درون بازی شکست خورده است.
و اگر داده بالاتر یا مساوی با خود 100 بود یعنی گروه پیروز شده است و قبل از اتمام زمان بازی از اتاق خارج شود. هر 30 ثانیه زمان اضافه معادل با یک واحد می باشد.
این ستون در واقع پیوسته است و یکی از ستون های هدف (یا همان ستون برچسب) ما است.

ستون "Victory" که دیگر ستون هدف ما می باشد، به صورت دودویی نشان دهنده پیروزی یا شکست گروه در بازی می باشد. 1=پیروزی / 0=شکست
----
### PreProcessing
پس از مرحله شناخت کسب و کار و شناخت داده، باید مرحله پیش پردازش داده را انجام داد.

با توجه به این که داده ها شخصاً توسط خودم جمع آوری شده، مشکلی از لحاظ وجود داده نویز یا داده از دست رفته نیست. ولی همچنان احتمال وجود داده پرت باقی می ماند.
که مسئله داده پرت درون برنامه رفع شده است.

همچنین در بخشی از مرحله پیش پردازش داده، ستون هایی که همبستگی زیادی داشتند حذف شده اند.