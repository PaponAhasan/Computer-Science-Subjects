### PHP Arrays
```
An array is a special variable, which can hold more than one value at a time.

There are three types of arrays:

Indexed arrays - Arrays with a numeric index
Associative arrays - Arrays with named keys
Multidimensional arrays - Arrays containing one or more arrays
```
```php
<?php
$cars = array("Volvo", "BMW", "Toyota");
echo count($cars); // 3
?>
```
```php
# Indexed Arrays

<?php
$cars = array("Volvo", "BMW", "Toyota");

echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";

$arrlength = count($cars);
for($x = 0; $x < $arrlength; $x++) {
  echo $cars[$x];
  echo "<br>";
}
?>

Output:
-------
I like Volvo, BMW and Toyota.

Volvo
BMW
Toyota
```
```php
# Associative Arrays

<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

or:

$age['Peter'] = "35";
$age['Ben'] = "37";
$age['Joe'] = "43";

echo "Peter is " . $age['Peter'] . " years old.";

foreach($age as $x => $x_value) {
  echo "Key=" . $x . ", Value=" . $x_value;
  echo "<br>";
}
?>

Output:
-------
Peter is 35 years old.

Key=Peter, Value=35
Key=Ben, Value=37
Key=Joe, Value=43
```
```php
# Multidimensional Arrays

<?php
$cars = array (
  array("Volvo",22,18),
  array("BMW",15,13),
  array("Saab",5,2),
  array("Land Rover",17,15)
);

echo $cars[0][0].": In stock: ".$cars[0][1].", sold: ".$cars[0][2].".<br>";

for ($row = 0; $row < 4; $row++) {
  echo "<p><b>Row number $row</b></p>";
  echo "<ul>";
  for ($col = 0; $col < 3; $col++) {
    echo "<li>".$cars[$row][$col]."</li>";
  }
  echo "</ul>";
}
?>

Volvo: In stock: 22, sold: 18.

Row number 0

Volvo
22
18
Row number 1

BMW
15
13

.
.
.
.
```
### Sorting Arrays
```
sort() - sort arrays in ascending order
rsort() - sort arrays in descending order
asort() - sort associative arrays in ascending order, according to the value
ksort() - sort associative arrays in ascending order, according to the key
arsort() - sort associative arrays in descending order, according to the value
krsort() - sort associative arrays in descending order, according to the key
```
```php
# Indexed Arrays

$numbers = array(4, 6, 2, 22, 11);
# ascending order
sort($numbers); // 2 4 6 11 22
# descending order
rsort($numbers); // 22 11 6 4 2

$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
asort($age); 
```
```php
# Associative Arrays

$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

# ascending order, the value
asort($age);

/*
Key=Peter, Value=35
Key=Ben, Value=37
Key=Joe, Value=43
*/

# ascending order the key
ksort($age);
/*
Key=Ben, Value=37
Key=Joe, Value=43
Key=Peter, Value=35
*/

# descending order the value
arsort($age);
/*
Key=Joe, Value=43
Key=Ben, Value=37
Key=Peter, Value=35
*/

# descending order the key
krsort($age);
/*
Key=Peter, Value=35
Key=Joe, Value=43
Key=Ben, Value=37
*/
```
