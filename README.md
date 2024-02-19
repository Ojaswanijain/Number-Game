import java.util.Random;
import java.util.Scanner;

public class NumberGame
 {
    public static void main(String[] args) 
    {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int minRange = 1;
        int maxRange = 100;
        int attemptsLimit = 5;
        int score = 0;

        boolean playAgain = true;
        while (playAgain)
         {
            int targetNumber = random.nextInt(maxRange - minRange + 1) + minRange;
            System.out.println("Welcome to Guess the Number Game!");
            System.out.println("I'm thinking of a number between " + minRange + " and " + maxRange + ".");
            System.out.println("You have " + attemptsLimit + " attempts to guess it.");

            int attempts = 0;
            boolean guessedCorrectly = false;
            while (attempts < attemptsLimit && !guessedCorrectly)
              {
                System.out.print("Enter your guess: ");
                int guess = scanner.nextInt();
                attempts++;

                if (guess == targetNumber)
                  {
                    System.out.println("Congratulations! You guessed the number correctly in " + attempts + "   attempts.");
                    guessedCorrectly = true;
                    score++;
                  } else if (guess < targetNumber)
                   {
                    System.out.println("Too low! Try again.");
                   } else
                     {
                      System.out.println("Too high! Try again.");
                     }
             }

             if (!guessedCorrectly)
             {
                System.out.println("Sorry, you've run out of attempts. The correct number was: " + targetNumber);
             }

              System.out.println("Your current score: " + score);
              System.out.print("Do you want to play again? (yes/no): ");
              String playAgainChoice = scanner.next();
              playAgain = playAgainChoice.equalsIgnoreCase("yes");
         }

          System.out.println("Thanks for playing Guess the Number!");
    }
}
