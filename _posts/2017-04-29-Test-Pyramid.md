---
layout: post
title: Base for Test Strategy 
---

### Test Pyramid
#### Apa itu test Pyramid ?

Test Pyramid adalah sebuah konsep perkembangan yang bertujuan untuk mempersingkat siklus umpan balik, untuk tim yang baru mulai automated testing harus sering mengkondisikan setiap pengujian yang luas. Setiap pengecekan harus punya banyak test case dalam kondisi waktu yang singkat.

![Pyramid](http://res.cloudinary.com/deshqivuj/image/upload/v1493404061/maven-eclipse/pyramid.png)

#### Unit Test :
  *Kenapa* Pastikan code yang dikembangkan dengan benar
  
  
#### Integration Test
Integration Test - adalah Integration Testing merupakan pengujian hasil dari penggabungan komponen atau unit-unit yang berinteraksi di dalam sebuah software. Umumnya para penguji akan mengetes bagaimana unit-unit tersebut bekerja dalam suatu kombinasi dan bukan lagi sebagai satu unit individual. 

#### BDD Acceptance Test
BDD Acceptance Test -  merupakan sumber kebingungan terbesar. Ketika diterapkan pada pengujian otomatis, BDD adalah serangkaian praktik terbaik untuk menulis tes hebat. BDD dapat, dan seharusnya, digunakan bersama dengan TDD dan metode pengujian unit.

Salah satu hal utama yang dituju BDD adalah detail implementasi dalam pengujian unit. Masalah umum dengan tes unit yang buruk adalah mereka terlalu bergantung pada bagaimana fungsi yang diuji diimplementasikan. Ini berarti jika Anda memperbarui fungsi, bahkan tanpa mengubah input dan output, Anda juga harus memperbarui tes.

**Kenapa** : Cover iterasi dan kontrak diantara didalam system dan diluar system 

**Apa** : Level selanjutnya dari test service tersebut

**Kapan** : Perkembangan Feature baru dan Siap untuk ditest 

**Brp % dari total keseluruhan** : 10-15 % dari step case

**Dimana** : Test environment dan CI

**Frequency** : Dieksekusi beberapa kali dalam sehari

**Penting** : Tes penerimaan diwajibkan untuk secara otomatis memeriksa apakah harapan pengguna akan terpenuhi atau tidak

#### TDD Acceptance Test - lebih ke developer

Test-Driven Development adalah proses ketika Anda menulis dan menjalankan tes Anda. Mengikutinya memungkinkan untuk memiliki cakupan tes yang sangat tinggi. Cakupan uji mengacu pada persentase kode Anda yang diuji secara otomatis, jadi angka yang lebih tinggi lebih baik. TDD juga mengurangi kemungkinan memiliki bug dalam pengujian Anda, yang sebaliknya bisa sulit dilacak.
Example : create unit test

* Proses TDD terdiri dari langkah-langkah berikut:

* Mulailah dengan menulis tes
* Jalankan tes dan tes lainnya. Pada titik ini, tes Anda yang baru ditambahkan harus gagal. Jika tidak gagal di sini, itu mungkin tidak menguji hal yang benar dan karenanya memiliki bug di dalamnya.
* Tulis jumlah kode minimum yang diperlukan untuk lulus ujian
* Jalankan tes untuk memeriksa lulus tes baru
* Opsional perbaiki kode Anda
* Ulangi dari 1 kali

### ATDD -> Acceptance Test Driven Development -> Lebih ke arah User PM 


