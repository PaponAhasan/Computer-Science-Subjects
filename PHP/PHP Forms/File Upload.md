### HTML Form
```html
<!DOCTYPE html>
<html>
<body>

<form action="upload.php" method="post" enctype="multipart/form-data">
  Select image to upload:
  <input type="file" name="fileToUpload" id="fileToUpload">
  <input type="submit" value="Upload Image" name="submit">
</form>

</body>
</html>
```
```
Requirements for file upload :
- Make sure that the form uses method="post"
- The form also needs the following attribute: enctype="multipart/form-data".
- The type="file" attribute of the <input> tag
```
### PHP Script
```php
<?php
$target_dir = "uploads/";
$target_file = $target_dir . basename($_FILES["fileToUpload"]["name"]);
$uploadOk = 1;
$imageFileType = strtolower(pathinfo($target_file,PATHINFO_EXTENSION));
// Check if image file is a actual image or fake image
if(isset($_POST["submit"])) {
  $check = getimagesize($_FILES["fileToUpload"]["tmp_name"]);
  if($check !== false) {
    echo "File is an image - " . $check["mime"] . ".";
    $uploadOk = 1;
  } else {
    echo "File is not an image.";
    $uploadOk = 0;
  }
}
?>
```
```
$target_dir = "uploads/" ==>  Create a new directory called "uploads" in the directory where "upload.php" file resides. 
       The uploaded files will be saved there.
       
basename() ==>  The function returns the filename from a path
       
       $path = "/testweb/home.php";
       # Show filename
       echo basename($path) ."<br/>"; # home.php
       
$_FILES["fileToUpload"]["name"] ==>  $_FILES is an associative array. The original name of the file to be uploaded.

pathinfo() ==> function returns information about a file path.
```
- [basename()](https://www.w3schools.com/php/func_filesystem_basename.asp)
- [$_FILES](https://www.tutorialspoint.com/php-files#:~:text=The%20global%20predefined%20variable%20%24_,to%20multipart%2Fform%2Ddata.&text=%24_FILES%5B'file'%5D,the%20file%20to%20be%20uploaded.)
- [pathinfo()](https://www.w3schools.com/php/func_filesystem_pathinfo.asp)
### PHP Validation
```php
<?php
// Check if file already exists
if (file_exists($target_file)) {
  echo "Sorry, file already exists.";
  $uploadOk = 0;
}

// Check file size
if ($_FILES["fileToUpload"]["size"] > 500000) {
  echo "Sorry, your file is too large.";
  $uploadOk = 0;
}

// Allow certain file formats
if($imageFileType != "jpg" && $imageFileType != "png" && $imageFileType != "jpeg"
&& $imageFileType != "gif" ) {
  echo "Sorry, only JPG, JPEG, PNG & GIF files are allowed.";
  $uploadOk = 0;
}

// Check if $uploadOk is set to 0 by an error
if ($uploadOk == 0) {
  echo "Sorry, your file was not uploaded.";
// if everything is ok, try to upload file
} else {
  if (move_uploaded_file($_FILES["fileToUpload"]["tmp_name"], $target_file)) {
    echo "The file ". htmlspecialchars( basename( $_FILES["fileToUpload"]["name"])). " has been uploaded.";
  } else {
    echo "Sorry, there was an error uploading your file.";
  }
}
?>
```
```
move_uploaded_file(string $from, string $to): bool ==>
This function checks to ensure that the file designated by from is a valid upload file.
If the file is valid, it will be moved to the filename given by to

from
The filename of the uploaded file.

to
The destination of the moved file.
```
[PHP Script](https://ideone.com/cCwJZZ)
