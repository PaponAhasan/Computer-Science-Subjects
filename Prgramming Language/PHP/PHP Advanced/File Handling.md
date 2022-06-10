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
PHP has several functions for creating, reading, uploading, and editing files.

- r	Open a file for read only.
- w	Open a file for write only.
- a	Open a file for write only
- x	Creates a new file for write only.
- r+	Open a file for read/write.
- w+	Open a file for read/write.
- a+	Open a file for read/write.
- x+	Creates a new file for read/write.

w - Erases the contents of the file or creates a new file if it doesn't exist. File pointer starts at the beginning of the file
a - The existing data in file is preserved. Creates a new file if the file doesn't exist. File pointer starts at the end of 
    the file.
    
fopen() - used to open files
readfile() - open up a file and read its contents.
fread() - reads from an open file.
fclose() - used to close an open file.
fgets() - used to read a single line from a file.
fgetc() -  used to read a single character from a file.
feof() - checks if the "end-of-file" (EOF) has been reached.
fwrite() - used to write to a file.
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
$myfile = fopen("webdictionary.txt", "r") or die("Unable to open file!");

echo fread($myfile,filesize("webdictionary.txt"));

echo fgets($myfile);

// Output one line until end-of-file
while(!feof($myfile)) {
  echo fgets($myfile) . "<br>";
}

// Output one character until end-of-file
while(!feof($myfile)) {
  echo fgetc($myfile);
}

# Write to File
$myfile = fopen("webdictionary.txt", "w") or die("Unable to open file!");
$txt = "John Doe\n";
fwrite($myfile, $txt);

# Append Text
$myfile = fopen("webdictionary.txt", "a") or die("Unable to open file!");
$txt = "Donald Duck\n";
fwrite($myfile, $txt);

fclose($myfile);
?>
```
```
Output :
--------
AJAX = Asynchronous JavaScript and XML CSS = Cascading Style Sheets HTML = Hyper Text Markup Language PHP = PHP Hypertext 
Preprocessor SQL = Structured Query Language SVG = Scalable Vector Graphics XML = EXtensible Markup Language236

AJAX = Asynchronous JavaScript and XML

AJAX = Asynchronous JavaScript and XML
CSS = Cascading Style Sheets
HTML = Hyper Text Markup Language
PHP = PHP Hypertext Preprocessor
SQL = Structured Query Language
SVG = Scalable Vector Graphics
XML = EXtensible Markup Language

AJAX = Asynchronous JavaScript and XML CSS = Cascading Style Sheets HTML = Hyper Text Markup Language PHP = PHP Hypertext
Preprocessor SQL = Structured Query Language SVG = Scalable Vector Graphics XML = EXtensible Markup Language

John Doe

John Doe
Donald Duck
```
```php
<?php
echo readfile("webdictionary.txt");
?>
```
```
AJAX = Asynchronous JavaScript and XML CSS = Cascading Style Sheets HTML = Hyper Text Markup Language PHP = PHP Hypertext 
Preprocessor SQL = Structured Query Language SVG = Scalable Vector Graphics XML = EXtensible Markup Language
```
