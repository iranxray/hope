# ساخت کانفیگ ارتباطی در X-UI
اینجا پیش‌فرض ما این می‌باشد که شما [Kafka را بر روی سیستم خود نصب](https://github.com/iranxray/hope/blob/main/install-xui.md) کرده اید. در اینجا توضیح خواهیم داد که چطور می‌توانید برای کاربران خود کانفیگ‌های مبتنی بر پروتکل VLESS و پروتکل Trojan تهیه کنید..

برای ساخت پروتکل‌های ارتباطی باید به صفحه Inbounds برویم. در عکس رو به رو، مشاهده می‌کنید که بر روی سرور ما تعدادی کانکشن وجود دارد و نشان داده می‌شود که چه میزان دانلود و آپلود از طریق سرور ما صورت گرفته است.

![image](https://user-images.githubusercontent.com/118040490/232974630-6252fe45-a387-4028-9aff-b5a26ac54ab8.png)

## ساخت Reality (پیشنهاد ما)
لطفا به [مقاله ساخت Reality](https://github.com/iranxray/hope/blob/main/create-vision-reality.md) رجوع کنید

## ساخت Trojan (روش منسوخ)
لطفا به [مقاله ساخت Trojan](https://github.com/iranxray/hope/blob/main/create-trojan.md) رجوع کنید.


## ساخت VLESS+XTLS (روش منسوخ)
لطفا به [مقاله ساخت VLESS](https://github.com/iranxray/hope/blob/main/create-vless.md) رجوع کنید.

## ساخت VLESS بدون رمزنگاری XTLS (روش منسوخ)
لطفا به [مقاله ساخت VLESS بدون رمزنگاری](https://github.com/iranxray/hope/blob/main/create-vless-without-tls.md) رجوع کنید.


## ساخت VMESS (روش منسوخ)
به دلایل ضعف‌های امنیتی VMESS، ما نحوه ساخت VMESS را آموزش نمی‌دهیم. برای اطلاع از جزییات امنیتی VMESS می‌توانید به [مقاله ما](https://github.com/iranxray/hope#%D9%BE%D8%B1%D9%88%D8%AA%DA%A9%D9%84-vmess-%D8%BA%DB%8C%D8%B1-%D8%A7%DB%8C%D9%85%D9%86-skull) رجوع کنید. مشکل امنیتی VMESS‌ این است که GFW به راحتی می‌تواند ترافیک آن را تشخیص دهد و احتمال بسته شدن server شما بالا خواهد رفت.
