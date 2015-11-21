# Addition Game Loops and Methods
For this project we were asked to take our addition game and modify it to use arrays and have custom methods to call and to learn new tips and tricks for coding

## Java Code
```java
import java.util.Scanner;

public class LoopsAndMethodsAdditonGame {
	public static void main(String[] args) {
		//System.out.println("Hello class.");
		
		//Call the addition game method.
		AdditonGameMethod();
	}
	public static void AdditonGameMethod() {
		//System.out.println("Inside the addition game method.");
		
		int[] gameVariables = new int[4];
		gameVariables[0] = 5; //hardness;
		//int hardness = gameVariables[0];
		gameVariables[1] = 2; //hardnessStep;
		//int hardnessStep = 2;
		gameVariables[2] = 0; //score;
		//int score = 0;
		gameVariables[3] = 0; // 1 for true, 0 for false
		
		// Set up my for loop to go through the number of rounds
		int numberOfRounds = 3;
		for(int roundNumber = 1; 
		roundNumber <= numberOfRounds;  
		roundNumber = roundNumber + 1){
			//System.out.println("Inside the for loop. Round: " + roundNumber);
			System.out.print("Round " + roundNumber + " of " + numberOfRounds + ". ");
			gameVariables = getAndCheckStudentAnswer(gameVariables);
			if(gameVariables[3] == 1){
				System.out.print("Your score was " + gameVariables[2] + " and is now ");
				gameVariables[2] = gameVariables[2] + gameVariables[0];
				System.out.print(gameVariables[2] + ". ");
				
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + gameVariables[0] + " and is now ");
					gameVariables[0] = gameVariables[0] * gameVariables[1];
					System.out.println(gameVariables[0] + ".");
				}
			}else{
				System.out.print("Your score is " + gameVariables[2] + ". ");
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + gameVariables[0] + " and is now ");
					if(gameVariables[0]>5){
						gameVariables[0] = gameVariables[0] / gameVariables[1];
					}
					System.out.println(gameVariables[0] + ".");
					
				}
				
			}
		}
		System.out.print("\nThe game is complete. ");
		System.out.println("Your final score was " + gameVariables[2] );
	}
	
	public static int[] getAndCheckStudentAnswer(int[] gameVariables) {
		//System.out.println("Inside get and check student answer method.");
		int number1 = (int)(Math.random()*gameVariables[0]);
		int number2 = (int)(Math.random()*gameVariables[0]);
		System.out.print("Add " + number1 + " and " + number2 +": ");
		//Scanner input = new Scanner(System.in);
		//int studentAnswer = input.nextInt();
		Scanner get = new Scanner(System.in);
		int studentAnswer = get.nextInt();
		if(studentAnswer == (number1 + number2)){
			System.out.print("Correct. ");
			gameVariables[3] = 1;
			
		}else{
			System.out.println("Nice try, but the correct answer was " 
					+ (number1 + number2) + ".");
			gameVariables[3] = 0;
		}
		return gameVariables;
	}
}
```

## Console Output
```
Round 1 of 3. Add 2 and 2: 4
Correct. Your score was 0 and is now 5. Your hardness was 5 and is now 10.
Round 2 of 3. Add 0 and 2: 2
Correct. Your score was 5 and is now 15. Your hardness was 10 and is now 20.
Round 3 of 3. Add 19 and 18: 37
Correct. Your score was 15 and is now 35. 
The game is complete. Your final score was 35

```

## Command Prompt Output
```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

C:\Users\Brinden Wallace>cd workspace

C:\Users\Brinden Wallace\workspace>cd "Loops and methods"

C:\Users\Brinden Wallace\workspace\Loops and methods>echo # additiongameloopsand
methods >> README.md

C:\Users\Brinden Wallace\workspace\Loops and methods>git init
'git' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\Brinden Wallace\workspace\Loops and methods>
```

## Conclusion
This project we worked on some in class with the coding. we added in our array today by taking our variables and changing them from being multiple variables and made them all into one big variable list so we could use a custom test method. I did however run into problems with getting git to work on my computer. I posted the command promt in my files so we can figure out what im doing wrong, because this is my first time doing git on my home computer and im not quite sure what im doing wrong to get the error.
