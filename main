/*Author: Marco Ares
Worked with: Gideon Manahan
Programmin Assignment 4
Description: In this assingment we are making the game
			 Craps. While using while loops and for loops
			 and figuring out how craps works. Hopefully
			 I do this right and get a 100.
*/

#include "Header.h"

int main(void)
{
	//Let's start with all the variables we need
	int die1 = 0, die2 = 0, sum = 0, points = 0, result = 0, rolls = 0, menu = 0, exit = 0, check = 0, play = 0;
	double wager = 0.0, balance = 0.0, bank_balance = 0.0, initial_balance = 0.0;

	//for the randomize throw of the dice
	srand((unsigned int)time(NULL));

	printf("\n-----Welcome to Craps!!!-----\n");

	//start the game with a game menu
	do
	{
		menu = game_menu();
		printf("You chose option: %d \n", menu);
		//Im using switch because it is easier
		switch (menu)
		{
			//when player chooses option 1 which is game rules
		case 1:
			print_game_rules();

			//clears out the rules and returns to menu, makes the game cleaner to play
			system("pause");
			system("cls");
			game_menu(); //returns to menu
		//when player chooses option 2 and plays the game
		case 2:
			system("cls");
			balance = get_bank_balance(); //getting the bank balance
			do //do - while statements for playing the game
			{
				wager = get_wager_amount(); //asking for player's bet

				// to check if wager is bigger than balance
				do
				{
					if (check_wager_amount(wager, balance) == 0)
					{
						wager = get_wager_amount();
					}
					else
					{
						check = 1;
					}
				} while (check == 0);
				
				//First roll of the game
				printf("\n-----1st Roll-----\n");
				die1 = roll_die();
				printf("First die was %d & ", die1);
				die2 = roll_die();
				printf("Second die was %d\n", die2);
				sum = calculate_sum_dice(die1, die2);
				printf("You rolled a %d\n", sum);

				//The result of first roll
				result = is_win_loss_or_point(sum);
				if (result == 1)
				{
					chatter_messages_wager(result);
					balance = adjust_bank_balance(balance, wager, result);
					printf("Your bank balance is now %.2lf\n", balance);
				}
				else if (result == 0)
				{
					chatter_messages_wager(result);
					balance = adjust_bank_balance(balance, wager, result);
					printf("Your bank balance is now %.2lf\n", balance);
				}
				else
				{
					//Second round of the game if didnt roll a 7
					points = sum; // adding points to the game
					do
					{
						printf("\n-----Next Roll-----\n");
						die1 = roll_die();
						printf("First die was %d & ", die1);
						die2 = roll_die();
						printf("Second die was %d\n", die2);
						sum = calculate_sum_dice(die1, die2);
						printf("You rolled a %d\n", sum);
						result = is_point_loss_or_neither(sum, points);
						if (result == 1)
						{
							chatter_messages_wager(result);
							balance = adjust_bank_balance(balance, wager, result);
							printf("Your bank balance is now %.2lf\n", balance);
						}
						else if (result == 0)
						{
							chatter_messages_wager(result);
							balance = adjust_bank_balance(balance, wager, result);
							printf("Your bank balance is now %.2lf\n", balance);
						}
					} while (result == -1);
				
				}

				//This makes the game cleaner to play
				system("pause"); 
				system("cls"); // clears out everytime you want to play again, (also a friend taught me this code)
				
				//when the bank balance is 0 the game is done
				if (balance == 0)
				{
					printf("\nYou lost all your money!\n");
					printf("\n-----GAME OVER-----\n");
					break;
				}
				//if not ask player to play more and win more
				else
				{
					printf("Do you wanna keep playing to win more? Enter 1 for Yes, 0 for No: \n");
					scanf("%d", &play);
				}
			} while (play == 1);
		//If player doesnt wanna play exit game
		case 3:
			printf("You exited game\n");
			exit = 1;
		}
	} while (exit != 1);
	return 0;
}
