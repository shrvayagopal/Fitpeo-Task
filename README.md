package AutomationPractice.SeleniumBasics;
import java.awt.Window;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import io.github.bonigarcia.wdm.WebDriverManager;
public class FitPeoTask {
public static void main(String[] args) throws InterruptedException
{
// TODO Auto-generated method stub
WebDriverManager.chromedriver().setup();
WebDriver driver=new ChromeDriver();
//1.Navigate to the FitPeo Homepage:
driver.get("https://fitpeo.com");
driver.manage().window().maximize();
Thread.sleep(5000);  	
//2.Navigate to the Revenue Calculator Page:
driver.findElement(By.xpath("(//*[@class='satoshi MuiBox-root css-1aspamu'])[5]")).click();
Thread.sleep(1000);  	
//3.Scroll Down to the Slider section:
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("window.scrollBy(0,500)");
Thread.sleep(6000);  
// 4. Adjust the Slider To 823:
WebElement MSlider=driver.findElement(By.xpath("(//*[@type='range'])"));
js.executeScript("window.scrollBy(0,500)");
Actions  act=new Actions(driver);
act.dragAndDropBy(MSlider, 94, 0).perform();
js.executeScript("window.scrollBy(0,300)");
Thread.sleep(6000);  
//4. Adjust the Slider To 823:
WebElement MSlider2=driver.findElement(By.xpath("(//*[@type='range'])"));
js.executeScript("window.scrollBy(0,500)");
Actions  acto=new Actions(driver);
act.dragAndDropBy(MSlider2, -700, 0).perform();
js.executeScript("window.scrollBy(0,300)");
//5.Update the Text Field:
Thread.sleep(5000);  
driver.findElement(By.xpath("(//*[@type='number'])")).click();
Thread.sleep(3000); 
driver.findElement(By.xpath("(//*[@type='number'])")).clear();
driver.findElement(By.xpath("(//*[@type='number'])")).sendKeys("820");
js.executeScript("window.scrollBy(0,300)");
Thread.sleep(5000); 
driver.findElement(By.xpath("(//*[@type='checkbox'])[1]")).click();
driver.findElement(By.xpath("(//*[@type='checkbox'])[2]")).click();
driver.findElement(By.xpath("(//*[@type='checkbox'])[3]")).click();
driver.findElement(By.xpath("(//*[@type='checkbox'])[8]")).click();
Thread.sleep(5000); 
WebElement total=driver.findElement(By.xpath("(//*[@class='MuiTypography-root MuiTypography-body1 inter css-hocx5c'])[4]"));
System.out.println("Value is"+total.getText());

/* driver.findElement(By.xpath("(//*[@type='number'])")).sendKeys("10"); */
}
}
