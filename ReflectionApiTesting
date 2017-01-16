import java.lang.reflect.*;



public class ReflectionApiTesting {
	
	
	public static void main(String[] args) throws InstantiationException, SecurityException, ClassNotFoundException, IllegalAccessException, IllegalArgumentException, InvocationTargetException, NoSuchFieldException{
	
	
		
		/// accessing private constructor
		Constructor con=Class.forName("Test").getDeclaredConstructors()[0];
		
		con.setAccessible(true);
		
		Object obj=con.newInstance(null);
		
		Test test=(Test)obj;
		
		// non private method get called
		test.defaultMethod();
		
		
		/// accessing field
		Field f=Class.forName("Test").getDeclaredField("a");
		
		f.setAccessible(true);
		// private field of Test Class via test object
		System.out.println(f.get(test));
		
		Method m=Class.forName("Test").getDeclaredMethods()[1];
		
		m.setAccessible(true);
		
		Integer arr[]= new Integer[2];
		
		arr[0]=new Integer(19);
		
		arr[1]=new Integer(11);
		//p
		m.invoke(test,arr);
		
		
		
		
	}

}


class Test{
	
	private int a=10;
	
	private Test(){
		
	}
		void defaultMethod(){
		System.out.println("method1 is called");
		
	}
		private void privateMethod(int a,int b){
		System.out.println("method 2 is called  "+a);
		
	}
	
}
