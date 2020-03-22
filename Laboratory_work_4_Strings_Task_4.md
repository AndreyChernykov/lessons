/*
 Лабораторная работа 4, задача 4.
 Вводится строка. Удалить из нее все пробелы. 
 После этого определить, является ли она палиндромом (перевертышем), 
 т.е. одинаково пишется как с начала, так и с конца.
 */

import java.util.Arrays;
import java.util.Scanner;

public class Main {

	static String str;

	public static void main(String []args) {	
		entStr();
		if(transform()){
			System.out.println(str + " является полиндромом");
		}else {
			System.out.println(str + " не является полиндромом");
		}
	
	}

		static void entStr() {
			System.out.print("Введите строку: ");
			Scanner scanStr = new Scanner(System.in);
			str = scanStr.nextLine();
	}

	static boolean transform() {
		char []strArray = str.toCharArray();
		str = "";
		for(int i = 0; i < strArray.length; i++ ) {
			if(strArray[i] != ' ') {
				str = str.concat(Character.toString(strArray[i]));
			}
		}
		int pol = 0;
		for(int i = 0, j = str.length()-1; i < str.length()/2; i++, j--) {
			if(str.charAt(i) == str.charAt(j)) {
				pol++;
			}else{
				return false;
			}
		}
		return true;
	}

}
