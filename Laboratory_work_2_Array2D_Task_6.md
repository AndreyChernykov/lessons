import java.util.Arrays;
import java.util.Collections;

//Лабораторная работа 2, двумерные массивы, задача 6
//Заменить все элементы матрицы на противоположные по знаку, а затем поменять местами первый и 
//последний столбец матрицы. Отсортировать последнюю строку матрицы по убыванию.

public class Main {
	
	private static Integer myArray[][] = new Integer[5][6];
	private static int result;
	public static void main(String [] args) {
		
		System.out.println("Лабораторная работа 2, двумерные массивы, задача 6");
		
		random();
		print();	
		
		negativeArray();
		System.out.println("Меняем все элементы матрицы на противоположные по знаку");
		print();
		
		
		columns();
		System.out.println("Меняем местами первый и последний столбец матрицы");
		print();
		
		sortArray();
		
		System.out.println("Сортируем последнюю строку матрицы по убыванию");
		print();

	}
	
	static void random() {//крутим рандом заполняем массив
		for(int i = 0; i < myArray.length; i++) {
			for(int j = 0; j < myArray[i].length; j++) {
				myArray[i][j] = (int)(Math.random() * 41) - 20;
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
	
	static void negativeArray() {//меняем все элементы матрицы на противоположные по знаку
		for(int i = 0; i < myArray.length; i++) {
			for(int j = 0; j < myArray[i].length; j++) {
				myArray[i][j] = myArray[i][j] - myArray[i][j] * 2;
			}
		}
		System.out.println();
	}
	
	static void columns() {//Меняем местами первый и последний столбец матрицы
		for(int i = 0; i < myArray.length; i++) {
			int temp = myArray[i][0];
			myArray[i][0] = myArray[i][myArray.length];
			myArray[i][myArray.length] = temp;
		}
		System.out.println();
	}
	
	static void sortArray() {//Сортируем последнюю строку матрицы по убыванию
		Arrays.sort(myArray[myArray.length-1], Collections.reverseOrder());
		System.out.println();
	}
}
