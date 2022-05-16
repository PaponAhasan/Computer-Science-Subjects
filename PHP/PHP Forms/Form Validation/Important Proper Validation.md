```
Proper validation of form data is important to protect your form from hackers and spammers!
```
```php
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">

- method="post" => When the form is submitted, the form data is sent with method="post".

- $_SERVER["PHP_SELF"] => The $_SERVER["PHP_SELF"] is a super global variable that returns the filename of the currently
  executing script.
  
- htmlspecialchars() =>  htmlspecialchars() function converts special characters to HTML entities. 
```
### PHP Form Validation Example
```php
<!DOCTYPE HTML>  
<html>
<head>
</head>
<body>  

<?php
// define variables and set to empty values
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>

<h2>PHP Form Validation Example</h2>
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">

  Name: <input type="text" name="name">
  <br><br>
  E-mail: <input type="text" name="email">
  <br><br>
  Website: <input type="text" name="website">
  <br><br>
  Comment: <textarea name="comment" rows="5" cols="40"></textarea>
  <br><br>
  Gender:
  <input type="radio" name="gender" value="female">Female
  <input type="radio" name="gender" value="male">Male
  <input type="radio" name="gender" value="other">Other
  <br><br>
  <input type="submit" name="submit" value="Submit">  
  
</form>

<?php
echo "<h2>Your Input:</h2>";
echo $name;
echo "<br>";
echo $email;
echo "<br>";
echo $website;
echo "<br>";
echo $comment;
echo "<br>";
echo $gender;
?>

</body>
</html>
```
![image](https://user-images.githubusercontent.com/59710234/168637742-ce2ad3dd-e1b3-4643-b1b8-d6c102698bfe.png)
### PHP Form Security
```php
The $_SERVER["PHP_SELF"] variable can be used by hackers!
If PHP_SELF is used in your page then a user can enter a slash (/) and then some Cross Site Scripting (XSS) commands to execute.
Assume we have the following form in a page named "test_form.php":
```
```php
<form method="post" action="<?php echo $_SERVER["PHP_SELF"];?>">

# Now, if a user enters the normal URL in the address bar like "http://www.example.com/test_form.php", the above code will be 
# translated to:

<form method="post" action="test_form.php">
```
```php
# a user enters the following URL in the address bar:

http://www.example.com/test_form.php/%22%3E%3Cscript%3Ealert('hacked')%3C/script%3E

# In this case, the above code will be translated to:

<form method="post" action="test_form.php/"><script>alert('hacked')</script>

# Any JavaScript code can be added inside the <script> tag! A hacker can redirect the user to a file on another server.
```
### Avoid $_SERVER["PHP_SELF"] Exploits
```php
# Using the htmlspecialchars() function avoided $_SERVER["PHP_SELF"] exploits.

<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">

# The htmlspecialchars() function converts special characters to HTML entities.

<form method="post" action="test_form.php/&quot;&gt;&lt;script&gt;alert('hacked')&lt;/script&gt;">
```
