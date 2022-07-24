---
title: "Permissions"
date: 2022-07-20T19:18:18+04:30
draft: false
---

<div dir='rtl'>

### فهرست

> - [فهرست](#فهرست)
> - [مقدمه](#مقدمه)
> - [نمایش دسترسی](#نمایش-دسترسی)
> - [انواع دسترسی](#انواع-دسترسی)
> - [مالکیت دسترسی](#مالکیت-دسترسی)
> - [تغییر دسترسی](#تغییر-دسترسی)
> - [تغییر دسترسی با اعداد](#تغییر-دسترسی-با-اعداد)
> - [نویسنده یا نویسندگان](#نویسنده-یا-نویسندگان)

### مقدمه

در هر سیستم عاملی مفهومی تحت عنوان سطح دسترسی وجود دارد. برای هر کاربر در یک
سیستم عامل سطح دسترسی خاصی تعیین می‌شود که مشخص می‌کند 
یک کاربر می‌تواند به چه فایل هایی چه نوع دسترسی هایی داشته باشد.

برای مثال شما می‌توانید برای دیگر کاربران سیستم عامل تایین کنید که آیا می‌توانند
فایل شما بخوانند و یا ویراش کنند و یا حتی فایل اجرایی شما را اجرا کنند یا خیر.

---

### نمایش دسترسی

برای دیدن دسترسی یک فایل یا یک دایرکتوری از ابزار
`ls`
و سوییچ
`l-`
استفاده می‌کنیم، این دستور را که در هر دایرکتوری اجرا کنید، فقط محتوای آن
دایرکتوری را خواهید دید، شما می‌توانید برای دیدن دسترسی های دیگر فایل و یا دایرکتوری ها
مسیر آن ها را به عنوان آرگومان به
`ls -l`
بدهید.

```bash
$ ls -l /usr/bin/bash

# -rwxr-xr-x 1 root root 1404744 مارس    19  2021 /usr/bin/bash
```

خروجی اجرای کامند سه دسترسی متفاوت برای سه مالکیت مختلف را نمایش می‌دهد.
به ترتیب از چپ به راست بعد از 
علامت **-**
سه کاراکتر اول برای مالک فایل
سه کاراکتر بعدی برای گروه فایل و سه کاراکتر آخر برای تعیین دسترسی دیگر کاربران است.

> نکته: اولین علامت که در این مثال - است، مشخص کننده فایل یا دایرکتوری است.
> اگر بجای - کاراکتر 
> ی
> باشد، آن مسیر یک دایرکتوری است.

---

### انواع دسترسی

در لینوکس سه نوع دسترسی مختلف برای یک فایل یا دایرکتوری وجود دارد.
هر دسترسی مجوز هایی را برای یک کابر، گروه و یا پردازش/برنامه ها معین می‌کند.

<div dir='ltr'>

> - x, Executable
>
> اگر یک اسکریپت و یا باینری یک برنامه دسترسی اجرایی داشته باشد
> آن فایل قابل اجرا خواهد بود.

> w, Write
> 
> دسترسی ویراش این قابلیت را به کاربر و یا پردازش می‌دهد تا بتواند یک فایل را ویرایش کند و
> یا فایلی به یک دایرکتوری اضافه کند.

> - r, Read
> 
> این دسترسی کاربر را مجاز می‌کند که محتوای فایل یا دایرکتوری را بتواند بخواند.

</div>

```bash
- r w x
│ │ │ ╰┈can Execute
│ │ ╰┈can Write
│ ╰┈can Read
╰┈d if directory, - if file
```

---

### مالکیت دسترسی

فایل و دایرکتوری ها یک مالک
(owner)
دارند، مالک دسترسی های خودش(owner)،
گروه(group)
و دیگران(others)
را برای یک فایل معین می‌کند.

با اینکار شما دسترسی های متفاوتی برای
مالک, گروه
و
دیگران مشخص می‌کنید.

برای مثال فایل
**bar**
توسط کاربر
**foo**
درست شده است، پس مالک این فایل کاربر
**foo**
است، و به دلیل اینکه هر کاربر عضو گروه خودش است، گروه این فایل هم
گروه
**foo**
خواهد بود.
شما می‌توانید دسترسی اجرای فایل
**bar**
را به گروه هم بدهید، تا با اینکار هر کاربری که عضو گروه
شود بتواند فایل را اجرا کند.
و برای اینکه دیگر کاربران سیستم که عضو این گروه نیستند نتوانند فایل را اجرا و یا ویرایش
کنند باید دسترسی های
`r, x`
را از
**other**
بگیرید.


```bash
# -rwx  r-x  r-x 1 root root 1404744 مارس    19  2021 /usr/bin/bash
   |||  |||  |||   
   |||  |||  ||└─┈Other
   |||  |||  |└─┈Other   
   |||  |||  └─┈Other
   |||  |||
   |||  ||└─┈Group
   |||  |└─┈Group
   |||  └─┈Group
   |||
   ||└─┈User
   |└─┈User
   └─┈User
```

در مثال بالا مالک فایل کاربر
root
و گروه فایل هم گروه
root
است.

---

### تغییر دسترسی

برای ویرایش دسترسی از کامند
`chown`
استفاده می‌کنیم، این کامند از علامت + برای دادن دسترسی و از علامت - برای اخذ دسترسی استفاده می‌کند.

ساختار کامند به این شکل است که اولین آرگومان باید اخذ و یا اضافه کردن یک دسترسی را مشخص کند
سپس مسیر فایل یا دایرکتوری را مشخص می‌کنیم.

برای مثال ما به فایل
bar
دسترسی اجرایی و خواندن می‌دهیم و دسترسی ویرایش را اخذ می‌کنیم.

```bash
chmod +xr bar
chmod -w bar
```

چهار کاراکتر
*a, u, g, o*
مشخص کننده مالکیت دسترسی است. برای مثلا اگر شما بخواهید یک دسترسی
را برای دیگران معین کنید کافی است کاراکتر
`o`
را قبل از علامت معین کننده اخذ و اضافه قرار دهید.

```bash
chmod o-rwx bar
```

---

### تغییر دسترسی با اعداد

هر کاراکتر یک عدد مختص خودش دارد. و به تنهایی نماد یک دسترسی است.
اما این اعداد با جمع شدن با یکدیگر، ترکیب چند دسترسی را مشخص می‌کنند.

<div dir='ltr'>

- r, 4
- w, 2
- x, 1

</div>

برای دادن دسترسی عدد باید دسترسی هر سه مالک دسترسی را مشخص کنیم. برای مثال به فایل
bar
فقط دسترسی خواندن را به هر سه مالک می‌دهیم

```bash
chmod 444 bar
```

اما برای مثال اگر بخواهیم به مالک دسترسی اجرایی هم بدهیم باید عدد 
r
را با عدد
x
جمع کنیم و در اولیل عدد سمت چپ قرار بدهیم

> r+x = 4+1 = 5

```bash
chmod 544 bar
```

---

### نویسنده یا نویسندگان

</div>

- *[Arya](https://github.com/shabane)* | **<m.mohamadshabane@gmail.com>**