/*
 Лабораторная 2, двумерные массивы, задача 3
 Получить вектор путем поэлементного умножения строки и столбца матрицы, где находится её максимальный элемент. 
 Отсортировать вектор по убыванию.
 */

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Scanner;

public class Main {
	
	static int [][]array = new int [6][6];
	static int []vector = new int[6];
	static int max = 0;
	static int strMax;
	static int colMax;
	
	public static void main(String [] args) {
		
		random();
		print();
		vectorPrint();
		sortVector();
	}
	
	static void random() {//крутим рандом, заполняем матрицу
		for(int i = 0; i < array.length; i++) {
			for(int j = 0; j < array[i].length; j++) {
				array[i][j] = (int)(Math.random() * 50)+1;
			}
		}
	}
	
	static void print() {// выводим на печать и ищем самый большой элемент
		for(int i = 0; i < array.length; i++) {
			System.out.println();
			for(int j = 0; j < array[i].length; j++) {
				if(array[i][j] < 10) {
					System.out.print(" " + array[i][j] + "  ");
				} else {
					System.out.print(array[i][j] + "  ");
				}
				if(array[i][j] > max) {
					max = array[i][j];
					strMax = i;//array[i][array.length-1];
					colMax = j;//array[array.length-1][j];
				}
			}
		}
		System.out.println();
		System.out.println("Самый большой элемент массива: " + max + " строка: " + strMax + " столбец: " + colMax);
	}
	
	static void vectorPrint() {//вычисляем вектор
		System.out.print("Вектор ");
		for(int i = 0; i < vector.length; i++) {
			vector[i] = array[strMax][i] * array[i][colMax];
			System.out.print(vector[i] + " ");
		}
	}
	static void sortVector() {//сортируем вектор выбором
		for(int i = 0; i < vector.length; i++) {
			int temp = i;
			for(int j = i; j < vector.length; j++) {
				if(vector[j] > vector[temp]) {
					temp = j;
				}
			}
			int temp2 = vector[i];
			vector[i] = vector[temp];
			vector[temp] = temp2;
		}
		System.out.println();
		System.out.println("Сортируем вектор по убыванию");
		System.out.println(Arrays.toString(vector));
	}
}
