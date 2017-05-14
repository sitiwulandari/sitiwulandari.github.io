---
layout: post
title: Membuat Project Sederhana Menggunakan Maven Cucumber Selenium
---


### Latihan check testing Login github menggunakan Cucumber maven selenium

1. Pastikan Aplikasi dibawah ini sudah terinstal:

    * Java
    * Maven
    * Plugin Maven sudah terinstal dieclipse
    * Plugin Cucumber sudah terinstal dieclipse
2. Buka aplikasi eclipse terlebih dahulu kemudian ikutin step seperti dibawah ini:

      * Klik File --> **NEW**
      * Pilih --> **OTHERS**
      
        ![new](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_282/v1494740343/maven-eclipse/2017-05-14_12-02-35.png)
      
      * Kemudian pilih folder **MAVEN** dan pilih **MAVEN PROJECT**
      
        ![maven](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_357/v1494740347/maven-eclipse/2017-05-14_12-03-32.png)
       
      * Centang **create simple project** 
      * Kemudian Klik button **Next**
      
        ![d](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_383/v1494740343/maven-eclipse/2017-05-14_12-04-15.png)
      
      * Isi file seperti gambar dibawah ini:
         * GroupId : com.book.cucumber
         * Artifat Id : com.book.cucumber
         * Name : com.book.cucumber
         * Description : com.book.cucumber
         
        ![d](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_316/v1494740343/maven-eclipse/2017-05-14_12-05-53.png)
        
3. Buka file **Pom.xml** dibawah folder target

    ![pom](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_207/v1494740342/maven-eclipse/2017-05-14_12-35-16.png)
    
4. Tambahkan source di pom.xml seperti dibawah ini : 

   ```xml
   
  <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.book.cucumber</groupId>
  <artifactId>com.book.cucumber</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <name>com.book.cucumber</name>
  <description>com.book.cucumber</description>
  <dependencies>
  	<dependency>
  		<groupId>info.cukes</groupId>
  		<artifactId>cucumber-junit</artifactId>
  		<version>1.2.2</version>
  		<scope>test</scope>
  	</dependency>
  	<dependency>
  		<groupId>info.cukes</groupId>
  		<artifactId>cucumber-java</artifactId>
  		<version>1.2.2</version>
  		<scope>tets</scope>
  	</dependency>
  	<dependency>
  		<groupId>org.seleniumhq.selenium</groupId>
  		<artifactId>selenium-java</artifactId>
  		<version>2.45.0</version>
  	</dependency>
  </dependencies>
  	<build>
  	<plugins>
  		<plugin>
               <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>2.5.1</version>
                <configuration>
                    <encoding>UTF-8</encoding>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
  		<plugin>
  			<groupId>org.apache.maven.plugins</groupId>
  			<artifactId>maven-surefire-plugin</artifactId>
  			<version>2.14</version>
                <executions>
                    <execution>
                        <id>acceptance-test</id>
                        <phase>integration-test</phase>
                        <goals>
                            <goal>test</goal>
                        </goals>
                        <configuration>
                            <forkCount>${surefire.fork.count}</forkCount>
                            <reuseForks>false</reuseForks>
                            <argLine>-Duser.language=en</argLine>
                            <argLine>-Xmx1024m</argLine>
                            <argLine>-XX:MaxPermSize=256m</argLine>
                            <argLine>-Dfile.encoding=UTF-8</argLine>
                            <useFile>false</useFile>
                            <includes>
                                <include>**/RunCukesLogin.class</include>
                                <!--<include>**/*AT.class</include>-->
                            </includes>
                            <testFailureIgnore>false</testFailureIgnore>
                        </configuration>
                    </execution>
                </executions>
  		</plugin>
  	</plugins>
  </build>
</project>

   ```
5. Buatlah struktur project seperti dibawah ini :
   * Membuat Package didalam *src/tets/java*
   * Klik kanan di *src/tets/java*
   * Klik *New Package* 
   
      ![new package](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_464/v1494741762/maven-eclipse/2017-05-14_13-00-11.png)
      
   * Inputkan nama package seperti dibawah ini :
      **cucumber.selenium.features**
      
      ![](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_383/v1494741766/maven-eclipse/2017-05-14_13-01-15.png)
