### PHP $GLOBALS
```php
# Used to access global variables from anywhere in the PHP script.
# PHP stores all global variables in an array called $GLOBALS[index].

<?php
$x = 75;
$y = 25;
 
function addition() {
  $GLOBALS['z'] = $GLOBALS['x'] + $GLOBALS['y'];
}
 
addition();
echo $z;
?>
```
### PHP $_SERVER
```php
# $_SERVER is a PHP super global variable which holds information about headers, paths, and script locations.

<?php
echo $_SERVER['PHP_SELF'];
echo "<br>";
echo $_SERVER['SERVER_NAME'];
echo "<br>";
echo $_SERVER['HTTP_HOST'];
echo "<br>";
echo $_SERVER['HTTP_REFERER'];
echo "<br>";
echo $_SERVER['HTTP_USER_AGENT'];
echo "<br>";
echo $_SERVER['SCRIPT_NAME'];
?>
```
### PHP $_REQUEST
```php
# which is used to collect data after submitting an HTML form.

/*A form with an input field and a submit button. When a user submits the data by clicking on "Submit", the 
form data is sent to the file specified in the action attribute of the <form> tag. Then, we can use the super 
global variable $_REQUEST to collect the value of the input field:*/

<!DOCTYPE html>
<html>
<body>

<form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>">
  Name: <input type="text" name="fname">
  <input type="submit">
</form>

<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
  // collect value of input field
  $name = $_REQUEST['fname'];
  if (empty($name)) {
    echo "Name is empty";
  } else {
    echo $name;
  }
}
?>

</body>
</html>
```
![image](https://user-images.githubusercontent.com/59710234/168489005-3ce3441b-23b9-4455-b127-045186e0d5ec.png)
### PHP $_POST
```
used to collect form data after submitting an HTML form with method="post".
```
```php
<html>
<body>

<form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>">
  Name: <input type="text" name="fname">
  <input type="submit">
</form>

<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
  // collect value of input field
  $name = $_POST['fname'];
  if (empty($name)) {
    echo "Name is empty";
  } else {
    echo $name;
  }
}
?>

</body>
</html>
```
![image](https://user-images.githubusercontent.com/59710234/168489005-3ce3441b-23b9-4455-b127-045186e0d5ec.png)
### PHP $_GET
```php
#  used to collect form data after submitting an HTML form with method="get".
# $_GET can also collect data sent in the URL.

```
