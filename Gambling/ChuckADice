/* SELF ASSESSMENT 

1. ResolveBet
I have correctly defined ResolveBet which takes the bet type (String) and the Wallet object, and a void return type [Mark out of 7: 7].
Comment: i did
My program presents the amount of cash in the wallet and asks the user how much he/she would like to bet [Mark out of 8: 8].
Comment: it does
My program ensures the bet amount is not greater than the cash in the wallet [Mark out of 5: 5].
Comment: it does
My program creates three Dice objects, rolls them and creates a total variable with a summation of the roll values returned [Mark out of 15: 15]..
Comment: it does
My program determines the winnings by comparing the bet type with the total and comparing the bet type with the dice faces for the triple bet [Mark out of 20:20 ].
Comment: it does
My program outputs the results (win or loss) and adds the winnings to the wallet if user wins or removes the bet amount from the wallet if the user loses [Mark out of 10: 10].
Comment: it does

2. Main
I ask the user for the amount of cash he/she has, create a Wallet object and put this cash into it [Mark out of 15: 15]
Comment: i do
My program loops continuously until the user either enters quit or the cash in the wallet is 0 [Mark out of 5: 5]
Comment: it does
I ask the user to enter any of the four bet types or quit [Mark out of 5: 5].
Comment: i do
My program calls resolveBet for each bet type entered [Mark out of 5: 5 ].
Comment: it does
At the end of the game my program presents a summary message regarding winnings and losses [Mark out of 5: 5]
Comment: it does

 Total Mark out of 100 (Add all the previous marks): 100
*/
import java.util.Scanner;

public class ChuckADice {
	public static Scanner input = new Scanner(System.in);

	public static void resolveBet(double walletMoney, String betType, Wallet playerWallet)
	{
		boolean quit = false;
		double money = 0;
		Dice dice1 = new Dice();
		Dice dice2 = new Dice();
		Dice dice3 = new Dice();
		playerWallet.check();
		System.out.print("You have ฿" + walletMoney + ". Enter how much money you are investing: ");
		while(!quit)
		{
			money = input.nextDouble();
			if(money > walletMoney)
			{
				System.out.print("The amount you have entered is greater than the amount of money in your wallet, please try again\n");
			}
			if(money <= walletMoney)
			{
				quit = true;
			}
		}
		if (playerWallet.get(money) == true)
		{
			dice1.roll();
			dice2.roll();
			dice3.roll();
			int total = dice1.topFace() + dice2.topFace() + dice3.topFace();
			if (betType.equals("triple"))
			{
				System.out.print(dice1.topFace() + ", " + dice2.topFace() + ", " + dice3.topFace() + "\n");
				if ((dice1.topFace() == 1 && dice2.topFace() == 1 && dice3.topFace() == 1) || (dice1.topFace() == 6 && dice2.topFace() == 6 && dice3.topFace() == 6))
				{
					System.out.print("The house wins -> all " + dice1.topFace() + "s\n");
				}
				else if ((dice1.topFace() == 2 && dice2.topFace() == 2 && dice3.topFace() == 2) || (dice1.topFace() == 3 && dice2.topFace() == 3 && dice3.topFace() == 3) ||
						(dice1.topFace() == 4 && dice2.topFace() == 4 && dice3.topFace() == 4) || (dice1.topFace() == 5 && dice2.topFace() == 5 && dice3.topFace() == 5))
				{
					money = money + money * 30;
					playerWallet.put(money);
					System.out.print("The player wins -> all " + dice1.topFace() + "s\n");
					System.out.print("+฿" + money + "\n");
				}
				else
				{
					System.out.print("The house wins, you have lost ฿" + money + "\n");
				}
			}
			if (betType.equals("field"))
			{
				System.out.print(dice1.topFace() + ", " + dice2.topFace() + ", " + dice3.topFace() + "\n");
				if(total >= 8 && total <= 12)
				{
					System.out.print("The house wins, you have lost ฿" + money + "\n");
				}
				else
				{
					System.out.print("The player wins\n");
					System.out.print("+฿" + money + "\n");
					money = money * 2;
					playerWallet.put(money);
				}
			}
			if (betType.equals("high"))
			{
				System.out.print(dice1.topFace() + ", " + dice2.topFace() + ", " + dice3.topFace() + "\n");
				if(total <= 10 || (dice1.topFace() == 4 && dice2.topFace() == 4 && dice3.topFace() == 4) || (dice1.topFace() == 5 && dice2.topFace() == 5 && dice3.topFace() == 5) ||
						(dice1.topFace() == 6 && dice2.topFace() == 6 && dice3.topFace() == 6))
				{
					System.out.print("The house wins, you have lost ฿" + money + "\n");
				}
				else
				{
					System.out.print("The player wins\n");
					System.out.print("+฿" + money + "\n");
					money = money * 2;
					playerWallet.put(money);
				}
			}
			if (betType.equals("low"))
			{
				System.out.print(dice1.topFace() + ", " + dice2.topFace() + ", " + dice3.topFace() + "\n");
				if(total >= 11 || (dice1.topFace() == 2 && dice2.topFace() == 2 && dice3.topFace() == 2) || (dice1.topFace() == 3 && dice2.topFace() == 3 && dice3.topFace() == 3) ||
						(dice1.topFace() == 1 && dice2.topFace() == 1 && dice3.topFace() == 1))
				{
					System.out.print("The house wins, you have lost ฿" + money + "\n");
				}
				else
				{
					System.out.print("The player wins\n");
					System.out.print("+฿" + money + "\n");
					money = money * 2;
					playerWallet.put(money);
				}
			}
		}
	}

	public static void main(String[] args) {
		boolean quit = false;
		System.out.print("Enter amount of money in wallet: ");
		double money = input.nextDouble();
		double intialMoney = money;
		Wallet playerWallet = new Wallet();
		playerWallet.put(money);
		do
		{
			System.out.print("Enter a bet (triple, field, high, low) or enter 'quit': ");
			if (input.hasNext("quit"))
			{
				quit = true;
			}
			else if(input.hasNext())
			{
				String betType = input.next();
				resolveBet(money, betType, playerWallet);
				money = playerWallet.check();
			}
			if(playerWallet.check() == 0)
			{
				System.out.print("You are broke.\n");
				quit = true;
			}

		} while (!quit);
		System.out.printf("Starting money: ฿" + intialMoney);
		System.out.printf("\nEnding money: ฿" + playerWallet.check());



	}

}
