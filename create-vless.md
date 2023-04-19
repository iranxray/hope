# ساخت کانفیگ VLESS + TCP + XTLS

⚠️ این روش منسوخ شده است. لطفا از [پروتکل Reality](https://github.com/iranxray/hope/blob/main/create-vision-reality.md) استفاده کنید.


پیش از شروع لازم است که دو نکته را با شما در میان بگذاریم. اول اینکه، توصیه ما [استفاده از پروتکل Trojan‌](https://github.com/iranxray/hope/blob/main/create-trojan.md) می‌باشد چرا که کارایی و امنیت بهتری دارد. نکته دوم هم اینکه استفاده از VLESS به VMESS ارجحیت دارد. در مقاله ابتدایی شرح داده‌ایم که [چرا VMESS امن نیست](https://github.com/iranxray/hope#%D9%BE%D8%B1%D9%88%D8%AA%DA%A9%D9%84-vmess-%D8%BA%DB%8C%D8%B1-%D8%A7%DB%8C%D9%85%D9%86-skull).

در صورت تمایل، برای یادگیری در مورد جزییات فنی این پروتکل به [مطلبی که در مورد VLESS](https://github.com/iranxray/hope#%D9%BE%D8%B1%D9%88%D8%AA%DA%A9%D9%84-vless-%D8%A7%DB%8C%D9%85%D9%86-sunglasses) تهیه کرده‌ایم رجوع کنید.

## گام اول

بر روی علامت + کلیک کنید.

![image](https://user-images.githubusercontent.com/118040490/201569651-5ae49659-70f3-4a43-a4ce-5a7ed8f87df1.png)

صفحه ساخت کانفیگ باز می‌شود.

![image](https://user-images.githubusercontent.com/118040490/201569842-bba57b9d-4144-4c44-a706-257cacc3d6b8.png)

## گام دوم

برای این کانفیگ نامی انتخاب کنید. ما ترجیح برای نام‌گذاری از یک فرمت مشخص استفاده کنیم. مثلا اگر پروتکل VLESS برای دوستی به نام رضا تهیه کرده باشیم، در قسمت remarks نام را به صورت vless-reza انتخاب می‌کنیم.

![image](https://user-images.githubusercontent.com/118040490/201570179-0ffbe326-db4a-4cff-a702-1633061d3bfc.png)

## گام سوم

حال برای پروتکل گزینه vless را انتخاب کنید. 

![image](https://user-images.githubusercontent.com/118040490/201570343-5966368f-7dc3-47e9-a6c4-f5e3ed5525a5.png)

## گام چهارم

هر کانفیگ، به یک پورت از سیستم شما نیاز خواهد داشت. این پورت توسط برنامه برای شما انتخاب شده اما در صورتی که بخواهید می‌توانید تغییرش دهید. ما پیشنهاد می‌کنیم که این مقدار را به 80 تغییر دهید. استفاده از پورت 80 شناسایی ترافیک شما را برای فیلترچی دشوارتر خواهد کرد..

![image](https://user-images.githubusercontent.com/118040490/201583336-e38c5121-2f20-4911-a236-60a0d81e82a0.png)

 :star: هر پورت فقط توسط یک کانفیگ می‌تواند استفاده شود. یعنی فقط یک کانفیگ می‌توانید با پورت 80 داشته باشید و بقیه کانفیگ‌ها باید از پورت‌های دیگر استفاده کنند. اما محدودیتی بر روی تعداد کاربر‌هایی که می‌توانند از یک کانفیگ استفاده کنند وجود ندارد. یعنی می‌توانید یک کانفیگ را با کاربران مختلف به اشتراک بگذارید. ما پیشنهاد می‌کنیم برای مصارف شخصی فقط یک کانفیگ داشته باشید و آن را روی پورت 80 تعریف کنید.

## گام پنجم

در این مرحله، مشخص می‌کنید که از این کانفیگ در مجموع چه میزان حجم از داده دانلود و آپلود می‌توانیم داشته باشیم. مثلا اگر عدد 20 را مشخص کنیم، آنگاه کاربران این کانفیگ در مجموع به اندازه 20Gb می‌توانند از سرور ما داده دانلود و یا آپلود کنند. به محض اینکه داده مصرفی تمام شود، این کانفیگ به صورت خودکار غیرفعال خواهد شد. اینجا ما عدد ۳۰ را مشخص می‌کنیم.

![image](https://user-images.githubusercontent.com/118040490/201583716-95b49100-cdb7-4ecf-a46b-7ff5569de491.png)
 
 ## گام ششم
 
در این قسمت نیاز داریم تا از certificate هایی که برای پروتکل TLS ساخته‌ایم استفاده کنیم. اگر این certificate ها را ندارید، لطفا [مستند ساخت TLS Certificate](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md) را دنبال کرده، دامنه و آدرس فایل‌های کلیدهای رمزنگاری را یادداشت کرده و به اینجا برگردید.

در اینجا، از همان نام domain استفاده کنید که در مرحله ساخت certificate استفاده کردید. مطمئن شوید گزینه certificate file path انتخاب شده باشد. برای public key آدرس مربوط به فایل fullchain.pem را وارد کنید. برای Key آدرس مربوط به فایل privkey.pem را وارد نمایید. روش تهیه این فایل‌ها در [مستند ساخت TLS Certificate](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md) شرح داده شده بود. 

![image](https://user-images.githubusercontent.com/118040490/201596466-93e8f7cf-b15b-4bfd-a002-5d427efb9a1d.png)



:star:
نکته‌ خیلی مهم: اگر از certificate معتبر و domain استفاده می‌‌کنید، مطمئن باشید که نوار آدرس در مرورگر شما به صورت http://IP:port نمی‌باشد. شما باید از آدرس domain استفاده کنید. این موضوع در [مقاله ساخت certificate معتبر](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md#%DA%AF%D8%A7%D9%85-%D9%87%D9%81%D8%AA%D9%85-1) توضیح داده شده بود.

![image](https://user-images.githubusercontent.com/118040490/203471327-0557d006-325b-435a-856d-c6a5ef1f57aa.png)
![image](https://user-images.githubusercontent.com/118040490/203471267-5f3bb039-5864-4614-9e12-69768fcf57a4.png)

## گام هفتم

دکمه Add را بزنید و تمام. خواهید که کانفیگ به موفقیت به فهرست اضافه شده و آماده استفاده می‌باشد.

![image](https://user-images.githubusercontent.com/118040490/201597880-7654ba1e-792b-4e09-a26a-f28ab4ffaaca.png)


نکته مهم، حتما مطمئن شوید که بعد از ساخت هر کانفیگ، پورت مربوط به آن کانفیگ بر روی server باز بوده و آماده پذیرش ترافیک ورودی می‌باشد. برای این موضوع به مستندات شرکتی که server شما را میزبانی می‌کند رجوع نمایید.

## گام هشتم

حالا که کانفیگ با موفقیت ساخته شده، نوبت به اشتراک‌گذاری کانفیگ با کاربر عزیز رسیده تا کمک‌ کنیم به اینترنت آزاد متصل شود. می‌توانید کانفیگ را به طریق زیر کپی نمایید.

![image](https://user-images.githubusercontent.com/118040490/201850200-039e1f29-332e-4fa8-bb49-03cc4625fa47.png)

![image](https://user-images.githubusercontent.com/118040490/201850330-6a910c59-5ff8-44ba-a77e-8dfff778d6bd.png)

![image](https://user-images.githubusercontent.com/118040490/201850439-541d423e-60d5-45f6-9105-e02fa6c0629f.png)

## گام نهم

حالا که کانفیگ کپی شده، می‌توانید یاد بگیرید چطور به [اندروید](https://github.com/iranxray/hope/blob/main/install-android.md) و یا [آیفون](https://github.com/iranxray/hope/blob/main/install-iphone.md) این تنظیمات را اضافه کنید
