# reflection-api-java-example

This is a Demo java Class in which i have written a code for accessing any private fields or methods from outside
the java class using java Reflection Api.
Reflection Api provides various tools for inspecting any java object. 
Using these stuffs one can violate the singleTon design pattern or the concept of private keyword in java.


#Creating an Object of a class which have single construtor of private type
     Constructor con=Class.forName("Test").getDeclaredConstructors()[0];
     con.setAccessible(true);
     creating new object from previously accessed constructor
		 Object obj=con.newInstance(null);
	   //type casting the object as Test Type	
		  
      Test test=(Test)obj;
	    now you have  Test class object you can play with it as you use to play with an normal objects
      test.defaultMethod();
     
#Accessing a Private Field of an class
    // accessing field
    //here a is private field of Test Class
		Field f=Class.forName("Test").getDeclaredField("a");
	
		f.setAccessible(true);
		// private field of Test Class via test object
	there may be multiple objects of a Test class so we must pass a reference address of object to Filed object whose field we
  wants to access
  System.out.println(f.get(test));

#Accessing a Private Method  of an class
Method m=Class.forName("Test").getDeclaredMethods()[1];
		
		m.setAccessible(true);
		
		Integer arr[]= new Integer[2];
		
		arr[0]=new Integer(19);
		
		arr[1]=new Integer(11);
		//p
		m.invoke(test,arr);

Feel free to ask any question
