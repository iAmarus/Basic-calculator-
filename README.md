import java.util.Scanner;

public class calculator {
	public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	
	
	double number1=0,number2=0;
	double result = 0;
	boolean flag = true;
	int op;
	
	do {
		System.out.println("1 for addition.\n2 for subtraction. \n3 for multiplication. \n4 for division. \n5 for sin. \n6 for Modulus. \n7 for factoial. "
				+ "\n8 for absloute value. \n9 for power. \n10 for square root. \n11 for log. \n12 for average. \n13 for stop");
		
		op = input.nextInt();
	switch(op) {
	case 1 : {
		System.out.println("Please enter number1 :");
		number1 = input.nextDouble();
		System.out.println("Please enter number2 :");
		number2 = input.nextDouble();
		result = addition(number1,number2);
		System.out.println("result = "+result);
		break;
	}
	case 2 :{
		System.out.println("Please enter number1 :");
		number1 = input.nextDouble();
		System.out.println("Please enter number2 :");
		number2 = input.nextDouble();
		result = subtraction(number1,number2);
		System.out.println("result = "+result);
		break;
	}
	case 3 :{
		System.out.println("Please enter number1 :");
		number1 = input.nextDouble();
		System.out.println("Please enter number2 :");
		number2 = input.nextDouble();
		result = multiplication(number1,number2);
		System.out.println("result = "+result);
		break;
	}
	case 4 :{
		System.out.println("Please enter number1 :");
		number1 = input.nextDouble();
		System.out.println("Please enter number2 :");
		number2 = input.nextDouble();
		if(number2==0) {System.out.println("wrong number, please enter a postive number");}
		else {result = division(number1,number2);}
		System.out.println("result = "+result);
		break;
	}
	case 5 :{
		System.out.println("Please enter number :");
		number1 = input.nextDouble();
		result = sin(number1);
		System.out.println("result = "+result);
		break;
	}
	case 6 :{
		System.out.println("Please enter number1 :");
		number1 = input.nextDouble();
		System.out.println("Please enter number2 :");
		number2 = input.nextDouble();
        result = remainder(number1,number2);
        System.out.println("result = "+result);
		break;
	}
	case 7 :{
		System.out.println("Please enter number :");
		number1 = input.nextDouble();
		if(number1>=0) {result = factorial(number1);}
		else if(number1 < 0) {System.out.println("Wrong number, please enter a postive number");}
		break;
	}
	case 8:{
		System.out.println("Please enter number :");
		number1 = input.nextDouble();
		result = abslouteValue(number1);
		System.out.println("result = "+result);
		break;
	}
	case 9 :{
		System.out.println("Please enter number1 :");
		number1 = input.nextDouble();
		System.out.println("Please enter number2 :");
		number2 = input.nextDouble();
		result = power(number1,number2);
        System.out.println("result = "+result);
		break;
	}
	case 10 :{
		System.out.println("Please enter number :");
		number1 = input.nextDouble();
		if(number1 < 0) {System.out.println("Wrong number, please enter a postive number");}
		else  {result = squareRoot(number1);
		System.out.println("result = "+result);
		}
		break;
	}
	case 11 :{
		System.out.println("Please enter base :");
		number1 = input.nextDouble();
		System.out.println("Please enter number :");
		number2 = input.nextDouble();
		result = log(number1,number2);
		System.out.println("result = "+result);
	break;
	}
	case 12 :{
		System.out.print("Enter how many number would you like to average: ");
		int n1 = input.nextInt();
		double [] array = new double[n1];
		for(int i=0;i<array.length;i++) {
			System.out.printf("Enter the #%d number:", (1 + i));
			array[i]= input.nextDouble();
		}
		result = avg(array);
		System.out.println("result = "+result);
		break;
	}
	case 13:{
		System.out.println();
		
	}
	
	default :{
    	System.out.println("System stop!!");
    	flag = false;
	}
	}
	}while(op!=13);
	
	
        
	
	}
	public static double addition(double number1,double number2) {
		return number1 + number2;
	}
	public static double subtraction(double number1,double number2) {
		return number1 - number2;
	}
	public static double multiplication(double number1,double number2) {
		return  number1 * number2;
	}
	public static double division(double number1,double number2) {
		return  number1 / number2;
	}
	public static double sin(double number1) {
		
		return  Math.sin(Math.toRadians(number1));
	}
	public static double remainder(double number1,double number2) {
		return  number1 % number2;
	}
	public static double factorial(double number1) {
		int factorial = 0;
		if(number1 == 0) {return 1;}
		else if(number1 != 0) {
			for(int i=0;i<=number1;i++) {
				factorial = factorial * i;
			}
				}
		return factorial;
	}
	public static double abslouteValue(double number1) {
		double abs = Math.abs(number1);
		return number1;
	}
	public static double squareRoot(double number1) {
		double sqart = 0;
		sqart = Math.sqrt(number1);
		return number1;
	}
	public static double log(double base_log, double number2) {
		double log = 0;
		if(base_log==10) {
		log = Math.log10(number2);}
		else if(base_log != 10) {
			log = Math.log(number2) / Math.log(base_log);
		}
		return log;
	}
	public static double power(double number1,double number2) {
		double pow = 0;
		return pow = Math.pow(number1, number2);

	}
	public static double avg(double[] avg) {
		double totalSum = 0;
		for(int i=0;i<avg.length;i++) {
			totalSum += avg[i];
		}
		return (totalSum/avg.length);
	}
	
}
