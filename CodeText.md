// Prime Factorization - Have the user enter a number and find all 
// Prime Factors (if there are any) and display them.

import java.util.Scanner;

public class PrimeFactorization {
	
	//end recursion if all factors discovered
	public static boolean done = false;

	public static void findPrimes(int number)
	{		
		for(int i = 2; i <= number; i++)
		{
			// if i reaches number, there are no more factors
			if (i == number && done == false)
			{
				System.out.println(number);
				done = true;
			}
			// discover and print factors
			else if(number % i == 0 && done == false)
			{
				System.out.println(i);
				
				// divide number by discovered factor, repeat
				number = number/i;
				findPrimes(number);
			}	
		}	
	}
	
	public static void main(String[] args) 
	{
		System.out.println("Number to factorize:");		
		Scanner scanner = new Scanner(System.in);
		final int x = Integer.parseInt(scanner.nextLine());
		
		findPrimes(x);
	}
}
