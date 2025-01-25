# Rock-Paper-Scissors
This is a simple game of Rock Paper Scissors where Player will play against Computer

import java.util.Random;
import java.util.Scanner;

public class game{
    public static void main(String [] args){
        Scanner scan = new Scanner(System.in);
        
            String[] rps = {"rock" , "paper" , "scissors"};
            String computer;
            String player ;

        while(true){
            computer = rps[new Random().nextInt(rps.length)];
            System.out.println("Enter Your Choice (rock , paper , scissors)");
            player = scan.nextLine();
           

            if (!player.equals("rock") && !player.equals("paper") && !player.equals("scissors")){
                System.out.println(player + " is not a valid move.");
                continue;
            }
            
            System.out.println("Player : " + player);
            System.out.println("Computer : " + computer);


            if (player.equals(computer)) {
                System.out.println("The game is a tie.");
            } else if (player.equals("rock") && computer.equals("scissors") ||
                       player.equals("scissors") && computer.equals("paper") ||
                       player.equals("paper") && computer.equals("rock")) {
                System.out.println("You won!");
            } else {
                System.out.println("Computer won!");
            }

            System.out.println("Do you want to play again? (yes/no)");
            String playAgain = scan.nextLine().toLowerCase();
            if (!playAgain.equals("yes")) {
                System.out.println("Thank you for playing! Goodbye!");
                break;
            }
        }
        scan.close();
    }
}
