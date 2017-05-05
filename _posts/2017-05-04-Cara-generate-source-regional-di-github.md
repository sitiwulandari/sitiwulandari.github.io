---
layout: post
title: Cloning web common master & web test regional 
---

### Cara generate source dan menjalankan source dengan library berbeda 
* Cloning Source Web Common test dan web test

1. Copy url SSH yang akan di clone 

   ![copy ssh](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_401/v1493964196/maven-eclipse/2017-05-03_17-29-37.png)

2. Kemudian masuk ke git , kemudian jalankan : **git clone git@xxx.com/xxx-xxx.git** 

3. Pastikan file yang telah diclone sudah ada difile Anda 

      ![](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_440/v1493964195/maven-eclipse/2017-05-04_09-13-04.png)
 

4. Buka Command Prompt, kemudian masuk ke folder **regional/web-xxx-xxx** dan lakukan **mvn clean install**
    ![](http://res.cloudinary.com/deshqivuj/image/upload/v1493866687/maven-eclipse/2017-05-04_09-57-28.png)

5. Buka file **Web test** di enclips atau di intellij IDE 

    ![](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,h_200,w_400/v1493869522/maven-eclipse/2017-05-04_10-44-26.png)


