# Java 8 Lambda Expression  
## Sample code for lambda expression 
```java
	public static void main(String[] argv) throws Exception{
		String[] strArr = new String[]{"string1", "str2", "string3", "str4"};
		Arrays.sort(strArr, (String a , String b)->Integer.compare(a.length(), b.length()));
		for (String str : strArr)
			System.out.println(str);
	}
``` 
## Passing method reference for lambda method  
If there exists some methods in libraries provided the exactly operation you want to do in the lambda expression, you just omit the parameter, and the "->", just put the method reference  
```java
Arrays.sort(strings, (x, y) -> x.compareToIgnoreCase(y))
equals
Arrays.sort(strings, String::compareToIgnoreCase)
```  
There are 4 format of method reference in the lambda expression  
* object::instanceMethod
* Class::staticMethod
* Class::instanceMethod  
For first and second form, the expanded lambda expression will have same arguments as the method defintion  
For third form, the expanded lambda will be look like (x, args)->x.instanceMethod(args)  