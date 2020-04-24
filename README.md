Hijri Date Time
==================
Hijri Date Time extension is a convenient and complete solution for users who want to use Hijri date in their projects and convert Gregorian calendar to Hijri (Islamic) calendar.

It support Arabic, English, France, and Indonesia languages.

This extension is made by Abdulrhman Alkhodiry & Abdul-Aziz Al-Oraij. I just add some addition for compatible with Yii2 and wrap it to composer.

The original source [here](https://www.yiiframework.com/extension/hijridatetime)


Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Just run

```
composer require biladina/yii2-hijridatetime
```

Usage
-----

Once the extension is installed, simply use it in your code by  :

```php
<?php

use biladina\hijridatetime\HijriDateTime;

// Choose Your Format Like 'l ، j F ، Y'
// Y => Hijri Year [1442]
// F => Hijri Month Arabic Name [رمضان]
// j => Hijri Day Number [27]
// l => Arabic Day Name [الجمعة]
// m => Hijri Month Number [09]
// a => 'ص'
// A => 'صباحًا'
// H => Hour
// i => Minutes
// s => Seconds

$hijri = new HijriDateTime();

$hijri->date("H:i A l, d F Y",time()) // formatting is like date function
// will return 16:16 PM Jum'at, 01 Ramadhan 1441

$hijri->GeToHijr(20, 02,  1976)
// will return Array Hijri date[int month, int day, int year]

$hijri->strToHijri("24 April 2020")
// will return a Date in Hijri d-m-Y if not formated
//-------- Or -----------
$hijri->strToHijri("24 April 2020 15:00:00", "l, d F Y H:i A")
// will return a Date in Hijri as formated like Jum'at, 01 Ramadhan 1441 15:00 PM

```

If you want to change language, open your config main.php file, change the languange id.

```php
return [
	'language' => 'id-ID', // 'en-US' for English, 'ar' for Arabic, 'fr' for France, 'id-ID' for Indonesia
]
```