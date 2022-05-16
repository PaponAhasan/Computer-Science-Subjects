```
Proper validation of form data is important to protect your form from hackers and spammers!
```
```php
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
```
```
- method="post" => When the form is submitted, the form data is sent with method="post".
- $_SERVER["PHP_SELF"] => The $_SERVER["PHP_SELF"] is a super global variable that returns the filename of the currently executing script.
- htmlspecialchars() =>  htmlspecialchars() function converts special characters to HTML entities. 
```
