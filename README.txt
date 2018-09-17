BUATLAH form sederhana untuk melakukan upload file berupa gambar
dan tampilkan gambar hasil upload

<!DOCTYPE html>
<html>
<center>
<head>
	<title></title>
</head>
<body>
<form action="Praktikum.html" method="post" enctype="multipart/form-data">
<input name="dokumen" type="file" id="dokumen"/>
<input type="submit" name="upload" id="upload" value="Upload" />
</form>
</body>
</center>
</html>
<?php
$file = $_FILES['dokumen'];
$nama_file = $file['name'];
$nama_tmp = $file['tmp_name'];
$upload_dir = "upload/";
move_uploaded_file($nama_tmp,$upload_dir.$nama_file);
?>
<img src="<?php echo $upload_dir .$nama_file; ?>">
