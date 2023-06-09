# نصب V2RayN بر روی ویندوز

بر روی ویندوز از یک نرم‌افزار open source به نام [V2RayN](https://github.com/2dust/v2rayN) استفاده می‌کنیم.

## پیش‌نیاز

برای نصب V2RayN، در ابتدا نیاز خواهید داشت تا [برنامه دات‌نت](https://download.visualstudio.microsoft.com/download/pr/513d13b7-b456-45af-828b-b7b7981ff462/edf44a743b78f8b54a2cec97ce888346/windowsdesktop-runtime-6.0.15-win-x64.exe) را به عنوان پیش‌نیاز نصب کنید. در غیر این صورت قادر نخواهید بود که V2RayN را اجرا کنید.

## گام اول

در ابتدا باید برنامه V2RayN را دانلود کنیم. بر روی این [لینک](https://github.com/2dust/v2rayN/releases/tag/6.23) کلیک کنید و فایل ‍`v2rayN-With-Core.zip` را دانلود کنید. 

![image](https://github.com/iranxray/hope/assets/118040490/d6f1ad0c-5ecc-42f0-bdf3-5009337a7f43)


## گام دوم

دانلود که تمام شد، فایل را unzip‌ کنید و فایل V2rayN.exe را باز کنید. 


![image](https://user-images.githubusercontent.com/118040490/203481188-65c8bec6-54f8-48bb-8f3a-6ba36a06ca70.png)

## گام سوم

برنامه داخل System Tray قرار گرفته و از آنجا می‌توانید برنامه را باز کنید.

![image](https://user-images.githubusercontent.com/118040490/203481553-458b7981-bc98-4b7e-8ef9-b2b77017abd3.png)


## گام چهارم
برنامه را که باز می‌کنید همه نوشته‌ها به چینی است. اگر چینی بلد نیستید، می‌توانیم زبان را به انگلیسی تغییر دهیم.

![image](https://github.com/iranxray/hope/assets/118040490/4d568f66-092a-4f79-880e-191f829ff745)
![image](https://github.com/iranxray/hope/assets/118040490/3e6c2354-6c93-42da-a173-24509dee7082)


نیاز دارید تا اپلیکیشن را ببندید و مجدد باز کنید. وقتی مجدد برنامه را باز می‌کنید همه چیز به انگلیسی خواهد بود.

![image](https://github.com/iranxray/hope/assets/118040490/8cc6769b-da77-41de-91e9-402270e71891)

## گام پنجم

کانفیگی که به شما داده شده است را کپی کنید. سپس به طریق زیر می‌توانید کانفیگ را به برنامه اضافه کنید.

![image](https://github.com/iranxray/hope/assets/118040490/0763aefc-ed47-4cd8-bc1f-58da0e2bb89f)

## گام ششم
بعد از اضافه شدن کانفیگ، نیاز هست تا پروکسی را بر روی سیستم فعال کنیم.

![image](https://github.com/iranxray/hope/assets/118040490/80a6e8c3-cafa-4db6-bf72-af1c49c748b1)

## گام هفتم
در آخر هم تنظیم می‌کنیم تا تمام ارتباطات سیستم شما از روی پروکسی عبور کند. گزینه Global را انتخاب کنید.

![image](https://github.com/iranxray/hope/assets/118040490/2544b3fb-aef1-48ce-a849-d0632b8e8fb5)

## گام هشتم
برای جلوگیری از شناسایی و IP Leak باید یک تغییر دیگر هم بدهیم. مطابق تصاویر زیر به صفحه DNS بروید و مقدار `1.1.1.1,8.8.8.8` را وارد کنید.

![image](https://github.com/iranxray/hope/assets/118040490/79075369-4c3a-4a72-a833-5f59694d7b6f)
![image](https://github.com/iranxray/hope/assets/118040490/f2ba3165-29d8-4e3f-a793-6af7f3e0d3ab)



تمام. حالا شما باید به اینترنت آزاد دسترسی داشته باشید.



# باز کردن سایت‌های ایرانی بدون عبور ترافیک از VPN
بسیاری از سایت‌های داخلی به شما اجازه نخواهند داد که هنگام اتصال به VPN‌ از آن‌ها استفاده کنید. خوش‌بختانه می‌توانیم V2RayN را به گونه‌ای تنظیم کنیم که ترافیک‌های داخلی را از فیلتر شکن عبور ندهد.

## گام اول
در ابتدا از روی منوی Settings باید Routing را انتخاب کنید.

![image](https://github.com/iranxray/hope/assets/118040490/d6898409-5015-4ef5-bfa6-e546fcce3f4e)

## گام دوم
گزینه Whitelist را انتخاب کنید.

![image](https://github.com/iranxray/hope/assets/118040490/117623e3-1de8-4d01-bead-798ef1ce5dc6)

## گام سوم
در پنجره باز شده گزینه Add Rule را انتخاب کنید.
![image](https://github.com/iranxray/hope/assets/118040490/91e04edf-bfbf-4c61-bb8b-885e0399b987)

## گام چهارم
در پنجره باز شده گزینه direct را انتخاب کنید. همچنین در جعبه IP باید مقدار ‍`geoip:ir` را وارد نمایید.
![image](https://github.com/iranxray/hope/assets/118040490/c30b4b73-c811-4014-b37b-919c3b770d0b)

## گام پنجم
تغییرات را با فشردن دکمه Confirm‌ ذخیره کنید. حالا بایستی ترافیک‌های داخلی به طور مستقیم از شبکه داخلی ایران عبور کنند.
