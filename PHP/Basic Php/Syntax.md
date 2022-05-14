```php
# A PHP script starts with <?php and ends with ?> :

<?php
// PHP code goes here
?>
```
### PHP Output
```php
<!DOCTYPE html>
<html>
<body>

<h1>My first PHP page</h1>
# built-in PHP function "echo" to output the text
<?php
echo "Hello World!";
?>

</body>
</html>
```
### PHP Single-Line Comment
```php
<!DOCTYPE html>
<html>
<body>

<?php
// This is a single-line comment

# This is also a single-line comment
?>

</body>
</html>
```
### PHP Multiple-Lines Comment
```php
<!DOCTYPE html>
<html>
<body>

<?php
/*
This is a multiple-lines comment block
that spans over multiple
lines
*/
?>

</body>
</html>
```
### PHP Variables (variables as containers for storing data.)
```
PHP has three different variable scopes:

- local
- global
- static
```
```php
# Global : A variable declared outside a function has a GLOBAL SCOPE and can only be accessed outside a function

<?php
$x = 5; // global scope

function myTest() {
  // using x inside this function will generate an error
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

echo "<p>Variable x outside function is: $x</p>";
?>
```
```php
# Local :

<?php
function myTest() {
  $x = 5; // local scope
  echo "<p>Variable x inside function is: $x</p>";
}
myTest();

// using x outside the function will generate an error
echo "<p>Variable x outside function is: $x</p>";
?>
```
```php
# The global keyword is used to access a global variable from within a function.

<?php
$x = 5;
$y = 10;

function myTest() {
  global $x, $y;
  $y = $x + $y;
}

myTest();
echo $y; // outputs 15
?>
```
```php
# The global keyword is used to access a global variable from within a function.

<?php
$x = 5;
$y = 10;

function myTest() {
  $GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];
  echo $GLOBALS['y']."<br/>";
} 

myTest();
echo $y;
?>
15
15
```
```php
# A variable starts with the $ sign

<!DOCTYPE html>
<html>
<body>

<?php
$txt = "Hello world!";
$x = 5;
$y = 10.5;

echo $txt;
echo "<br>";
echo "I love " . $txt . "!";
echo "<br>";
echo $x;
echo "<br>";
echo $y;
echo "<br>";
echo $x + $y;
?>

</body>
</html>

Output :
-------
 Hello world!
 5
 10.5
```
```php
# static Keyword

 /* When a function is completed/executed, all of its variables are deleted. 
 However, sometimes we want a local variable NOT to be deleted. We need
 static keyword. Static keyword first declare the variable. */
 
<?php
function myTest() {
  static $x = 0;
  echo $x;
  $x++;
}

myTest();
myTest();
myTest();
?>

Output :
--------
0
1
2
```
###  Echo vs Print
```
Two basic ways to get output: echo and print :

- They are both used to output data to the screen.
- echo has no return value while print has a return value of 1 
- echo can take multiple parameters while print can take one argument.
- echo is marginally faster than print
- print "<h2>PHP is Fun!</h2>";
  print "Study PHP at " . $txt2 . "<br>";
  echo "This ", "string ", "was ", "made ", "with multiple parameters.";
  echo "Study PHP at " . $txt2 . "<br>";
```
