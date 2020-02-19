import java.lang.reflect.Array;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.Scanner;

//Лабораторная работа 2, двумерные массивы, задача 2

/* Сформировать вектор В из элементов матрицы, меньших заданного числа k 
  и находящихся в нечетных столбцах. Отсортировать вектор В по возрастанию.*/

public class Main {
	
	private static int myArray[][] = new int[6][6];
	private static ArrayList<Integer>myVector = new ArrayList<>();
	private static int num;
	public static void main(String [] args) {
		
		System.out.println("Лабораторная работа 2, двумерные массивы, задача 2");
		
		random();
		print();	
		entNum();
		vectorArray();
		vectorPrint();
		sort();
		vectorPrint();
	}
	
	static void random() {//крутим рандом заполняем массив
		for(int i = 0; i < myArray.length; i++) {
			for(int j = 0; j < myArray[i].length; j++) {
				myArray[i][j] = (int)(Math.random() * 201) - 100;
			}
		}
	}
	
	static void print() {//выводим на экран массив
		for(int i = 0; i < myArray.length; i++) {
			System.out.println();
			for(int j = 0; j < myArray[i].length; j++) {
				System.out.print(myArray[i][j] + "  ");
			}
		}
		System.out.println();
	}
	
	static int entNum() {//принимаем число, по которому будет построен вектор
		System.out.print("Введите целое число от - 99 до 99 ");
		Scanner scan = new Scanner(System.in);
		if(scan.hasNextInt()) {
			num = scan.nextInt();
			if(num < -99 || num > 99) {
				System.out.println(num + " не входит в диапазон от - 99 до 99 ");
				entNum();
				}
			}else {
				String strNum = scan.nextLine();
				System.out.println("\"" + strNum + "\"" + " не является целым числом");
				entNum();
		}
		return num;
	}
	
	static void vectorArray() {//Формируем вектор из элементов матрицы, меньших num и находящихся в нечетных столбцах
		System.out.println("Формируем вектор из элементов матрицы, меньших " + num + " и находящихся в нечетных столбцах");
		for(int i = 0; i < myArray.length; i++) {
			for(int j = 1; j < myArray[i].length; j+=2) {
				if(myArray[i][j] < num) {
					myVector.add(myArray[i][j]);
				}
			}
		}
	}
	
	static void sort() {//Сортируем вектор
		System.out.println();
		System.out.println("Сортируем вектор");
		boolean inter = true;
		while(inter) {
			inter = false;
			for(int i = 1; i < myVector.size(); i++) {
				if(myVector.get(i) < myVector.get(i-1)) {
					int temp = myVector.get(i);
					myVector.set(i, myVector.get(i-1));
					myVector.set(i-1, temp);
					inter = true;
				}
			}
		}
	}
	
	static void vectorPrint() {//выводим вектор на печать
		for(int i : myVector) {
			System.out.print(i + " ");
		}
	}
}
