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
   
      **cucumber.selenium.features** , **cucumber.selenium.selenium** , **cucumber.selenium.StepDef**
      
      ![](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_383/v1494741766/maven-eclipse/2017-05-14_13-01-15.png)
      
6. Kemudian buat Junit configurasi class untuk memanggil file feature dan file StepDef
   * Tambahkan file class **RunCukes.java** didalam package **cucumber.selenium.StepDef**
   * Klik New --> Class --> Name: *RunCukes*
   * Tambahkan source seperti dibawah ini:
 
```java
package cucumber.selenium.StepDef;
import org.junit.runner.RunWith;
import cucumber.api.CucumberOptions;
import cucumber.api.junit.Cucumber;
@RunWith(Cucumber.class)
@CucumberOptions(
		features="src/test/java/cucumber/selenium/features",
		glue ="cucumber.selenium.StepDef",
		plugin= {
			"pretty",
			"html:target/cucumber"
		}
		)
public class RunCukesLogin {
}
```
7. Buat Scenario test didalam package **com.selenium.StepDef** 
   * Klik kanan dipackage **com.selenium.StepDef** 
   * Klik *New* --> *File* 
   ![new-file](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_456/v1494755421/maven-eclipse/2017-05-14_16-49-03.png)
   * Tambahkan file dengan : *LoginGithub.feature*
     ![feature](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_387/v1494757138/maven-eclipse/2017-05-14_16-52-45.png)
   * Kemudian Klik Finish
   * Kita akan mengetes page **https://www.github.com**
   * Buat Scenario seperti dibawah ini 
   
```feature
Feature: As user want to check Screen and user can login 
	
	Scenario: user can click sign in without username & pass
		Given user can see homepage github 
		When user can click link Sign in 
		Then user is displayed login screen 
		
	Scenario: user want  back to homepage 
		Given user can back to homepage
		Then user is displayed homepage screen
		
	Scenario: user want to login with use username & pass
		Given user want to login 
		When user can input username & pass
		Then user can see dashboard github

```

![scenario](http://res.cloudinary.com/deshqivuj/image/upload/c_scale,w_385/v1494759050/maven-eclipse/2017-05-14_17-41-38.png)

**Keterangan Scenario diatas :**
    1. User membuka halaman homepage github dan dapat mengklik *Sign in* tanpa username & pass
    
    2. User ingin kembali ke halaman homepage github yang *sebelumnya berada dihalaman Login github*
    
    3. User ingin Login dengan username dan password 

   
