package array;
import java.io.*;
import java.util.*;
public class Array {

	public static void main(String[] args) throws FileNotFoundException {
		Scanner input = new Scanner(new File("student.txt"));
		PrintStream out = new PrintStream(new File("output.txt"));
		Scanner sc = new Scanner(System.in);
		String correct = "false";
		System.out.println("Input gender (f/m):");
		String userg = sc.next();
		do{
		if (userg.equals("f")) {
			System.out.println("List of female students");
			correct = "true";
		}
		else if (userg.equals("m")) {
			System.out.println("List of male students");
			correct = "true";
		}
		else {
			System.out.println("Invalid input");
			correct = "false";
		}
		}while (correct=="false");
		System.out.println("id name age");
		System.out.println("-----------");
		int i = 0;
		int i2 =0;
		int average = 0;
		String[] genders = new String[6];
		int[] ages = new int[6];
		int[] nums = new int[6];
		String[] names = new String[6];
		int n=0;
		int n2=0;
		int avg=0;
		int trueavg=0;
		int avg2=0;
		int trueavg2=0;
		while (input.hasNext() && userg.equals("f")) {
			int num = input.nextInt();
			String name = input.next();
			String gender = input.next();
			int age = input.nextInt();
			i=i+1;
			for (int a=1; a<=6; a++) {
				int b=a-1;
				if (i==a){genders[b]=gender;ages[b]=age;names[b]=name; nums[b]=num;
				if (genders[b].equals("f")){System.out.println(nums[b] + " " + names[b] + " " + ages[b]); 
				n = n+1; 
				avg=avg+age;
				}
				if (i==6) {System.out.println("There are " + n + " female students"); trueavg=avg/n;
				System.out.println("The average age of female students is " + trueavg);}
				}
			}
		}
		while (input.hasNext() && userg.equals("m")) {
			int num = input.nextInt();
			String name = input.next();
			String gender = input.next();
			int age = input.nextInt();
			i=i+1;
			for (int a=1; a<=6; a++) {
				int b=a-1;
				if (i==a){genders[b]=gender;ages[b]=age;names[b]=name; nums[b]=num;
				if (genders[b].equals("m")){System.out.println(nums[b] + " " + names[b] + " " + ages[b]); 
				n = n+1; 
				avg=avg+age;
				}
				if (i==6) {System.out.println("There are " + n + " male students"); trueavg=avg/n;
				System.out.println("The average age of male students is " + trueavg);}
	}
			}
		}
	}
}
		
