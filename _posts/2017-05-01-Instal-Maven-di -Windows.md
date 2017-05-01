---
layout: post
title: Instal Maven di Windows
---

### Bagaimana Instal Maven di Windows
**1.Sediakan / unduh aplikasi yang dibutuhkan terlebih dahulu :**

* JDK 1.8

* Maven 3.5.0

**2.Download Maven 3.5.0 kemudian extract/unzip Maven tersebut di folder : *C:\program files\Apache\maven*,sebelumnya Anda buat terlebih 
dahulu buat folder maven didalam apache tersebut**

![add folder](http://res.cloudinary.com/deshqivuj/image/upload/v1493634481/maven-eclipse/2017-05-01_17-17-32.png)
![unzip file maven](http://res.cloudinary.com/deshqivuj/image/upload/v1493634491/maven-eclipse/2017-05-01_17-17-59.png)

**3. Tambahkan *M2_HOME* dan *MAVEN_HOME* di Environment Variables **

  * Windows-> properties->advanced system setting ->Environment Variables 
  
  * tambahkan Variables baru **M2_HOME** dengan Value *(C:\Program Files\Apache\maven)* di System Variables
  
  ![Maven_home](http://res.cloudinary.com/deshqivuj/image/upload/v1493635257/maven-eclipse/2017-05-01_17-35-01.png)
  
  * Kemudian tambahkan **MAVEN_HOME** dengan value *(C:\Program Files\Apache\maven)* juga di System Variables
  ![M2_HOME](http://res.cloudinary.com/deshqivuj/image/upload/v1493635254/maven-eclipse/2017-05-01_17-33-05.png)
 
**4.tambahkan Value *%M2_HOME%\bin* di Path**

![path](http://res.cloudinary.com/deshqivuj/image/upload/v1493635259/maven-eclipse/2017-05-01_17-37-21.png)

**5.Verifikasi Maven**

  * Setelah semua variable ditambahkan , kemudian jalankan **mvn-version** di command prompt / di git bush
![mvn version](http://res.cloudinary.com/deshqivuj/image/upload/v1493636465/maven-eclipse/2017-05-01_17-59-03.png)
