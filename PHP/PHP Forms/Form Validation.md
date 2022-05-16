```
Proper validation of form data is important to protect your form from hackers and spammers!
```
```php
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">
```
```
- method="post" => When the form is submitted, the form data is sent with method="post".
- $_SERVER["PHP_SELF"] => The $_SERVER["PHP_SELF"] is a super global variable that returns the filename of the currently
  executing script.
- htmlspecialchars() =>  htmlspecialchars() function converts special characters to HTML entities. 
```
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
