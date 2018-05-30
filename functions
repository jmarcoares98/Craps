#include "Header.h"

//for switch statements
int game_menu(void)
{
	int option = 0;
	printf("Menu:\n");
	printf("1. Craps Rules\n");
	printf("2. Play Game\n");
	printf("3. Exit Game\n");
	printf("Choose an option:\n");
	scanf("%d", &option);
	return option;
}

void print_game_rules(void)
{
	printf("Craps Game Rules: You, the player rolls a roandom dice\n");
	printf("Each die has 6 faces. If the sum of the\n");
	printf("of the dice is 7 or 11 you win money!!\n");
	printf("If the sum is 2, 3 or 12 on the first throw\n");
	printf("(called craps). You lose. If the sum is\n");
	printf("4, 5, 6, 8, 9 or 10 on the first throw then the sum\n");
	printf("becomes the player's 'points'. To win you must\n");
	printf("roll the dice until you 'make your point.'\n");
	printf("The player loses by rolling a 7 before making the point\n\n");
}

//prompt the player to get initial bank balance. I asked for a minimum of $1000
double get_bank_balance(void)
{
	double balance = 0.0;
	printf("To start playing enter a bank balance:\n");
	scanf("%lf", &balance);
	return balance;
}

//Wager with the bank balance that the player, to bet in game
double get_wager_amount(void)
{
	double wager = 0.0;
	printf("Enter how much you want to wager:\n");
	scanf("%lf", &wager);
	return wager;
}

//this is where, if the player exceeds amount of wager than bank balance
int check_wager_amount(double wager, double balance)
{
	int amount = 0;
	if (wager <= balance)
	{
		amount = 1;
	}
	if (wager > balance)
	{
		printf("Your wager exceeds your bank balance\n");
		amount = 0;
	}
	return amount;
}

//The first roll of the dice
int roll_die(void)
{
	int die1 = 0;
	die1 = (1 + (rand() % 6));
	return die1;
}

//The second roll of the dice
int roll_die2(void)
{
	int die2 = 0;
	die2 = (1 + (rand() % 6));
	return die2;
}

//Getting the sum of the two dies
int calculate_sum_dice(int die1, int die2)
{
	int sum = 0;
	sum = die1 + die2;
	return sum;
}

//whether the player wins, loses or gets a point. Use if statements on this one
int is_win_loss_or_point(int sum)
{
	int result = 0;
	if (sum == 7 || sum == 11)
	{
		result = 1;
	}
	else if (sum == 2 || sum == 3 || sum == 12)
	{
		result = 0;
	}
	else
	{
		result = -1;
	}
	return result;
}

//This where the game continues and determines result of the roll after the first one
int is_point_loss_or_neither(int sum, int points)
{
	int result = -1;
	if (sum == points)
	{
		result = 1; 
	}
	if (sum == 7)
	{
		result = 0; //game has ended
	}
	return result;
}

//This is where we add or subtract the wager in the bank balance
double adjust_bank_balance(double balance, double wager, int result)
{
	if (result == 1)
	{
		balance += wager;
	}
	if (result == 0)
	{
		balance -= wager;
	}
	return balance;
}

//chatter messages when player wins some money or lose money
void chatter_messages_wager(int result)
{
	if (result == 1)
	{
		printf("AYE! you won some money!\n");
	}

	if (result == 0)
	{
		printf("AWW, you lost some money\n");
	}
}
