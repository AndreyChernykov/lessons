
import java.util.Arrays;
import java.util.Scanner;

/*
 Лабораторная 2, массивы, задача 10
Найти сумму элементов массива, таких, что номер элемента кратен заданному числу k и сам элемент кратен k.
 */

public class Main {
	
	static int[]myArray = new int[100];
	static int sum;
	static int num;
	public static void main(String [] args) {
		
		rand();
		System.out.println(Arrays.toString(myArray));
		entNum();
		sumNum(num);
	}
	
	static void rand() {
		for(int i  = 0; i < myArray.length; i++) {//крутим рандом от 1 до 100 и заполняем массив
			myArray[i] = (int)(Math.random() * 100) + 1;
		}
	}
	
	static int entNum() {//принимаем и проверяем число
		System.out.print("Введите целое число от 1 до 100  ");
		Scanner scan = new Scanner(System.in);
		if(scan.hasNextInt()) {
			num = scan.nextInt();
			if(num < 1 || num > 100){
				System.out.println("Вы ввели недопустимое значение");
				entNum();
			}
		}else {
			String sNum = scan.nextLine();
			System.out.println(sNum + " не является целым числом");
			entNum();
		}
		return num;
	}
	
	static int sumNum(int num) {//считаем сумму элементов кратных num
		for(int i = 0; i < myArray.length; i++) {
			if(i % num == 0 && myArray[i] % num == 0) {
				sum += myArray[i];
			}
		}
		if(sum == 0) {
			System.out.println("Чисел кратных " + num + " с номером в массиве кратном " + num + " не обнаружено");
		}else {
			System.out.println("Сумма чисел кратных " + num + " с номером в массиве кратном " + num + " составляет " + sum);
		}
		return sum;
	}
}
