/*
 Лабораторная работа 4, задача 7.
Дана строка. Если она начинается на 'abc', то заменить их на 'www', 
иначе добавить в конец строки 'zzz'
 */

import java.util.Scanner;

public class Main {
	static String str;
	public static void main(String []args) {
		entStr();
		System.out.println(transString());
	}
	
	static String entStr() {
		System.out.print("Введите строку ");
		Scanner scanStr = new Scanner(System.in);
		str = scanStr.nextLine();
		return str;
	}
	
	static String transString() {
		if(str.indexOf("abc") == 0) {
			str = str.replace("abc", "www");
		}else {
			str = str.concat("zzz");
		}
		return str;
	}
}
