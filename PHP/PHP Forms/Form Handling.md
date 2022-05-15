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

### GET VS POST
```
- GET method is visible to everyone 
- GET also has limits on the amount of information to send.

- POST method is invisible to others
- POST has no limits on the amount of information to send.
```
