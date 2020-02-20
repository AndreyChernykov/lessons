import java.util.Scanner;

/*
Лабораторная 4, строки, задача 2
Найти в строке указанную подстроку и заменить ее на новую. 
Строку, ее подстроку для замены и новую подстроку вводит пользователь.
 */

public class Main {	
	
	static String str = "", subStr = "", newSubStr = "";
	
	public static void main(String [] args) {
		
		String str = entString("");
		String subStr = entString("заменяемую под");
		String newSubStr = entString("новую под");
		conversString(str, subStr, newSubStr);
		
	}
	
	static String entString(String s) {//принимаем строку, подстроку, новую подстроку 
		System.out.print("введите " + s + "строку: ");
		Scanner scan = new Scanner(System.in);
		String str = scan.nextLine();	
		return str;
		
	}
	
	static void conversString(String str, String subStr, String newSubStr) {//заменяем подстроку на новую подстроку
		int inStr = str.indexOf(subStr);
		if(inStr == -1) {
			System.out.println("\""+ subStr + "\"" + " в строке: " + str + " не обнаружено");
		}else {
			str = str.replace(subStr, newSubStr);
			System.out.println("измененная строка: " + str);
		}

	}
}
