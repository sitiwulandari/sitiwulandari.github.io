### As User creating a end-to-end (e2e) tests for creating a gist

*User Stories*
As a user, I want to create a public gist. 

As a user, I want to edit an existing gist. 

As a user, I want to delete an existing gist. 

As a user, I want to see my list of gists. 

*Created Using:*
* Java
* Cucumber
* Maven

```Feature
Feature : As User creating a end-to-end (e2e) tests for creating a gist
Scenario: As a user, I want to create a public gist
	Given user access gist
	When user add new public gist
	Then displayed gist added

Scenario: As a user, I want to edit an existing gist
	Given user access gist
	When user  edit an existing gist
	Then displayed gist updated
	
Scenario: As a user, I want to delete an existing gist
	Given user access gist
	When user delete an existing gist
	Then displayed list all gist 	
	
Scenario: As a user, I want to see my list of gists. 
	Given user access gist
	When user click see all of your gists
	Then displayed list all gist
  ```
  
  ```java
  package cucumber.selenium.selenium;

    import java.net.MalformedURLException;
    import java.util.concurrent.TimeUnit;

    import org.openqa.selenium.chrome.ChromeDriver;
    import org.openqa.selenium.By;
    import org.openqa.selenium.WebDriver;
    import org.openqa.selenium.support.ui.ExpectedConditions;
    import org.openqa.selenium.support.ui.WebDriverWait;

public class seleniumFunction {

        public static WebDriver driver=null;
        public static WebDriverWait waitVar=null;

        public static String baseURL="https://gist.github.com/sitiwulandari";

        public void createDriver() throws MalformedURLException,InterruptedException{
            System.setProperty("webDriver.chrome.driver","/home/sitiwulandari/chromedriver");
            driver =  new ChromeDriver();

            driver.manage().window().maximize();
            driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS);

            driver.get(baseURL);

            waitVar = new WebDriverWait(driver,15);
        }
		 public void tearDown(){
            driver.quit();
        }
		
		public void inGistWulan (){
		driver.findElement(By.name("sitiwulandari")).isDisplayed();
		}
		
		public void clickAdd (){
		driver.findElement(By.cssSelector("svg.octicon.octicon-plus > path")).click();
		driver.findElement(By.name("All gists")).isDisplayed();
		}
		
		public void addPublic (){
		driver.findElement(By.name("gist[contents][][name]")).clear();
		driver.findElement(By.name("gist[contents][][name]")).sendKeys("Gist2");
		driver.findElement(By.name("gist[contents][][value]")).sendKeys("test description")
		driver.findElement(By.name("gist[public]")).click();
		}
		
		public void clickDetailGist(){
		driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='sitiwulandari'])[3]/following::strong[1]")).click();
		}
		
		public void EditExisting (){
		driver.findElement(By.linkText("Edit")).click();
		driver.findElement(By.name("gist[description]")).click();
		driver.findElement(By.name("gist[description]")).clear();
		driver.findElement(By.name("gist[description]")).sendKeys("gist description edit asa");
		driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='gist description name'])[1]/following::textarea[1]")).sendKeys("gist description yesssasa");
		driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Add file'])[1]/following::button[1]")).click();
		}
		
		public void GistDelete () {
		driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='sitiwulandari'])[3]/following::strong[1]")).click();
		acceptNextAlert = true;
		driver.findElement(By.xpath("(//button[@type='submit'])[2]")).click();
		assertTrue(closeAlertAndGetItsText().matches("^Are you positive you want to delete this Gist[\\s\\S]$"));
		}
		
		public void MyListGist (){
		driver.get("https://gist.github.com/");
		driver.findElement(By.xpath("(.//*[normalize-space(text()) and normalize-space(.)='Back to GitHub'])[1]/following::img[1]")).click();
		driver.findElement(By.linkText("Your gists")).click();
		}
		
		public void displayed_add_updated(){
		driver.findElement(By.name("Edit").displayed();
		}

  ```
  ```java
  package cucumber.selenium.StepDef;

         import java.net.MalformedURLException;

         import cucumber.selenium.selenium.seleniumFunction;
         import cucumber.api.PendingException;
         import cucumber.api.java.en.Given;
         import cucumber.api.java.en.Then;
         import cucumber.api.java.en.When;

         public class StepDefinition {
			seleniumFunction sf = new seleniumFunction();
			@Given ("^user access gist$")
			public void user_access_gists () throws MalformedURLException,InterruptedException{
			
			sf.createDriver();
			sf.inGistWulan();
			}
			
			@When("^user add new public gist$")
			public void user_add_new_ public_ gist (){
			sf.clickAdd();
			sf.addPublic();
			}
			
			@Then("^displayed gist added$")
			public void displayed_gist_added() {
			sf.displayed_add_updated();
			}
			
			@Given ("^user access gist$")
			public void user_access_gists () throws MalformedURLException,InterruptedException{
			
			sf.createDriver();
			sf.inGistWulan();
			}
			
			@When ("^user edit an existing gist$")
			public void user_edit_an_existing_gist(){
			sf.clickDetailGist
			sf.EditExisting 
			}
			
			@Then ("^displayed gist updated$")
			public void displayed_gist_updated(){
			sf.displayed_add_updated
			}
			
			@Given("^user access gist$")
			public void user_access_gists () throws MalformedURLException,InterruptedException{
			
			sf.createDriver();
			sf.inGistWulan();
			}
			
			@When ("^user delete an existing gist$")
			public void user_delete_an_existing_gist(){
			sf.GistDelete();
			}
			
			@Then ("^displayed list all gist$")
			public void displayed_list_all_gist(){
			sf.inGistWulan();
			}
			
			@Given("^user access gist$")
			public void user_access_gists () throws MalformedURLException,InterruptedException{
			
			sf.createDriver();
			sf.inGistWulan();
			}
			
			@When("^user click see all of your gists$")
			public void user_click_see_all_of_your_gists(){
			sf.MyListGist();
			}
			
			@Then displayed list all gist 	
			public void displayed_list_all_gist(){
			sf.inGistWulan();
			}
  ```
  
