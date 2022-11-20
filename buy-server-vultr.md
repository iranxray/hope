# خرید server از شرکت Vultr

ما برای راه اندازی سیستم عبور از فیلترینگ نیاز به یک server داریم و server هم چیزی نیست جز یک کامپیوتر که از یک شرکت ثالث به صورت ماهانه اجاره می‌کنیم. خرید server از شرکت‌های ثالث مزیت‌های زیادی دارد. مثلا شما لازم نیست که سخت‌افزار را در خانه نگه دارید. امنیت سیستم تا حدود خوبی توسط شرکت ثالث تامین می‌شود. همچنین شما این امکان را خواهید داشت که تعیین کنید کامپیوتری که اجاره می‌کنید در چه کشوری قرار بگیرد. هر چقدر فاصله فیزیکی به ایران کمتر باشد، سرعت سرویس شما هم بیشتر خواهد بود.

در اینجا ما نحوه خرید یک سرویس حداقلی را از vultr آموزش می‌دهیم که بتواند بین ۵۰ تا ۱۰۰ نفر را سرویس دهد. هزینه سرویس ماهانه کمتر از ۱۰ دلار آمریکا خواهد بود.

## گام صفر - نصب SSH

پیش از هر کاری باید SSH را در Windows نصب کنید. SSH به ما امکان می‌دهد تا به کامپیوتری که کرایه می‌کنید متصل شویم. خیلی ساده است. [نحوه نصب SSH در Windows را از اینجا](https://github.com/iranxray/hope/blob/main/install-ssh-windows.md) می‌توانید ببینید. 


## گام اول
اولین گام این هست که وارد [وب‌سایت شرکت vultr](https://www.vultr.com/) بشید.

![image](https://user-images.githubusercontent.com/118040490/202649857-64a6bc5a-e2ba-491f-bc8e-f4b2182805ba.png)


## گام دوم - ساخت حساب کاربری
حالا یک حساب کاربری در vultr می‌سازیم. در اینجا باید کردیت‌ کارت خود را همراه‌ داشته باشید. 
به عنوان نام کاربری باید email خود را وارد کنید. همچنین نیاز دارید که رمز عبور حساب vultr خود را مشخص کنید. در آخر هم دکمه Create Account را کلیک کنید.

![image](https://user-images.githubusercontent.com/118040490/202650479-d807d289-887f-412e-8b31-5aef58cdcc1a.png)

## گام سوم - تکمیل اطلاعات کارت

در این صفحه اطلاعات پرداخت را مشخص کرده و در آخر روی Link Credit Card کلیک کنید.

![image](https://user-images.githubusercontent.com/118040490/202650977-b3fe7c29-ef41-4fc7-8759-09e15619a686.png)

## گام چهارم - تایید آدرس ایمیل
در اینجا باید به ایمیل خود مراجعه کنید. ایمیلی از طرف Vultr به شما ارسال شده تا آدرس ایمیل شما تایید شود. بر روی لینک دریافتی کلیک کنید.


## گام پنجم - خرید server

در ابتدا، از نوار سمت چپ گزینه Products را انتخاب کنید و بعد بر روی Deploy Server کلیک کنید.

![image](https://user-images.githubusercontent.com/118040490/202651690-40addce8-3b9c-4782-af6f-1eb4537fa9a7.png)

در صفحه باز شده ابتدا Cloud Compute رو انتخاب کنید و بعد هم گزینه Intel High Performance را بزنید.

![image](https://user-images.githubusercontent.com/118040490/202652163-0baf1657-85e5-47c7-bb1d-6f4cddb10e34.png)

صفحه رو اسکرول کنید و پایین تر بروید. حالا نوبت به انتخاب محل server رسیده. ما توصیه می‌کنیم که server شما در نزدیک‌ترین فاصله به ایران باشد. برای همین پیشنهاد می‌کنیم طبق گزینه زیر دهلی هند را انتخاب کنید.

![image](https://user-images.githubusercontent.com/118040490/202653326-fdc71777-b18b-4814-8d64-f48b62a34fc0.png)


سپس، مطابق با تصویر زیر سیستم عامل را انتخاب کنید. پیشنهاد ما سیستم Ubuntu نسخه 22.04 LTS می‌باشد.

![image](https://user-images.githubusercontent.com/118040490/202653834-a7ccd199-96d2-4e8f-9889-fec5b5110fbd.png)

در آخر، نوبت به انتخاب مشخصات server می‌رسد. می‌توانید ارزان‌ترین را که server شش دلاری است انتخاب کنید.

![image](https://user-images.githubusercontent.com/118040490/202654079-c139b1b9-5e32-46e9-b30b-94a5c58805c3.png)

می‌توانید با غیرفعال کردن Autobackup کمی در هزینه‌ها صرفه‌جویی کنید.

![image](https://user-images.githubusercontent.com/118040490/202654289-ffc56284-90f7-4711-8cd9-a1fd80e83589.png)

در آخر هم می‌بایست به دلخواه نامی را برای کامپیوتری که کرایه کرده‌اید انتخاب کنید. اینجا ما نام را iranxray وارد کردیم.
![image](https://user-images.githubusercontent.com/118040490/202821698-baffacf4-0bfd-4abc-8758-d93f18edfa98.png)

## گام ششم - نصب

حالا نوبت شماست که منتظر بمانید تا Vultr سیستمی را که درخواست داده‌اید راه‌اندازی کند.

![image](https://user-images.githubusercontent.com/118040490/202821774-a2e8d125-29c7-4b59-88e7-9fed93adee6a.png)

وقتی وضعیت به Running تغییر کرد یعنی سیستم شما راه‌اندازی شده. تبریک.

![image](https://user-images.githubusercontent.com/118040490/202891872-4da4d6fd-14a2-466c-b381-7f065b39e8be.png)
## گام هفتم - اتصال به سیستم 

حالا که سیستم راه‌اندازی شده بایستی به آن متصل شویم و یا به قول کامپیوتری‌ها SSH کنیم. برای اینکه به کامپیوتر متصل شویم، نیاز هست تا مراحل زیر را طی کنیم.

* اول باید آدرس IP و نام کاربری و رمز عبور سیستم را پیدا کنیم. این‌ها به طور خودکار توسط vultr برای ما ساخته شده اند. ابتدا، بر روی Server Details کلیک کنید.

![image](https://user-images.githubusercontent.com/118040490/202822559-969cb093-3c0f-4a83-a049-990e2060f70a.png)

در صفحه بعد، آدرس IP‌ و Username‌ و Password را مشاهده می‌کنید. از این‌ها در گام‌های بعدی استفاده می‌کنیم.

![image](https://user-images.githubusercontent.com/118040490/202822686-e080ccc7-aa1c-40ef-a6e5-4cb6c9e91df5.png)

* حالا با داشتن این‌ها می‌توانیم به server متصل شویم. پیش‌فرض ما اینجا این هست که شما [SSH را در Windows 10 و یا Windows 11‌](https://github.com/iranxray/hope/blob/main/install-ssh-windows.md) نصب کرده اید. دکمه Start را بزنید و تایپ کنید cmd و Command Promt را انتخاب کنید.

![image](https://user-images.githubusercontent.com/118040490/202823343-c219d2b3-bed2-491f-90da-aa5f42eb609f.png)


* در صفحه باز شده دستور زیر را وارد کنید. به جای IP و username مقادیری را که در مرحله قبلی کپی کرده‌اید وارد کنید.

```bash
ssh username@ip
```

![image](https://user-images.githubusercontent.com/118040490/202823632-f0c14a51-d58b-4a12-8cbd-079373b1b574.png)

* جواب سوالی بعدی را yes بدهید.

![image](https://user-images.githubusercontent.com/118040490/202823774-f14d9bbd-fee9-45cb-9754-6427bcccf888.png)

* در این مرحله باید رمز عبور را وارد کنیم. دقت کنید که وقتی رمز عبور را تایپ می‌کنید، حروف به شما نشان داده نمی‌شوند. وقتی رمز را وارد کردید enter را بزنید.

![image](https://user-images.githubusercontent.com/118040490/202823939-7f0b45fd-ddfe-4f69-b18b-56e576c18783.png)

* اگر همه چیز درست پیش‌ رفته باشد، اینجا کار تمام هست و باید پیامی شبیه شکل زیر را در صفحه ببینید.

![image](https://user-images.githubusercontent.com/118040490/202824091-e15f3ee4-e727-4d5e-87eb-cec8af252fce.png)

تبریک می‌گوییم. حالا که به server متصل شده‌اید، می‌توانید به [راهنمای نصب xray](https://github.com/iranxray/hope/blob/main/install-xui.md) مراجعه کنید تا نرم ‌افزار عبور از فیلترینگ را در سیستم خود نصب کنید.
