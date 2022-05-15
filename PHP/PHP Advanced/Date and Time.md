### Get a Date
```
d - Represents the day of the month (01 to 31)
m - Represents a month (01 to 12)
Y - Represents a year (in four digits)
l (lowercase 'L') - Represents the day of the week
```
```php
<?php
echo "Today is " . date("Y/m/d/l") . "<br>";
?>

Today is 2022/05/15/Sunday
```
### Get a Time
```
H - 24-hour format of an hour (00 to 23)
h - 12-hour format of an hour with leading zeros (01 to 12)
i - Minutes with leading zeros (00 to 59)
s - Seconds with leading zeros (00 to 59)
a - Lowercase Ante meridiem and Post meridiem (am or pm)
```
```php
<?php
echo "The time is " . date("h:i:sa");
?>

The time is 12:56:11pm
```
### Get Your Time Zone
```
If the time you got back from the code is not correct, another country or set up for a different timezone.
```
```php
#  if you need the time to be correct according to a specific location

<?php
date_default_timezone_set("America/New_York");
echo "The time is " . date("h:i:sa");

date_default_timezone_set("Asia/Dhaka");
echo "The time is " . date("h:i:sa");
?>

The time is 08:58:31am
```
