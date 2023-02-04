# مسدودسازی سایت‌ها و اپلیکیشن‌های ایرانی

سیستم فیلترینگ از روش‌های متنوعی استفاده می‌کند تا بتواند «حدس بزند» یک IP متعلق به پروکسی سرور می‌باشد یا نه. در چین، یکی از روش‌هایی که GFW استفاده می‌کند این است که اگر از یک سرور خارجی درخواستی به سمت سایت‌های داخلی چینی بیاید، آن را مسدود می‌کند. حدس می‌زنیم که در ایران هم از سیستم مشابهی استفاده می‌شود. 


وقتی که گوشی کاربر به پروکسی ‌سرور متصل نباشد، تمامی درخواست‌ها به وب‌سایت‌ها و اپلیکیشن‌های ایرانی در درون شبکه اینترنت ایران صورت خواهد گرفت. شبیه شکل زیر:

![image](https://user-images.githubusercontent.com/118040490/216741378-5d1168cb-e79c-4ab7-ac33-29cf25f7d359.png)


اما فرض کنید گوشی کاربر به پروکسی سرور شما - که در خارج از کشور قرار گرفته - متصل باشد. در این صورت، تمامی درخواست‌های کاربر برای باز کردن وب‌سایت‌ها و اپلیکیشن‌های داخلی از سمت سرور شما صورت خواهد گرفت. شبیه شکل زیر. همانطور که در تصویر می‌بینید، در این حالت از یک IP‌ خارج از کشور درخواست به سمت وب‌سایت‌های داخلی ارسال خواهد شد. همین اتفاق برای فیلترچی دلیل کافی خواهد بود تا به IP سرور شما مشکوک بشود.

![image](https://user-images.githubusercontent.com/118040490/216741596-fae3d86b-e12d-433e-92e5-c9cd6fae75fc.png)

بهترین راه حل برای رفع این مشکل این است که کاربران مراقب باشند که در هنگام اتصال به پروکسی از شبکه‌ داخلی ایران استفاده نکنند. برخی از اپلکیشن‌ها مثل V2RayNG به شما این امکان را می‌دهند که مشخص کنید ترافیک چه اپلیکیشن‌هایی می‌تواند از پروکسی عبور کند. اما یک راه حل دیگر استفاده از مکانیزمی است که در سامانه XRay به نام Routing شناخته می‌شود.

# مکانیزم Routing
این مکانیزم که در Xray‌ تعبیه شده به شما اجازه می‌دهد که مشخص کنید چه ترافیکی می‌تواند از پروکسی سرور شما عبور کند. مثلا می‌توانید مشخص کنید تمام دامنه‌های ir مسدود شوند یا می‌توانید بگویید که یک دامنه خاص مثه digikala.com‌ نباید از سرور شما قابل دسترس باشد. در نتیجه اعمال این تغییرات، کاربران پروکسی سرور شما نمی‌توانند از وب‌سایت‌های داخلی استفاده کنند. مکانیزم routing در [مستندات رسمی XRay](https://xtls.github.io/config/routing.html#routingobject) توضیح داده شده است.

## گام اول
برای اعمال Routing ما فرض می‌کنیم که شما X-UI را بر روی سرور خود [نصب کرده‌اید](https://github.com/iranxray/hope/blob/main/install-xui.md) و از آخرین نسخه Xray استفاده می‌کنید. برای به روز رسانی نسخه Xrayِ، کافی است در داشبورد X-UI بر روی version کلیک کنید و در پنجره‌ای که باز‌ می‌شود آخرین نسخه را انتخاب کنید.

![image](https://user-images.githubusercontent.com/118040490/216742295-587863ef-59a4-4f63-94e6-92f5ea9fa7bd.png)

## گام دوم
در ابتدا لازم داریم تا فهرست تمام وب‌سایت‌ها و اپلیکیشن‌های فارسی را بر روی سرور دانلود کرده و در فولدر Xray‌ قرار دهیم. (وقتی که X-UI‌ را نصب می کنید، سیستم XRay در آدرس ‍‍`usr/local/x-ui/bin` نصب خواهد شد.)

حالا به سرور SSH‌ بزنید و دستورات زیر را سطر به سطر جداگانه اجرا کنید تا فهرست دامنه‌های داخلی را بر روی سرور دانلود کنیم.

```bash
sudo -i
cd /usr/local/x-ui/bin
wget https://github.com/chiroots/iran-hosted-domains/releases/download/202301210059/iran.dat
wget https://github.com/v2fly/domain-list-community/releases/latest/download/dlc.dat
```
## گام سوم
حالا که فهرست دامنه‌ها بارگذاری شده، نوبت به این می‌رسد که مشخصا به Xray بگوییم که وب‌سایت‌های ایرانی را مسدود کند. برای این کار داخل پنل X-UI‌ شوید و به قسمت تنظیمات بروید.

![image](https://user-images.githubusercontent.com/118040490/216742902-538975b9-30f2-449b-80fe-d5bf890a2ae3.png)

## گام چهارم
در این گام، متن زیر را کامل کپی کرده و جایگزین مقدار قبلی در تنظیمات X-UI بکنید.

```json
{
  "api": {
    "services": [
      "HandlerService",
      "LoggerService",
      "StatsService"
    ],
    "tag": "api"
  },
  "inbounds": [
    {
      "listen": "127.0.0.1",
      "port": 62789,
      "protocol": "dokodemo-door",
      "settings": {
        "address": "127.0.0.1"
      },
      "tag": "api"
    }
  ],
  "outbounds": [
    {
      "protocol": "freedom",
      "settings": {}
    },
    {
      "protocol": "blackhole",
      "settings": {},
      "tag": "blocked"
    }
  ],
  "policy": {
    "system": {
      "statsInboundDownlink": true,
      "statsInboundUplink": true
    }
  },
  "routing": {
    "rules": [
      {
        "inboundTag": [
          "api"
        ],
        "outboundTag": "api",
        "type": "field"
      },
      {
        "ip": [
          "geoip:private"
        ],
        "outboundTag": "blocked",
        "type": "field"
      },
      {
        "outboundTag": "blocked",
        "protocol": [
          "bittorrent"
        ],
        "type": "field"
      },
      {
        "outboundTag": "blocked",
          "domain": [
            "regexp:.*\\.ir$",
            "ext:iran.dat:ir",
            "geosite:category-porn",
            "geosite:category-ir-gov",
            "geosite:category-ir-news",
            "geosite:category-ir-bank",
            "geosite:category-ir-tech",
            "geosite:category-ir-travel",
            "geosite:category-ir-shopping",
            "geosite:category-ir-insurance",
            "geosite:category-ir-scholar",
            "ext:iran.dat:other","snapp", "digikala","tapsi", "blogfa", "bank", "sb24.com", "sheypoor.com", "tebyan.net", "beytoote.com", "telewebion.com", "Film2movie.ws", "Setare.com", "Filimo.com", "Torob.com", "Tgju.org", "Sarzamindownload.com", "downloadha.com", "P30download.com", "Sanjesh.org"
          ],
        "type": "field"
      }
    ]
  },
  "stats": {}
}
```

## گام پنجم

تنظیمات را ذخیره کنید. تمام دسترسی‌ها به سرور‌های داخلی بایستی مسدود شده باشند.

![image](https://user-images.githubusercontent.com/118040490/216743759-c8c7be1c-6832-42cd-ad3d-b273af8c2b07.png)



# فهرست سایت‌های داخلی را از کجا گرفته‌ایم؟
تا جایی که ما متوجه شدیم، دو مجموعه به طور جداگانه در حال تهیه فهرست وب‌سایت‌های داخلی هستند. یکی به زحمت بچه‌های [iran-hosted-domain](https://github.com/chiroots/iran-hosted-domains) تهیه شده و دیگری توسط [جامعه بچه‌های V2Ray‌](https://github.com/v2fly/domain-list-community) تکمیل می‌شود. در این مستند، ما از فهرستی که این دوستان تهیه کرده‌اند، استفاده کردیم. البته همانطور که می‌بینید، یک سری از دامنه‌ها را هم به طور دستی مشخص کرده‌ایم.
