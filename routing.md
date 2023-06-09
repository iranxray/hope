# مسدودسازی سایت‌ها و اپلیکیشن‌های ایرانی

سیستم فیلترینگ از روش‌های متنوعی استفاده می‌کند تا بتواند «حدس بزند» یک IP متعلق به پروکسی سرور می‌باشد یا نه. در چین، یکی از روش‌هایی که GFW استفاده می‌کند این است که اگر از یک سرور خارجی درخواستی به سمت سایت‌های داخلی چینی بیاید، آن را مسدود می‌کند. حدس می‌زنیم که در ایران هم از سیستم مشابهی استفاده می‌شود. 


وقتی که گوشی کاربر به پروکسی ‌سرور متصل نباشد، تمامی درخواست‌ها به وب‌سایت‌ها و اپلیکیشن‌های ایرانی در درون شبکه اینترنت ایران صورت خواهد گرفت. شبیه شکل زیر:

![image](https://user-images.githubusercontent.com/118040490/216741378-5d1168cb-e79c-4ab7-ac33-29cf25f7d359.png)


اما فرض کنید گوشی کاربر به پروکسی سرور شما - که در خارج از کشور قرار گرفته - متصل باشد. در این صورت، تمامی درخواست‌های کاربر برای باز کردن وب‌سایت‌ها و اپلیکیشن‌های داخلی از سمت سرور شما صورت خواهد گرفت. شبیه شکل زیر. همانطور که در تصویر می‌بینید، در این حالت از یک IP‌ خارج از کشور درخواست به سمت وب‌سایت‌های داخلی ارسال خواهد شد. همین اتفاق برای فیلترچی دلیل کافی خواهد بود تا به IP سرور شما مشکوک بشود.

![image](https://user-images.githubusercontent.com/118040490/216741596-fae3d86b-e12d-433e-92e5-c9cd6fae75fc.png)

بهترین راه حل برای رفع این مشکل این است که کاربران مراقب باشند که در هنگام اتصال به پروکسی از شبکه‌ داخلی ایران استفاده نکنند. برخی از اپلکیشن‌ها مثل V2RayNG به شما این امکان را می‌دهند که مشخص کنید ترافیک چه اپلیکیشن‌هایی می‌تواند از پروکسی عبور کند. اما یک راه حل دیگر استفاده از مکانیزمی است که در سامانه XRay به نام Routing شناخته می‌شود. در ادامه آموزش می‌دهیم که چگونه در سمت کاربر و سمت سرور بتوانیم ترافیک داخلی ایران را مسدود کنیم.

# مکانیزم Routing
این مکانیزم که در Xray‌ تعبیه شده به شما اجازه می‌دهد که مشخص کنید چه ترافیکی می‌تواند از پروکسی سرور شما عبور کند. مثلا می‌توانید مشخص کنید تمام دامنه‌های ir مسدود شوند یا می‌توانید بگویید که یک دامنه خاص مثه digikala.com‌ نباید از سرور شما قابل دسترس باشد. در نتیجه اعمال این تغییرات، کاربران پروکسی سرور شما نمی‌توانند از وب‌سایت‌های داخلی استفاده کنند. مکانیزم routing در [مستندات رسمی XRay](https://xtls.github.io/config/routing.html#routingobject) توضیح داده شده است.

### مزایای استفاده از Routing
* کاهش احتمال شناسایی سرور
* کاهش ترافیک سرور و در نتیجه بالا رفتن کیفیت
* کاهش هزینه‌های سرور (اگر بابت ترافیک هزینه جداگانه پرداخت می‌کنید.)

## ترافیک داخلی بدون استفاده از VPN
این قسمت را از کاربرا‌ن‌تان بخواهید که انجام دهند. چرا که ایده‌ال ترین حالت این است که اساسا ترافیک داخلی ایران به سمت پروکسی سرور شما ارسال نشود. مثلا اپلیکیشن V2Ray‌ برای ما این امکان را فراهم می‌کند که به سادگی مشخص کنیم ترافیک داخلی از پروکسی عبور نکند و فقط ترافیک خارجی به سمت پروکسی سرور ارسال شود.

## گام اول
به قسمت Settings می‌رویم.


<img src="https://user-images.githubusercontent.com/118040490/216750059-e08c84eb-f724-4f12-8d0e-511412492aae.png" 
alt="IMAGE ALT TEXT HERE" width="250" height="420" border="10" />


## گام دوم
به قسمت Custom Rules می‌رویم.

<img src="https://user-images.githubusercontent.com/118040490/216750258-a97b130c-f2d2-4d67-85d7-b00fb4f4f14b.png" 
alt="IMAGE ALT TEXT HERE" width="250" height="420" border="10" />


## گام سوم
به قسمت Direct Url or IP می‌رویم و مقدار `geoip:ir` را وارد می‌کنیم. این کار باعث خواهد شد که ترافیک داخلی ایران از پروکسی سرور عبور نکند. عبارت `geoip:ir` مخفف مجموعه‌ای است که تمامی IP‌های ایران را تا حد خوبی پوشش می‌دهد.

<img src="https://user-images.githubusercontent.com/118040490/216750327-45e75c33-c348-423e-93c1-e08602051795.png" 
alt="IMAGE ALT TEXT HERE" width="250" height="420" border="10" />




## مسدودسازی از سمت سرور
این قسمت مسئولیت شما است. ما می‌توانیم مسدودسازی رو در سمت سرور هم انجام بدهیم. ما توصیه می‌کنیم این کار حتما صورت بگیرد چون مواقعی هست که به دلایل مختلف مسدودسازی از سمت کاربر مقدور نیست و شما هم نمی‌توانید به کاربران‌تون اطمینان داشته باشید که حتما مسدودسازی رو انجام داده‌اند. 


## گام اول
برای اعمال Routing ما فرض می‌کنیم که شما X-UI را بر روی سرور خود [نصب کرده‌اید](https://github.com/iranxray/hope/blob/main/install-xui.md) و از آخرین نسخه Xray استفاده می‌کنید. برای به روز رسانی نسخه Xrayِ، کافی است در داشبورد X-UI بر روی version کلیک کنید و در پنجره‌ای که باز‌ می‌شود آخرین نسخه را انتخاب کنید.

![image](https://user-images.githubusercontent.com/118040490/216749334-8dc7d6d7-4743-40ff-b8d4-956f338d2841.png)

## گام دوم
حالا نوبت به این می‌رسد که مشخصا به Xray بگوییم که وب‌سایت‌های ایرانی را مسدود کند. برای این کار داخل پنل X-UI‌ شوید و به قسمت تنظیمات بروید.

![image](https://user-images.githubusercontent.com/118040490/216742902-538975b9-30f2-449b-80fe-d5bf890a2ae3.png)

## گام سوم
در این گام، متن زیر را کامل کپی کرده و جایگزین مقدار قبلی در تنظیمات X-UI بکنید. کانفیگ زیر با استفاده از فهرست `geoip:ir` تا حد بسیار خوبی IP‌های ایران را بر روی سرور مسدود می‌کند.

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
    "levels": {
      "0": {
        "statsUserUplink": true,
        "statsUserDownlink": true
      }
    },
    "system": {
      "statsInboundDownlink": true,
      "statsInboundUplink": true
    }
  },
  "routing": {
    "domainStrategy": "IPIfNonMatch",
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
          "geoip:private",
          "geoip:ir"
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
      }
    ]
  },
  "stats": {}
}
```
## گام چهارم

تنظیمات را ذخیره کنید. تمام!

![image](https://user-images.githubusercontent.com/118040490/216743759-c8c7be1c-6832-42cd-ad3d-b273af8c2b07.png)



## گام پنجم (اختیاری)
دستور قیلی توسط ‍`geop:ir` آدرس IP‌های ایران را بر روی سرور مسدود کرد. برای محکم‌کاری شاید بخواهید در کنار IPها، دامنه‌های ایرانی را هم مسدود کنید. برای اینکار، در ابتدا لازم داریم تا فهرست تمام وب‌سایت‌ها و اپلیکیشن‌های فارسی را بر روی سرور دانلود کرده و در فولدر Xray‌ قرار دهیم. (وقتی که X-UI‌ را نصب می کنید، سیستم XRay در آدرس ‍‍`usr/local/x-ui/bin` نصب خواهد شد.)

حالا به سرور SSH‌ بزنید و دستورات زیر را سطر به سطر جداگانه اجرا کنید تا فهرست دامنه‌های داخلی را بر روی سرور دانلود کنیم.

```bash
sudo -i
cd /usr/local/x-ui/bin
wget https://github.com/bootmortis/iran-hosted-domains/releases/latest/download/iran.dat
wget https://github.com/v2fly/domain-list-community/releases/latest/download/dlc.dat
```

حالا که فهرست دامنه‌ها بارگذاری شده، باید کانفیگ زیر را در X-UI قرار دهیم تا هم IP و هم دامنه‌های ایرانی بر روی سرور مسدود شوند.


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
    "levels": {
      "0": {
        "statsUserUplink": true,
        "statsUserDownlink": true
      }
    },
    "system": {
      "statsInboundDownlink": true,
      "statsInboundUplink": true
    }
  },
  "routing": {
    "domainStrategy": "IPIfNonMatch",
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
          "geoip:private",
          "geoip:ir"
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
            "ext:iran.dat:other",
            "geosite:category-ir-gov",
            "geosite:category-ir-news",
            "geosite:category-ir-bank",
            "geosite:category-ir-tech",
            "geosite:category-ir-travel",
            "geosite:category-ir-shopping",
            "geosite:category-ir-insurance",
            "geosite:category-ir-scholar",
            "snapp", "digikala","tapsi", "blogfa", "bank", "sb24.com", "sheypoor.com", "tebyan.net", "beytoote.com", "telewebion.com", "Film2movie.ws", "Setare.com", "Filimo.com", "Torob.com", "Tgju.org", "Sarzamindownload.com", "downloadha.com", "P30download.com", "Sanjesh.org"
          ],
        "type": "field"
      }
    ]
  },
  "stats": {}
}
```



# فهرست سایت‌های داخلی را از کجا گرفته‌ایم؟
تا جایی که ما متوجه شدیم، دو مجموعه به طور جداگانه در حال تهیه فهرست وب‌سایت‌های داخلی هستند. یکی به زحمت بچه‌های [iran-hosted-domain](https://github.com/bootmortis/iran-hosted-domains) تهیه شده و دیگری توسط [جامعه بچه‌های V2Ray‌](https://github.com/v2fly/domain-list-community) تکمیل می‌شود. در این مستند، ما از فهرستی که این دوستان تهیه کرده‌اند، استفاده کردیم. البته همانطور که می‌بینید، یک سری از دامنه‌ها را هم به طور دستی مشخص کرده‌ایم.



# فهرست IP‌های ایران را از کجا گرفته‌ایم؟
اگر به تنظیمات دقت کرده باشید، ما در کنار مشخص کردن فهرستی از دامنه‌ها، با استفاده از `geoip:ir` تمامی IP های ایران هم بر روی سرور مسدود کرده‌ایم. این فهرست از IP ها توسط [پروژه V2Ray GeoIP](https://github.com/v2ray/geoip) تهیه شده که از [لیست معروف MaxMind](https://www.maxmind.com/en/home) استفاده می‌کند. فهرست Max Mind تا حد ممکن IP تمام کشور‌های دنیا از جمله ایران را پوشش می‌دهد.
