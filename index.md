<div dir="rtl">
<h4 style="text-align: center">باسمه تعالی</h4>
<h4>محمدحسین ایزدی  92106356</h4>
</div>
<h2> When ebay implements a keylogging feature</h2>

<div dir="rtl">

<strong>ترجمه:</strong>
<p>
من  به تازگی هنگام کار با نرم افزار Ebay bug bounty program متوجه شدم سایت Ebay در صفحه ریست کردن رمز عبور زمانی که رمز عبور جدید را تایپ می کنم سایت ده ها درخواست را به سرور های سایت ارسال می کند. در واقع سایت به ازای هر کاراکتر که کاربر تایپ می کند در خواست POST به /PWDStrength  ارسال می کند که  body آن شامل رمز عبور، ایمیل و نام کاربری کاربر است. به نظر می رسد که آن ها یک ابزار سمت سرور برای اندازه گیری قوی بودن رمز پیاده سازی کرده اند که یک شیوه معمول در web-application هاست. به طور معمول این کار در سمت کاربر به وسیله JavaScript انجام می شود ولی افزودن بررسی های سمت سرور  هم معمول است، اما فرستادن هر کاراکتری که کاربر تایپ می کند و بررسی مناسب بودن آن در سمت سرور و فرستادن پاسخ "خوب" یا "بد" ایده ی چندان خوبی نیست و بیشتر شبیه یک key-logger کوچک است. تصور کنید که کاربر رمزی را که در یک سرویس دیگر استفاده می کند را در فیلد رمز وارد کند و پیش از زدن کلید ارسال به سرور های ebay متوجه اشتباهش شود، کاربر انتظار دارد که هیچ داده ای قبل از زدن کلید ارسال به سرور ها ارسال نشود. من این موضوع را به تیم امنیتی ebay گزارش کردم ولی آن ها در جواب گفتند که نمی توانند علت این کار را به من بگویند.
</p>
<p>
مورد عجیب دیگر این بود که در Ebay customer control panel هنگام تغییر رمز هم همین عمل انجام می شد با این تفاوت که برای ارسال هر کاراکتری که تایپ می شد از درخواست GET استفاده می شد اما دیگر شامل نام کاربری و ایمیل نبود. متغیر هایی که به روش GET ارسال می شوند می توانند به وسیله پروکسی ها کش شوند و در log-files ذخیره شوند در نتیجه معمولا توسط افراد بیشتری قابل دسترسی هستند. البته درخواست ها همگی با پروتکل https ارسال می شدند در نتیجه third-party proxies نمی توانند url یا http header و یا body را ببینند.
</p>
<strong>درک مطلب:</strong>
<p>
سایت ebay در قسمت تغییر رمز به ازای هر کاراکتری که کاربر در فیلد رمز وارد می کند به سرور های خود یک درخواست از نوع POST ارسال می کند که بدنه آن شامل رمز عبور نوشته شده، ایمیل و نام کاربری کاربر است. به نظر می رسد که این عمل برای بررسی قوی بودن رمز باشد اما ارسال تک تک حروف قبل از زدن کلید ارسال کاری عجیب به نظر می رسد. به عنوان مثال اگر کاربر رمز یک سرویس دیگری را که از آن استفاده می کند به اشتباه در فیلد وارد کند و قبل از زدن کلید ارسال متوجه اشتباهش شود، با این که انتظار دارد به سرور های ebay داده ای ارسال نشود ولی با این حال رمزش ارسال می شود. 
</p>
<p>
این مسئله در Ebay customer control panel هم وجود دارد با این تفاوت که در خواست ها به روش GET  ارسال می شوند و دیگر ایمیل و نام کاربری به همراه آن ارسال نمی شود. این مسئله باعث می شود که رمز وارد شده در url ارسالی وجود داشته باشد و به همین دلیل پروکسی ها می توانند با ذخیره url ها در log-files به رمز دسترسی داشته باشند و افرادی هم که به این فایل ها دسترسی دارند می توانند رمز را آن استخراج کنند.
</p>

<strong>منبع:</strong>
<p>
https://slashcrypto.org/2016/06/29/Ebay/
</p>
</div>




## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/mh-izadi/WebResearchAssignment/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mh-izadi/WebResearchAssignment/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
