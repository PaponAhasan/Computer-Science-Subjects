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
```php
<?php
class Car {
  public $color;
  public $model;
  public function __construct($color, $model) {
    $this->color = $color;
    $this->model = $model;
  }
  public function message() {
    return "My car is a " . $this->color . " " . $this->model . "!";
  }
}

$myCar = new Car("black", "Volvo");
echo $myCar -> message();
echo "<br>";
$myCar = new Car("red", "Toyota");
echo $myCar -> message();
?>
```
### PHP String
```php
<?php
echo strlen("Hello world!"); // outputs 12

echo str_word_count("Hello world!"); // outputs 2

echo strrev("Hello world!"); // outputs !dlrow olleH

/*If a match is found, the function returns the character position of the first match. 
If no match is found, it will return FALSE.*/
echo strpos("Hello world!", "world"); // outputs 6

echo str_replace("world", "Dolly", "Hello world!"); // outputs Hello Dolly!
?>
```
### PHP Math
```php
<?php
echo(pi()); // returns 3.1415926535898

echo(min(0, 150, 30, 20, -8, -200));  // returns -200

echo(max(0, 150, 30, 20, -8, -200));  // returns 150

echo(abs(-6.7));  // returns 6.7

echo(sqrt(64));  // returns 8

# nearest integer
echo(round(0.60));  // returns 1
echo(round(0.49));  // returns 0

echo(rand()); // 1381167960

echo(rand(10, 100)); // 97
?>
```
### PHP Constants
```
Constants are like variables. Once they are defined they cannot be changed or undefined.
A valid constant name starts with a letter or underscore (no $ sign before the constant name).

To create a constant, use the define() function : define(name, value, case-insensitive)

Parameters:
----------
  name: Specifies the name of the constant
  value: Specifies the value of the constant
  case-insensitive: Specifies whether the constant name should be case-insensitive. Default is false
```
```php
<?php
// case-sensitive constant name
define("GREETING", "Welcome to W3Schools.com!");
echo GREETING;

// case-insensitive constant name
define("GREETING", "Welcome to W3Schools.com!", true);
echo greeting;

define("cars", [
  "Alfa Romeo",
  "BMW",
  "Toyota"
]);
echo cars[0];
?> 

Welcome to W3Schools.com!
Welcome to W3Schools.com!
Alfa Romeo
```
```php
# Constants are automatically global and can be used across the entire script.

<?php
define("GREETING", "Welcome to W3Schools.com!");

function myTest() {
  echo GREETING;
}
 
myTest();
?>
```
### PHP Operators
```
PHP divides the operators in the following groups:

- Arithmetic operators
- Assignment operators
- Comparison operators
- Increment/Decrement operators
- Logical operators
- String operators
- Array operators
- Conditional assignment operators
```
```php
# Arithmetic Operators

<?php
$x = 10;  
$y = 6;

echo $x + $y; // 16
echo $x - $y; // 10
echo $x * $y; // 60
echo $x / $y; // 1.667
echo $x % $y; // 4
echo $x ** $y; // 1000
?> 
```
```php
# Assignment Operators

$x = 10; // 10
$x += 100; // 110
$x -= 30; // 80
$x *= 2; // 160
$x /= 5; // 32
$x %= 2 // 2
```
```php
# Comparison Operators

$x == $y	Returns true if $x is equal to $y
$x === $y	Returns true if $x is equal to $y, and they are of the same type
$x != $y	Returns true if $x is not equal to $y
$x <> $y	Returns true if $x is not equal to $y
$x !== $y	Returns true if $x is not equal to $y, or they are not of the same type
$x > $y	  Returns true if $x is greater than $y	
$x < $y	  Returns true if $x is less than $y	
$x >= $y	Returns true if $x is greater than or equal to $y
$x <= $y	Returns true if $x is less than or equal to $y
$x <=> $y	Returns an integer less than, equal to, or greater than zero, depending on if $x is less than, equal to, 
           or greater than $y. Introduced in PHP 7.
```
```php
# Increment / Decrement Operators

$x = 10;  
# Pre-increment
echo ++$x; // 11
# Post-increment
echo $x++; // 10
# Pre-decrement
echo --$x; // 9
# Post-decrement
echo $x--; // 10
```
```php
# Logical Operators

<?php
$x = 100;  
$y = 50;
# And
if ($x == 100 and $y == 50) {
    echo "Hello world!";
}
# Or
if ($x == 100 or $y == 80) {
    echo "Hello world!";
}
# Xor
if ($x == 100 xor $y == 80) {
    echo "Hello world!";
}
# And
if ($x == 100 && $y == 50) {
    echo "Hello world!";
}
# Or
if ($x == 100 || $y == 80) {
    echo "Hello world!";
}
# Not
if ($x !== 90) {
    echo "Hello world!";
}
?>
```
```php
# String Operators

<?php
$txt1 = "Hello";
$txt2 = " world!";

# Concatenation
echo $txt1 . $txt2; // Hello world!

# Concatenation assignment
$txt1 .= $txt2;
echo $txt1; // Hello world!
?>  
```
```php
# Array Operators


```
```php
# Conditional Assignment Operators

$user = "John Doe";

# Ternary
// if empty($user) = FALSE, set $status = "logged in"
echo $status = (empty($user)) ? "anonymous" : "logged in";
```
### PHP if...else...elseif Statements
```php
<?php
$t = date("H");

if ($t < "10") {
  echo "Have a good morning!";
} elseif ($t < "20") {
  echo "Have a good day!";
} else {
  echo "Have a good night!";
}
?>
```
### PHP switch Statement
```php
<?php
$favcolor = "red";

switch ($favcolor) {
  case "red":
    echo "Your favorite color is red!";
    break;
  case "blue":
    echo "Your favorite color is blue!";
    break;
  case "green":
    echo "Your favorite color is green!";
    break;
  default:
    echo "Your favorite color is neither red, blue, nor green!";
}
?>
```
### PHP Loops
```php
- while
- do...while
- for
- foreach
```
```php
# while loop

<?php
$x = 1;

while($x <= 5) {
  echo "The number is: $x <br>";
  $x++;
}
?>
```
```php
# do...while Loop

<?php
$x = 1;

do {
  echo "The number is: $x <br>";
  $x++;
} while ($x <= 5);
?>
```
```php
# for Loop

<?php
for ($x = 0; $x <= 10; $x++) {
  echo "The number is: $x <br>";
}
?>
```
```php
# foreach Loop

<?php
$colors = array("red", "green", "blue", "yellow");

foreach ($colors as $value) {
  echo "$value <br>";
}
?>
```
```php
# foreach Loop

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $val) {
  echo "$x = $val<br>";
}
?>
```
