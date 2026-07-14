import java.util.Scanner;

class EscapeRoom {

    int lives = 3;
    Scanner sc = new Scanner(System.in);

    public void startGame() {

        System.out.println("==================================");
        System.out.println("      WELCOME TO ESCAPE ROOM      ");
        System.out.println("==================================");

        room1();
    }

    public void room1() {
        while (lives > 0) {
            try {
                System.out.println("\nROOM 1 - Guess the Number");
                System.out.println("Guess a number between 1 and 10");
                int guess = sc.nextInt();

                if (guess == 8) {
                    System.out.println("Correct! Door Unlocked.");
                    room2();
                    return;
                } else {
                    lives--;
                    System.out.println("Wrong! Lives Left = " + lives);
                }
            } catch (Exception e) {
                System.out.println("Invalid Input!");
                sc.nextLine();
            }
        }
        gameOver();
    }

    public void room2() {
        while (lives > 0) {
            try {
                int arr[] = {10, 20, 30, 40};

                System.out.println("\nROOM 2 - Array Puzzle");
                System.out.println("What is the index of 30 in {10,20,30,40} ?");
                int ans = sc.nextInt();

                if (ans == 2) {
                    System.out.println("Correct! Door Unlocked.");
                    room3();
                    return;
                } else {
                    lives--;
                    System.out.println("Wrong! Lives Left = " + lives);
                }
            } catch (Exception e) {
                System.out.println("Invalid Input!");
                sc.nextLine();
            }
        }
        gameOver();
    }

    public void room3() {
        while (lives > 0) {
            try {
                String word = "JAVA";

                System.out.println("\nROOM 3 - String Puzzle");
                System.out.println("What is the length of the word JAVA?");
                int ans = sc.nextInt();

                if (ans == word.length()) {
                    System.out.println("Correct! Door Unlocked.");
                    room4();
                    return;
                } else {
                    lives--;
                    System.out.println("Wrong! Lives Left = " + lives);
                }
            } catch (Exception e) {
                System.out.println("Invalid Input!");
                sc.nextLine();
            }
        }
        gameOver();
    }

    public void room4() {
        while (lives > 0) {
            try {
                System.out.println("\nROOM 4 - Java MCQ Challenge");
                System.out.println("Which package contains the Scanner class?");
                System.out.println("1. java.io");
                System.out.println("2. java.util");
                System.out.println("3. java.lang");
                System.out.println("4. java.net");

                int choice = sc.nextInt();

                if (choice == 2) {
                    System.out.println("\nExit Door Opens...");
                    System.out.println("🎉 YOU ESCAPED! 🎉");
                    return;
                } else {
                    lives--;
                    System.out.println("Wrong! Lives Left = " + lives);
                }
            } catch (Exception e) {
                System.out.println("Invalid Input!");
                sc.nextLine();
            }
        }
        gameOver();
    }

    public void gameOver() {
        System.out.println("\nGAME OVER!");
        System.out.println("You lost all your lives.");
    }
}

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        while (true) {

            System.out.println("\n===== ESCAPE ROOM =====");
            System.out.println("1. Start Game");
            System.out.println("2. Exit");
            System.out.print("Enter Choice: ");

            try {
                int choice = sc.nextInt();

                if (choice == 1) {
                    EscapeRoom game = new EscapeRoom();
                    game.startGame();
                    break;
                } else if (choice == 2) {
                    System.out.println("Thank You!");
                    break;
                } else {
                    System.out.println("Invalid Choice!");
                }

            } catch (Exception e) {
                System.out.println("Enter numbers only!");
                sc.nextLine();
            }
        }

        sc.close();
    }
}
