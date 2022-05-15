```
PHP superglobals $_GET and $_POST are used to collect form-data.
```
```php
// "welcome.php"

<html>
<body>

Welcome <?php echo $_POST["name"]; ?><br>
Your email address is: <?php echo $_POST["email"]; ?>

</body>
</html>
```
```php
<html>
<body>

<form action="welcome.php" method="post">
Name: <input type="text" name="name"><br>
E-mail: <input type="text" name="email"><br>
<input type="submit">
</form>

</body>
</html>
```
```
The output :
------------
Welcome John
Your email address is john.doe@example.com
```
