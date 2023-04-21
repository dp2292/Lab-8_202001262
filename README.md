# Lab-8_202001262
# Name - Devansh Patel
# ID - 202001262

## 1. Creating a new Eclipse project, and within the project create a package and defining the class named Boa.




![1](https://user-images.githubusercontent.com/75575802/233605101-9ae420af-073b-454d-a4ea-db26ebfd9ae4.png)

## Code
```
// represents a boa constrictor
public class Boa {
	
	private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;
	public Boa (String name, int length, String favoriteFood){
	this.name = name;
	this.length = length;
	this.favoriteFood = favoriteFood;
	}
// returns true if this boa constrictor is healthy
	public boolean isHealthy(){
	return this.favoriteFood.equals("granola bars");
	}
// returns true if the length of this boa constrictor is
// less than the given cage length
	public boolean fitsInCage(int cageLength){
	return this.length < cageLength;
	}
}
```

### Test method to test the behaviour of the Boa class : 
![2](https://user-images.githubusercontent.com/75575802/233605292-ec8a3591-0fe7-4e4e-b602-a76b14bef19c.png)
![3](https://user-images.githubusercontent.com/75575802/233605414-c10a4908-d3f4-431c-bf4a-cfc3b4906a18.png)

## Code
```
import static org.junit.Assert.*;

import org.junit.Test;
import org.junit.Before;
import org.junit.Test;

public class BoaTest {
	
	
    private Boa jeni;
    private Boa kenn;
    public Boa mike;
    
    @Before
    public void setUp() throws Exception {
    jeni = new Boa("Jennifer", 2, "grapes");
    kenn = new Boa ("Kenneth", 3, "granola bars");
    mike =new Boa("mike",5,"mango");
    }
    
	@Test
	public void testIsHealthy() {
        assertTrue(kenn.isHealthy());
        assertFalse(jeni.isHealthy());
        assertFalse(mike.isHealthy());
	}

	@Test
	public void testFitsInCage() {
		
        assertFalse(jeni.fitsInCage(1)); // cage length is less than the length of boa
        assertFalse(jeni.fitsInCage(2)); // cage length is equal to length of boa
        assertTrue(jeni.fitsInCage(5));  // cage length is greater than length of boa
        
        assertFalse(kenn.fitsInCage(2)); // cage length is lesser than the length of boa
        assertFalse(kenn.fitsInCage(3)); // cage length is equal to length of boa
        assertTrue(kenn.fitsInCage(6));  // cage length is greater than the length of boa
        
        assertFalse(mike.fitsInCage(3)); // cage length is lesser than the length of boa
        assertFalse(mike.fitsInCage(5)); // cage length is equal to length of boa
        assertTrue(mike.fitsInCage(10)); // cage length is greater than the length of boa
	}
}
```

![4](https://user-images.githubusercontent.com/75575802/233605617-e2ccfa94-e110-4d51-a1c4-5acdb0049e5e.png)


### Modified Boa class with the new lengthInInches() method:

![5](https://user-images.githubusercontent.com/75575802/233605692-be888eb1-896d-4fab-9ed5-1ebbcbef6f16.png)

## Code
```
// represents a boa constrictor
public class Boa {
	
	private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;

	public Boa (String name, int length, String favoriteFood){
	this.name = name;
	this.length = length;
	this.favoriteFood = favoriteFood;
	}

// returns true if this boa constrictor is healthy
	public boolean isHealthy(){
	return this.favoriteFood.equals("granola bars");
	}

// returns true if the length of this boa constrictor is
// less than the given cage length
	public boolean fitsInCage(int cageLength){
	return this.length < cageLength;
	}
	
	//produce the length of the Boa in inches
	public int lengthInInches() {
		return this.length*12;
	}
}
```

### Here's an example of a new test case in the BoaTest class that tests the lengthInInches() method:

![6](https://user-images.githubusercontent.com/75575802/233605812-9aa3e03d-0441-46ff-b971-94aedbb57d5f.png)

## Code

```
import static org.junit.Assert.*;

import org.junit.Test;
import org.junit.Before;
import org.junit.Test;

public class BoaTest {
	
	
    private Boa jeni;
    private Boa kenn;
    public Boa mike;
    
    @Before
    public void setUp() throws Exception {
    jeni = new Boa("Jennifer", 2, "grapes");
    kenn = new Boa ("Kenneth", 3, "granola bars");
    mike =new Boa("mike",5,"mango");
    }
    
	@Test
	public void testIsHealthy() {
        assertTrue(kenn.isHealthy());
        assertFalse(jeni.isHealthy());
        assertFalse(mike.isHealthy());
	}

	@Test
	public void testFitsInCage() {
		
        assertFalse(jeni.fitsInCage(1)); // cage length is less than the length of boa
        assertFalse(jeni.fitsInCage(2)); // cage length is equal to length of boa
        assertTrue(jeni.fitsInCage(5));  // cage length is greater than length of boa
        
        assertFalse(kenn.fitsInCage(2)); // cage length is lesser than the length of boa
        assertFalse(kenn.fitsInCage(3)); // cage length is equal to length of boa
        assertTrue(kenn.fitsInCage(6));  // cage length is greater than the length of boa
        
        assertFalse(mike.fitsInCage(3)); // cage length is lesser than the length of boa
        assertFalse(mike.fitsInCage(5)); // cage length is equal to length of boa
        assertTrue(mike.fitsInCage(10)); // cage length is greater than the length of boa
	}
	
	@Test
	public void lengthInInches() {
		assertEquals(24,jeni.lengthInInches());
		assertEquals(36,kenn.lengthInInches());
		assertEquals(60,mike.lengthInInches());
	}
	
}
```

This test case is designed to verify that the lengthInInches() method works correctly on each of the Boa objects created in the setUp() method by checking that the expected value matches the actual value returned by the method using the assertEquals() method. The @Test annotation specifies that this method is a JUnit test and should be executed.
