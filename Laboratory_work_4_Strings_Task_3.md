
import java.util.ArrayList;
import java.util.Scanner;

/*
Лабораторная 4, строки, задача 3
Вводится строка. Требуется удалить из нее повторяющиеся символы и все пробелы. 
Например, если было введено "abc cde def", то должно быть выведено "abcdef"
 */

public class Main {	

	static String str;
	public static void main(String [] args) {
		
		entrStr();
		result();
	}
	
	static String entrStr() {
		System.out.print("Введите строку: ");
		Scanner scanStr = new Scanner(System.in);
		str = scanStr.nextLine();
		return str;
	}
	
	static void result() {
		System.out.print("Удаляем повторяющиеся элементы и пробелы: ");
		char [] strArray = str.toCharArray();
		str = "";
		ArrayList<Character>strList = new ArrayList<>();
		for(int i = 0; i < strArray.length; i++) {
			if(strList.indexOf(strArray[i]) == -1 && strArray[i] != ' ') {
				strList.add(strArray[i]);
				str = str.concat(Character.toString(strArray[i]));
			}
		}
		System.out.println(str);
	}
}
