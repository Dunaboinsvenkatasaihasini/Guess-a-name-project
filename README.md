# Guess-a-name-project

//Number Guessing Game

import java.util.Scanner;
import java.util.Random;

public class task9{

	public static void main(String args[])
    { 
    		generateRandom();
    } //end main method



    public static void generateRandom(){
    	//Creating object of Random Class
    	Random rand=new Random();

    	//Generating a random number between 0-10
    	int randomNum=rand.nextInt(11);

    	//Calling guess method
    	guess(randomNum);
    }//end generateRandom method



    public static void guess(int randomNum){
    	//creating an object of Scanner Class
    	Scanner in=new Scanner(System.in);

    	//Welcome Message
    	System.out.println("");
    	System.out.println("Number Guessing Game");
    	System.out.print("Guess a number between 0-10: ");
    	int guess=in.nextInt();
    	System.out.println("");

    	//input validation
    	while (guess<0 || guess>10){
    		System.out.print("Guess a number between 0-10: ");
    		guess=in.nextInt();
    		System.out.println("");
    	}

    	//try again until you guess the correct number
    	int tries=0;
    	while(guess!=randomNum){
    		tries++;
    		System.out.println("Wrong Guess!");
    		System.out.print("Guess again: ");
    		guess=in.nextInt();
    		System.out.println("");

    		//input validation
    		while (guess<0 || guess>10){
    			System.out.print("Guess a number between 0-10: ");
    			guess=in.nextInt();
    			System.out.println("");
    		}
    	}

    	//Game Won
    	System.out.println("Correct Answer. You Won!");
    	System.out.println("Wrong Tries: "+tries);
    	System.out.println("");

    	//Play again or exit?
    	System.out.println("Press 1 to Play again.");
    	System.out.println("Press 0 to exit.");
    	int choice=in.nextInt();

    	if(choice==1)
    		generateRandom();
    	else
    		return;
    }//end guess method

}//end class
