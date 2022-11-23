
# ساخت کانفیگ Trojan + XTLS
در صورت تمایل، برای یادگیری در مورد جزییات فنی این پروتکل به [مطلبی که در مورد Trojan](https://github.com/iranxray/hope#%D9%BE%D8%B1%D9%88%D8%AA%DA%A9%D9%84-trojan-%D8%A7%DB%8C%D9%85%D9%86-sunglasses) تهیه کرده‌ایم رجوع کنید


۱. در صفحه Inbound Lists بر روی علامت + کلیک کنید.

![image](https://user-images.githubusercontent.com/118040490/201569651-5ae49659-70f3-4a43-a4ce-5a7ed8f87df1.png)

صفحه ساخت کانفیگ باز می‌شود.

![image](https://user-images.githubusercontent.com/118040490/201569842-bba57b9d-4144-4c44-a706-257cacc3d6b8.png)

۲. برای این کانفیگ نامی انتخاب کنید. ما ترجیح برای نام‌گذاری از یک فرمت مشخص استفاده کنیم. مثلا اگر پروتکل Trojan برای دوستی به نام رضا تهیه کرده باشیم، در قسمت remarks نام را به صورت vless-reza انتخاب می‌کنیم.

![image](https://user-images.githubusercontent.com/118040490/201599300-472a07ea-5070-423e-a011-c9764b6ca528.png)


۳. حال برای پروتکل گزینه Trojan را انتخاب کنید. 

![image](https://user-images.githubusercontent.com/118040490/201599420-cb61c301-35c3-47b7-aa52-498b36ee632b.png)

۴. هر کانفیگُ، به یک پورت از سیستم شما نیاز خواهد داشت. این پورت توسط برنامه برای شما انتخاب شده اما در صورتی که بخواهید می‌توانید تغییرش دهید. ما اینجا تغییری نمی‌دهیم.

![image](https://user-images.githubusercontent.com/118040490/201599517-6546afb1-d28d-4edd-ad1d-406a81a1a984.png)

۵. در این مرحله، مشخص می‌کنید که از این کانفیگ در مجموع چه میزان حجم از داده دانلود و آپلود می‌توانیم داشته باشیم. مثلا اگر عدد 20 را مشخص کنیم، آنگاه کاربران این کانفیگ در مجموع به اندازه 20Gb می‌توانند از سرور ما داده دانلود و یا آپلود کنند. به محض اینکه داده مصرفی تمام شود، این کانفیگ به صورت خودکار غیرفعال خواهد شد. اینجا ما عدد ۳۰ را مشخص می‌کنیم.

![image](https://user-images.githubusercontent.com/118040490/201599616-96f49d37-f06d-499e-bfb2-75d9688cfa33.png)

۶. در این قسمت نیاز داریم تا از certificate هایی که برای پروتکل TLS ساخته‌ایم استفاده کنیم. اگر این certificate ها را ندارید، لطفا [مستند ساخت TLS Certificate](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md) را دنبال کرده، دامنه و آدرس فایل‌های کلیدهای رمزنگاری را یادداشت کرده و به اینجا برگردید.

در اینجا، از همان نام domain استفاده کنید که در مرحله ساخت certificate استفاده کردید. مطمئن شوید گزینه certificate file path انتخاب شده باشد. برای public key آدرس مربوط به فایل fullchain.pem را وارد کنید. برای Key آدرس مربوط به فایل privkey.pem را وارد نمایید. روش تهیه این فایل‌ها در [مستند ساخت TLS Certificate](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md) شرح داده شده بود. 

![image](https://user-images.githubusercontent.com/118040490/201599862-aad2e081-b92f-42be-913f-3914066b7715.png)



:star:
نکته‌ خیلی مهم: اگر از certificate معتبر و domain استفاده می‌‌کنید، مطمئن باشید که نوار آدرس در مرورگر شما به صورت http://IP:port نمی‌باشد. شما باید از آدرس domain استفاده کنید. این موضوع در [مقاله ساخت certificate معتبر](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md#%DA%AF%D8%A7%D9%85-%D9%87%D9%81%D8%AA%D9%85-1) توضیح داده شده بود.

![image](https://user-images.githubusercontent.com/118040490/203471327-0557d006-325b-435a-856d-c6a5ef1f57aa.png)
![image](https://user-images.githubusercontent.com/118040490/203471267-5f3bb039-5864-4614-9e12-69768fcf57a4.png)

۷. دکمه Add را بزنید و تمام. خواهید که کانفیگ به موفقیت به فهرست اضافه شده و آماده استفاده می‌باشد.

![image](https://user-images.githubusercontent.com/118040490/201600468-326bfd66-ed7b-40f5-bd69-ca8f1c1171a2.png)
 
۸. نکته مهم، حتما مطمئن شوید که بعد از ساخت هر کانفیگ، پورت مربوط به آن کانفیگ بر روی server باز بوده و آماده پذیرش ترافیک ورودی می‌باشد. برای این موضوع به مستندات شرکتی که server شما را میزبانی می‌کند رجوع نمایید. ما هم برای سرورهای که از Vultr تهیه شده‌اند، مستندی تهیه کرده‌ایم که [نحوه باز کردن port](https://github.com/iranxray/hope/blob/main/open-server-port.md) را آموزش می‌دهد. از روی فهرست می‌توانید ببینید که کدام port را لازم هست باز کنید.

![image](https://user-images.githubusercontent.com/118040490/202892935-8b4e4e06-5115-47b9-b0d5-ac464d986963.png)

۹. حالا که کانفیگ با موفقیت ساخته شده، نوبت به اشتراک‌گذاری کانفیگ با کاربر عزیز رسیده تا کمک‌ کنیم به اینترنت آزاد متصل شود. می‌توانید کانفیگ را به طریق زیر کپی نمایید.

![image](https://user-images.githubusercontent.com/118040490/201850200-039e1f29-332e-4fa8-bb49-03cc4625fa47.png)

![image](https://user-images.githubusercontent.com/118040490/201850330-6a910c59-5ff8-44ba-a77e-8dfff778d6bd.png)

![image](https://user-images.githubusercontent.com/118040490/201850439-541d423e-60d5-45f6-9105-e02fa6c0629f.png)

۹. حالا که کانفیگ کپی شده، می‌توانید یاد بگیرید چطور به [اندروید](https://github.com/iranxray/hope/blob/main/install-android.md) و یا [آیفون](https://github.com/iranxray/hope/blob/main/install-iphone.md) این تنظیمات را اضافه کنید.
