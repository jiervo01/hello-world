# hello-world
Code for class 4/5
Pay Calculator
	abstract class PayCalculator
	{	
	//Create an abstract class PayCalculator that has an attribute payRate given in dollars per hour.
	protected double payRate;

	//The class should also have a method computePay(hours) that returns the pay for a given amount of time.
	public double computePay(int hours)
	{
	return hours*payRate;
	}
		}

	//Derive a class RegularPay from PayCalculator, as described above.
	class RegularPay extends PayCalculator
	{
	//It should have a constructor that has a parameter for the pay rate. It should not override any of the methods.
	public RegularPay(double payRate)
	{
	this.payRate = payRate;
	}
	}

Hazzard Pay
	class HazardPay extends RegularPay
	{
	public HazardPay(double payRate)
	{	
	super(payRate);
	}
	//The new method should return the amount returned by the base class method multiplied by 1.5.
	public double computePay(int hours)
	{
	return hours*payRate*1.5;
	}
	}

Discount policy
	abstract class DiscountPolicy{

     abstract int computeDiscount(int count, int itemCost);

	}
Bulk Discount
	class BulkDiscount extends DiscountPolicy

	{    

	private double percent;

	private double minimum;

	public BulkDiscount(int minimum, double percent)

	{

	this.minimum = minimum;

	this.percent = percent;

	}

	public double computeDiscount(int count, double itemCost)

	{

	if (count >= minimum)

	{

	return (percent/100)*(count*itemCost); //discount is total price * percentage discount

	}

	return 0;

	}

	int computeDiscount(int count, int itemCost) {
	return 0;
	}

	}
Message encoder
	public interface MessageEncoder {
    	public abstract String encode(String plainText);
	}
MEssage decoder
	public interface MessageDecoder {
 	public abstract String decode(String cipherText);
	}
Substitution cipher
	public class SubstitutionCipher implements MessageEncoder, MessageDecoder{
    	private int shiftBy;   
   

    	public SubstitutionCipher (int shiftBy){
        this.shiftBy = shiftBy;
    	}
   

  	  private char shift(char ch, int shiftValue){
        char shiftedChar = ch;       

        if(ch >= 'a' && ch <= 'z')
            shiftedChar = (char) ( 'a' + ( ch - 'a' + shiftValue ) %26 );

        else if(ch >= 'A' && ch <= 'Z')
            shiftedChar = (char) ( 'A' + ( ch - 'A' + shiftValue ) %26 );
        return shiftedChar;
 	   }
   

 	   public String encode(String plainText){
   	     String encodedMsg = "";
   	     for( int i = 0; i < plainText.length(); i++){
            char ch = plainText.charAt(i);
            encodedMsg += shift(ch, shiftBy);
     	   }
     	   return encodedMsg;
  	  }
	
	@Override
	public String decode(String cipherText) {

		return null;
	}

	} 

Driver
	public static void main(String[] args) {

				HazardPay HP = new HazardPay(44);
				System.out.println("Pay for HP is given by " +HP.computePay(45));
				

                DiscountPolicy dp = new BulkDiscount(10,5);
                System.out.println("Bulk Discount :"+dp.computeDiscount(20, 20));
                
                int choise, choise2;
                java.util.Scanner input = new java.util.Scanner(System.in);

                while (true) {

                    System.out.println("\n\n1.To Encode A Message");
                    System.out.println("2.Exit");

                    do {
                        System.out.print("Enter your choise: ");
                        choise = input.nextInt();
                        input.nextLine();

                        if (choise == 2)
                            System.exit(0);

                    } while (choise >1  || choise < 1);

                    System.out.println("\n\n1.Substitution Cipher");
                    System.out.println("2.Exit");

                    do {
                        System.out.print("Enter your choise: ");
                        choise2 = input.nextInt();
                        input.nextLine();

                        if (choise2 == 3)
                            System.exit(0);

                    } while (choise2 > 2 || choise2 < 1);

                    String text;
                    int n;
                    switch (choise) {

                    case 1: 
                        System.out.print("Enter text to be encode: ");
                        text = input.nextLine();
                        String encodedMsg = "";

                        switch (choise2) {
                        case 1: 
                            System.out.print("Enter shift value: ");
                            n = input.nextInt();
                            input.nextLine();
                            SubstitutionCipher sub = new SubstitutionCipher(n);
                            encodedMsg = sub.encode(text);
                            System.out.println("Encode Message: " + encodedMsg);
                            break;
                        } 
                        break;
                    } 
                } 

			}
	
