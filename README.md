package selectclasspackage;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.Select;
import org.junit.Test;
//import org.junit.Before;
import static javax.swing.JOptionPane.showMessageDialog;

import java.util.ArrayList;
import java.util.List;

import org.openqa.selenium.WebElement;

public class selectclass {
	
	@Test
	public void Sample () throws InterruptedException {
		 System.setProperty("webdriver.gecko.driver", "C:\\\\Users\\Rajiv\\Downloads\\geckodriver-v0.14.0-win64\\geckodriver.exe");
		 WebDriver driver = new FirefoxDriver ();
		 
		 String URL = "https://www.goibibo.com/";
		 driver.get(URL);
		driver.manage().window().maximize();
		Thread.sleep(3000);
		
		
		Select seatingclass = new Select (driver.findElement(By.id("gi_class")));
		//List <WebElement> elementCount = seatingclass.getOptions();
		//System.out.println(elementCount.size());
		 List<WebElement> dropDwonList = new ArrayList<WebElement>();
	        dropDwonList = seatingclass.getOptions();
		
	        for(WebElement temp:dropDwonList)
	        {
	            
	        	seatingclass.selectByValue("B");
	        }
	   
	        
		for (int i = 0; i < dropDwonList.size(); i++)
	   {
	      new Select(driver.findElement(By.id("gi_class"))).selectByIndex(i);
	    }
		
		seatingclass.selectByVisibleText ("Premium Economy");
		System.out.println("Premium Economy selected");
		//showMessageDialog(null, "Check Now!");
		//Thread.sleep(3000);
		
		
		seatingclass.selectByIndex(2);
		System.out.println("First Class selected");
		showMessageDialog(null, "Check Now!");
		Thread.sleep(3000);
		
		seatingclass.selectByValue("B");
		System.out.println("Business Class selected");
		showMessageDialog(null, "Check Now!");
		Thread.sleep(3000);
		
		
			}
	

}
