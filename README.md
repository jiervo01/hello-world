# hello-world
Code for class 2/08
  package HW;

public class HW2 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		PositiveOrNegative(-9);
		Greatest(22,4,99);
		DayOfWeek(6);
	}
	
	public static void PositiveOrNegative(int x){
		if(x > 0)
			System.out.println(x + " is positive");
		if(x < 0)
			System.out.println(x + " is negative");
		else
			System.out.println(x+ " is zero");
	}
	
	public static void Greatest(int a, int b, int c){
		if(a > b && b > c)
			System.out.println(a + " is the greatest");
		if(a > c && c > b)
			System.out.println(a + " is the greatest");
		if(a > b && b == c)
			System.out.println(a + " is the greatest");
		if(b > a && a > c)
			System.out.println(b + " is the greatest");
		if(b > c && c > a)
			System.out.println(b + " is the greatest");
		if(b > a && a == c)
			System.out.println(b + " is the greatest");
		if(c > a && a > b)
			System.out.println(c + " is the greatest");
		if(c > b && b > a)
			System.out.println(c + " is the greatest");
		if(c > b && b == a)
			System.out.println(c + " is the greatest");
		if(a == b && b == c)
			System.out.println(a + " all numbers are equal");
		if(a==b && b > c)
			System.out.println(a + " is the greatest");
		if(c==b && b > a)
			System.out.println(c + " is the greatest");
	}
	public static void DayOfWeek(int day){
		String weekday="";
		switch(day){
		case 1: weekday ="1 - Monday";
		break;
		case 2: weekday ="2 - Tuesday";
		break;
		case 3: weekday ="3 - Wednesday";
		break;
		case 4: weekday ="4 - Thursday";
		break;
		case 5: weekday ="5 - Friday";
		break;
		case 6: weekday ="6 - Saturday";
		break;
		case 7: weekday ="7 - sunday";
		break;
		default:System.out.println("Invalid Day!");
		}
		System.out.println(weekday); 
	}
	}
