
# ساخت کانفیگ Trojan + XTLS

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

۶. در این قسمت نیاز داریم تا از certificate هایی که برای پروتکل TLS ساخته‌ایم استفاده کنیم. اگر این certificate ها را ندارید، لطفا [مستند ساخت TSL Certificate](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md) را دنبال کرده، دامنه و آدرس فایل‌های کلیدهای رمزنگاری را یادداشت کرده و به اینجا برگردید.

در اینجا، از همان نام domain استفاده کنید که در مرحله ساخت certificate استفاده کردید. مطمئن شوید گزینه certificate file path انتخاب شده باشد. برای public key آدرس مربوط به فایل cert.pem را وارد کنید. برای Key آدرس مربوط به فایل private key را وارد نمایید. روش تهیه این فایل‌ها در [مستند ساخت TSL Certificate](https://github.com/iranxray/hope/blob/main/create-tsl-certificate.md) پیشتر شرح داده شده. 

![image](https://user-images.githubusercontent.com/118040490/201599862-aad2e081-b92f-42be-913f-3914066b7715.png)

۷. دکمه Add را بزنید و تمام. خواهید که کانفیگ به موفقیت به فهرست اضافه شده و آماده استفاده می‌باشد.

![image](https://user-images.githubusercontent.com/118040490/201600468-326bfd66-ed7b-40f5-bd69-ca8f1c1171a2.png)

نکته مهم، حتما مطمئن شوید که بعد از ساخت هر کانفیگُ، پورت مربوط به آن کانفیگ بر روی server باز بوده و آماده پذیرش ترافیک ورودی می‌باشد.
