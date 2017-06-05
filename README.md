# java-projects
This is a collection of various projects I've completed in java.
# This project is titled "Test Scores" 

import java.util.*;
public class TestScores {

	public static void main(String[] args) {
		//This program reads an unspecified number of scores and determines how many
		//scores are above or equal to the average and how many scores are below the average.
		int[] scores = new int[30];
		int count = 0;
		int input;
		boolean done = false;
		Scanner console = new Scanner(System.in);
		while (!done) {
			System.out.println("Enter new score or -1 to exit: ");
			input = console.nextInt();
			if (input == -1)
				done = true;
			else {
				scores[count] = input;
				count++;
			}
		}
		scores[count] = -1;
		int average = getAverage(scores, count);
		int aboveAverage = getAbove(scores, average);
		int belowAverage = getBelow(scores, average);
		System.out.println("The number of scores entered is " + count);
		System.out.println("The average scores is " + average);
		System.out.println("The number of scores above or equal to the average is " + aboveAverage);
		System.out.println("The number of scores below the average is " + belowAverage);
	}
	public static int getAverage(int[] scores, int count) {
		int total = 0;
		for (int i = 0; scores[i] >= 0; i++) {
			total += scores[i];
		}
		return total / count;
	}
	public static int getAbove(int[] scores, int average) {
		int count = 0;
		for (int i = 0; scores[i] >= 0; i++) {
			if (scores[i] >= average)
				count++;
		}
		return count;
	}
	public static int getBelow(int[] scores, int average) {
		int count = 0;
		for (int i = 0; scores[i] >= 0; i++) {
			if (scores[i] < average)
				count++;
		}
		return count;
	}
}
