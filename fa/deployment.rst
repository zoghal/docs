استفاده از برنامه
##########

در صورتی که برنامه تون تکمیل شده باشه و یا حتی قبل از اون، ممکنه که یخواهید ازش استفاده کنید.
که چند نکته ای وجود داره، که قبل از استفاده از برنامه CakePHP باید انجام بدید.

تعیین document root
=================

تنظیم صحیح document root در برنامتون یکی از مهمترین گام ها برای امن نگه داشتن کدها و برنامتون هست. برنامه های CakePHP، باید document root شون در برنامه، به مسیر ``app/webroot`` تعیین شده باشه. این باعث می شه که از طریق URL نشه به فایل های تنظیمان و برنامه دسترسی داشت.
نحوه تعیین document root در هر وب سروری تفاوت می کنه. که برای اطلاعات خاص مربوط به وب سرور بخش :doc:`/installation/advanced-installation` در مستندات رو ببینید.

آپدیت فایل core.php
===============

آپدیت کردن فایل core.php، بخصوص مقدار ``debug`` به شدت مهمه.
تغییر مقدار debug به صفر (debug = 0) یک سری از امکانات در حین توسعه (development) رو غیرفعال می کنه که بطور کلی هم هیچ وقت نبایستی بدون غیرفعال کردنشون برناممه رو در اینترنت بصورت عمومی ارائه کرد. غیرفعال کردن خطاگیری (debug) یک سری از موارد زیر رو تغییر می ده:

* پیام های مربوط به خطاگیری (Debug) که توسط متدهای :php:func:`pr()` و :php:func:`debug()` ایجاد می شن، غیرفعال می شن.
* کش هسته CakePHP هر 99 سال پاکسازی می شه، بجای هر 10 ثانیه که در حین توسعه (development) اتفاق می افته.
* Error views are less informative, and give generic error messages instead.
* خطا ها نمایش داده نمی شن.
* Exception stack traces are disabled.

در کنار مورد فوق، بسیاری از پلاگین ها و (application extensions ها) از ``debug`` برای تغییر رفتارشون استفاده می کنن.


برنامه های چندگانه CakePHP که از هسته مشترک استفاده می کنن
=================================================

چند راه وجود داره که می شه برنامه های چندگانه که بطور مشترک از یک هسته CakePHP استفاده می کنن رو تنظیم کرد. که یا می تونید از دستور ``include_path`` در خود PHP استفاده کرد و یا با اعمال کردن ``CAKE_CORE_INCLUDE_PATH`` در فایل ``webroot/index.php`` در برنامه تون.
بطور کلی استفاده از دستور ``include_path`` خود PHP ، خیلی آسون و سر راسته. که خود CakePHP هم طوری از پیش تنظیم شده که ``include_path`` رو چک می کنه و اینکه استفاده ازش هم آسونه.

در فایل ``php.ini`` دستور ``include_path`` رو پیدا کرده و سپس یا به دستور مربوطه اضافه کنید و یا یک دستور ``include_path`` خودتون اضافه کنید::

    include_path = '.:/usr/share/php:/usr/share/cakephp-2.0/lib'

که در این دستور فرض شده شما از یک سرور \*nix (یونیکس / لینوکس) استفاده می کنید و CakePHP هم در آدرس ``/usr/share/cakephp-2.0`` قرار داره.


.. meta::
    :title lang=fa: استفاده از برنامه
    :keywords lang=en: stack traces,application extensions,set document,installation documentation,development features,generic error,document root,func,debug,caches,error messages,configuration files,webroot,deployment,cakephp,applications
