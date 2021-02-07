# hello-world
Code for class 2/01
Hello i am a freshman at NYIT and a computer/electrical engineering major

Name,Email,ID

	public class NameEmailID {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		String name = "Joseph Iervolino";
		String Email = "jiervo01@nyit.edu";
		int IDN = 1280238;
		System.out.println("name = " + name);
		System.out.println("email = " + Email);
		System.out.println("id number = " + IDN);

	}

	}

addition

	public class Addition {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int x = 9;
		int y = 27;
		int sum = x+y;
		System.out.print("Sum =" + sum);

	}

	}

Input Addition

	import java.util.Scanner;

	public class InputAddition {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int a,b;
		Scanner num1 = new Scanner(System.in);
		System.out.println("Please input your first number");
		a = num1.nextInt();
		Scanner num2 = new Scanner(System.in);
		System.out.println("Please input your second number");
		b = num2.nextInt();
		int sum = a+b;
		System.out.println("your sum is " + sum);
	}
	}
