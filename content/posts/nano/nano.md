---
title: "nano"
date: 2022-04-04T01:31:42+04:30
draft: false
---


<div dir='rtl'>

### فهرست

> - [مقدمه](#مقدمه)
> - [باز کردن فایل با ادیتور](#باز-کردن-فایل-با-ادیتور)
> - [ذخیره فایل](#ذخیره-فایل)
> - [خروج از ادیتور](#خروج-از-ادیتور)
> - [نمایش خطوط در کنار هم](#نمایش-خطوط-در-کنار-هم)
> - [لیست کردن تمامی دستورات ادیتور](#لیست-کردن-تمامی-دستورات-ادیتور)
> - [جستجو در فایل](#جستجو-در-فایل)
> - [کپی و کات کردن سریع](#کپی-و-کات-کردن-سریع)
> - [برگشتن به کاراکتر قبلی و بعدی](#برگشتن-به-کاراکتر-قبلی-و-بعدی)
> - [نمایش انتها و ابتدای خط](#نمایش-انتها-و-ابتدای-خط)
> - [جابه جا شدن در فایل](#جابه-جا-شدن-در-فایل)
> - [Author or Authors](#author-or-authors)
</div>

---
<div dir='rtl'>

### مقدمه
در گنو/لینوکس ادیتور های زیادی در محیط cli داریم ، که هرکدام بسته به سلیقه و راحتی افراد استفاده میشود. در این بخش شما با ادیتور nano آشنا خواهید شد . کار با این ادیتور بسیار ساده است، هنگام کار با ادیتور متوجه خواهید شد.
</div>


---
<div dir='rtl'>

### باز کردن فایل با ادیتور

برای باز کردن فایل با ادیتور nano کافیست از دستور nano قبل از مسیر فایل استفاده کنید. لازم به ذکر است بدانید که برای ادیت فایل هایی که به دسترسی روت نیاز دارند باید حتما دسترسی روت را به ابزار داده باشید زیرا در غیر اینصورت به مشکل خواهید خورد. در پایین محیط ابزار nano را مشاهده میکنید.
<p align = "center">
    <img src ="View.png">
</p>
</div>

    $ sudo nano /etc/resolv.conf


---
<div dir='rtl'>

### ذخیره فایل 
برای ذخیره فایل از کلید ترکیبی ctrl + o استفاده کنید. بعد از استفاده از این کلید ترکیبی کلید اینتر را فشار دهید تا تغییرات شما روی فایل اعمال شود.
<p align = "center">
    <img src ="save1.png">
</p>
</div>

    # select the CTRL + O & Enter for Save the file

---
<div dir='rtl'>

### خروج از ادیتور
برای خروج از ادیتور از کلید ترکیبی ctrl + x استفاده کنید. لازم به ذکر است بدانید اگر فایل را ادیت کرده باشید و تغییرات را ذخیره نکرده باشید هنگام خروج از شما سوال پرسیده میشود که آیا مایل به ذخیره تغییرات هستید یا نه، اگر کلید y را فشار دهید و اینتر بزنید فایل شما ذخیره میشود و از ادیتور خارج میشوید. اما اگر کلید n را فشار دهید تغییرات اعمال نمیشود و از ادیتور خارج میشوید.

</div>

    # select the ctrl + x for exit the editor
---
<div dir='rtl'>

### نمایش خطوط در کنار هم
با استفاده از کلیدهای ترکیبی ctrl + j میتوانید فایل را به شکل justify مشاهده کنید . به اینصورت که خطوط فایل شما در کنار هم قرار خواهند گرفت .

</div>

    $ cat amir.txt
    
    # OUTPUT
    # aalskdfapple
      computer
      linux
      android

    $ select the ctrl + j in nano
    
    # OUTPUT
    # aalskdfapple computer linux android
 
---
<div dir='rtl'>

### لیست کردن تمامی دستورات ادیتور
شما میتوانید با استفاده از کلیدهای ctrl + g تمامی دستورات ادیتور را مشاهده کنید.

</div>

    # View The All Command With ctrl + g
---
<div dir='rtl'>

### جستجو در فایل 
شما میتوانید با استفاده از کلید های ترکیبی ctrl + w در فایل به جستجو بپردازید.

</div>

    # select the ctrl + w For Search in the file
---
<div dir='rtl'>

### کپی و کات کردن سریع

به شکل عادی برای انتخاب کردن یک متن در ادیتور از موس استفاده میکنیم و بعد از انتخاب خط های انتخاب شده با کلید های ctrl + c & ctrl + x خطوط را کپی یا کات میکنیم . در ادیتور nano شما میتوانید با استفاده از کلید های ترکیبی ctrl + 6 حالت انتخاب را فعال کرده و بدون استفاده از موس بخشی از متن را انتخاب، و بعد از انتخاب شما میتوانید با کلید های ctrl + c یا ctrl + x بخش خاص را کپی یا کات کنید.
</div>

    # select the ctrl + 6 for enable mark mod
    # select the text with keyboard
    # copy or cut with select the ctrl + c or ctrl + x
---
<div dir='rtl'>

### برگشتن به کاراکتر قبلی و بعدی

شما میتوانید با استفاده از کلید های ترکیبی Ctrl + f & Ctrl + b به کاراکتر بعدی یا قبلی برگردید. با استفاده از کلیدهای ctrl + f میتوانید به کاراکتر بعدی و با استفاده از کلیدهای ctrl + b به کاراکتر قبلی برگردید.
</div>

    # select the Ctrl + b For Go back one character
    # select the Ctrl + f For Go forward one character
---
<div dir='rtl'>

### نمایش انتها و ابتدای خط

با استفاده از کلیدهای home & end میتوانید انتها و ابتدای خطی که در آن حضور دارید را مشاهده کنید. با استفاده از home میتوانید ابتدای خط و با استفاده از end میتوانید انتهای خط را مشاهده کنید.
</div>
    
    # select the Home for Go to beginning of current line
    # select the End for Go to end of current line
---
<div dir='rtl'>

### جابه جا شدن در فایل 
شما میتوانید با استفاده از دکمه های page down & page up در فایل به بالا و پایین جابه جا شوید. با استفاده از page up به بالای فایل و با استفاده از page down به انتهای فایل مهاجرت کنید. در ضمن اگر از کیبوردهایی استفاده میکنید که فاقد دکمه های گفته شده هستند، میتوانید با کلیدهای ترکیبی ctrl + y و ctrl + v به بالا و پایین فایل مهاجرت کنید. با استفاده از ctrl + y به بالای فایل و با استفاده از ctrl + v میتوانید به انتهای فایل مهاجرت کنید.

</div>

    # select the page up For rull up in file
    # select the page down for rull down in file

    # Or

    # select the ctrl + y for rull up in file
    # select the ctrl + v for rull down in file
---

### Author or Authors

- *[Amirhosein](https://github.com/amirhoseinsb)* | **<amirhoseinsohrabi.official@gmail.com>**