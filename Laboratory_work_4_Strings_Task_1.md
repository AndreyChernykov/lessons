
import java.util.Scanner;

/*
Лабораторная 4, строки, задача 1
Вводится ненормированная строка, у которой могут быть пробелы в начале, в конце и между словами более одного пробела. 
Привести ее к нормированному виду, т.е. удалить все пробелы в начале и конце, а между словами оставить только один пробел.
 */

public class Main {
	
	static String str;
	
	public static void main(String [] args) {
		entString();
		System.out.println("Строка преобразована");
		System.out.println("Удалены лишние пробелы: " + transformString(str));
	}
	
	static void entString() {//получаем строку
		System.out.print("Введите строку: ");
		Scanner scan = new Scanner(System.in);
		str = scan.nextLine();
	}
	
	static String transformString(String str) {//преобразуем строку
		String newStr = "";
		str = str.trim();//убираем пробелы вначале и конце строки
		char [] strArray = str.toCharArray();//делаем из строки массив 
		for(int i = 1; i < strArray.length; i++) {//читаем массив, удаляем лишние пробелы, добавляем в строку всё кроме последнего элемента
			if(strArray[i] == ' ' && strArray[i-1] == ' ') {
				continue;
			}else {
				String temp = Character.toString(strArray[i-1]);
				newStr = newStr.concat(temp);
			}
		}
		str = newStr.concat(Character.toString(strArray[strArray.length-1]));//добавляем последний элемент
		return str;
	}
}
