### include
```
It is possible to insert the content of one PHP file into another PHP file (before the server executes it), with the include or 
require statement.
```
```php
# menu.php

<?php
echo '<a href="/default.asp">Home</a> -
<a href="/html/default.asp">HTML Tutorial</a> -
<a href="/css/default.asp">CSS Tutorial</a> -
<a href="/js/default.asp">JavaScript Tutorial</a> -
<a href="default.asp">PHP Tutorial</a>';
?>
```
```php
<!DOCTYPE html>
<html>
<body>

<div class="menu">
<?php include 'menu.php';?>
</div>

<h1>Welcome to my home page!</h1>
<p>Some text.</p>
<p>Some more text.</p>

</body>
</html>
```
```
Home - HTML Tutorial - CSS Tutorial - JavaScript Tutorial - PHP 7 Tutorial
Welcome to my home page!
Some text.

Some more text.
```
### File Handling
```
- r	Open a file for read only.
- w	Open a file for write only.
- a	Open a file for write only
- x	Creates a new file for write only.
- r+	Open a file for read/write.
- w+	Open a file for read/write.
- a+	Open a file for read/write.
- x+	Creates a new file for read/write.

w - Erases the contents of the file or creates a new file if it doesn't exist. File pointer starts at the beginning of the file
a	- The existing data in file is preserved. Creates a new file if the file doesn't exist. File pointer starts at the end of 
    the file.
```
```
# webdictionary.txt

AJAX = Asynchronous JavaScript and XML
CSS = Cascading Style Sheets
HTML = Hyper Text Markup Language
PHP = PHP Hypertext Preprocessor
SQL = Structured Query Language
SVG = Scalable Vector Graphics
XML = EXtensible Markup Languag
```
```php
<?php
echo readfile("webdictionary.txt");
?>
```
```
AJAX = Asynchronous JavaScript and XML CSS = Cascading Style Sheets HTML = Hyper Text Markup Language PHP = PHP Hypertext 
Preprocessor SQL = Structured Query Language SVG = Scalable Vector Graphics XML = EXtensible Markup Language236
```
