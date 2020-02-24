/*
Лабораторная работа 4, задача 8.
Дана строка. Разделить строку на фрагменты по три подряд идущих символа. 
В каждом фрагменте средний символ заменить на случайный символ, 
не совпадающий ни с одним из символов этого фрагмента. 
Показать фрагменты, упорядоченные по алфавиту.
 */

import java.util.Scanner;

public class Main {

	static String str;
	static char [][]strArr;
	public static void main(String []args) {
		
		entStr();
		strToArr();
		random();
		printAbc();		
	}
	
	static String entStr() {
		System.out.print("Введите строку латинских символов ");
		Scanner scanStr = new Scanner(System.in);
		str = scanStr.nextLine();
		while(str.length() % 3 != 0) {//добавляем пробелы в конце строки, если она не кратна 3м
			str = str.concat(" ");
		}
		for(int i = 0; i < str.length(); i++) {//проверяем состоит ли строка только из лат символов
			if(str.charAt(i) > 122 || str.charAt(i) < 97) {
				System.out.println("Строка должна содержать только латинские символы");
				entStr();
			}
		}
		return str;
	}
	
	static void strToArr() {
		int k = 0;
		strArr = new char[str.length()/3][3];
		System.out.println("Делим строку на фрагменты по три символа");
		for(int i = 0; i < strArr.length; i++) {
			for(int j = 0; j < strArr[i].length; j++) {
				strArr[i][j] = str.charAt(k);
				System.out.print(strArr[i][j]);
				k++;
			}
			System.out.println();
		}
	}
	
	static void random() {
		char rand;
		System.out.println("Меняем каждый второй символ");

		for(int i = 0; i < strArr.length; i++) {//меняем второй символ, кроме пробелов, в тройках на рандомную литинскую букву
			if(strArr[i][1] != ' ') {
				do{
					rand = (char) ((char)(Math.random() * (123-97)) +97);
					strArr[i][1] = rand;
				}while(strArr[i][0] == rand && strArr[i][1] == rand && strArr[i][2] == rand);
			}	
		}
		for(int i = 0; i < strArr.length; i++) {
			for(int j = 0; j < strArr[i].length; j++) {
				System.out.print(strArr[i][j]);
			}
			System.out.println();
		}
	}
	
	static void printAbc() {//Выводим фрагменты упорядоченые по алфавиту 
		System.out.println("Фрагменты упорядоченые по алфавиту");
		boolean abc = false;
		for(int i = 0; i < strArr.length; i++) {
			if(strArr[i][0] < strArr[i][1] && strArr[i][1] < strArr[i][2]) {
				System.out.println(strArr[i][0] + "" + strArr[i][1] + "" + strArr[i][2]);
				abc = true;
			}
		}
		if(abc == false) {
			System.out.println("Фрагментов упорядоченых по алфавиту не обнаружено");
		}
	}
}
