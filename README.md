		package projectIdea2;
		import java.util.Scanner;

		public class MastermindGame
		{
		  public static void main(String[] args)
		  {
		      //game instructions
		      System.out.println("Welcome to Mastermind!");
		      System.out.println("The computer will generate a passcode with your specified number of digits.");
		      System.out.println("Your job is to break that code!");
		      System.out.println("After each guess, the computer will tell you how many correct digits are in the correct position.");
		      System.out.println("It will do this by printing one X for each correct digit.");
		      System.out.println("It does not tell you which digit is correct.");
		      System.out.println("If you do not see any Xs print, none of your digits were correct.");
		      System.out.println("GOOD LUCK!");

	      //ask user to determine how many digits the code will be
	      System.out.println("How many digits would you like the code to be?");
	      //enable input from the user
	      Scanner in = new Scanner(System.in);
	      //read the integer the user types
	      int length = in.nextInt();
	      //create the new game with the indicated number of digits
	      Mastermind game = new Mastermind(length);

	      //ssshh!! cheating so we can see if this works!
	      System.out.println("Shhh! Just so we know if our program works, the code is ");
	      //game.printCode();

	      //set up an array to hold the user's guesses
	      int[] guess = new int[length];

	      //set up a String to display the result of the guess
	      String guessResult = "";


	      //allow the user 4 tries to break the code
	      for (int j = 0; j < 4; j++)
	      {
		  //tell the user to take a guess
		  System.out.println("Gander a guess");
		  //loops as many digits (length) as they indicated the code should be
		  for (int i = 0; i< length; i++)
		  {
		      //ask the user to input their guess for this digit
		      System.out.println("Enter digit #" + (i+1) + ":");
		      //store their guess in the guess array
		      guess[i] = in.nextInt();
		  }
		  //call the method in the Mastermind class that checks their guess against the code
		  guessResult = game.attempt(guess);
		  //it will print out as many Xs as correct digits, order irrelevant
		  System.out.println ( guessResult);

		  //if the user guess, game over so end the main method with "return"
		  if (guessResult.equals("YOU WIN!!"))
		      return;
	      }
	      //if we get outside the loop, user wasn't able to guess, "game over"
	      System.out.println("~~~GAME OVER~~~");
	  }
	}

	class Mastermind
	{
	  private int[] code;

	  //overloaded constructor
	  public Mastermind(int length)
	  {
	      //set the length of the array to the number of digits the user requested
	      code = new int[length];

	      //walk through the code
	      for (int i = 0; i < code.length; i++)
	      {
		  //add a random digit (0-2 in this case) to the code
		  code[i] = (int)(Math.random() * 3);
	      }
	  }

	  //method to check the user's guess against the code
	  public String attempt(int[] guess)
	  {
	      String response = "";
	      boolean verify = true;

	      //walk through the guess array
	      for (int i = 0; i<guess.length;i++)
	      {
		  //compare guess array to code
		  //if digits are the same, add an X to response string
		  if (guess[i] == code[i])
		     response += "X";
		  //if digits are not equal, set verify to false because the guess is not the code
		  else
		      verify = false;
	      }

	      //if verify was never set to false, then the user guessed correctly so return YOU WIN
	      if (verify == true)
		  return "YOU WIN!!";

	      //if code gets here, user did not guess correctly, return the String with Xs for correct number of digits.
	      return response;
	  }

		  //created this method so we can cheat to check that our game works
		  public void printCode()
		  {
		      String answer = "";
		      //walk through code, concatenating the digit to the answer string
		      for (int i = 0; i < code.length; i++)
		      {
			  answer += code[i] + " ";
		      }
		      //print the code
		      System.out.println(answer);
		  }
		}
