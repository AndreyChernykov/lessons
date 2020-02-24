import java.util.ArrayList;
import java.util.Scanner;

/*
Лабораторная 4, строки, задача 10
Дан текст. Найти сумму имеющихся в нем цифр.
 */

public class Main {	
	
	static String str;
	static ArrayList<String> numsArr = new ArrayList<>();
	
	public static void main(String [] args) {
		entText();
		System.out.println("Сумма всех чисел в строке составляет " + numsInText());
	}
	
	static void entText() {//читаем введенную строку
		System.out.print("Введите текст с числами ");
		Scanner scan = new Scanner(System.in);
		str = scan.nextLine();
		str = str.concat("n");//добавляем вконце символ, для прочтения последних символов
	}  
	
	static int numsInText() {//читаем текст и добавляем числа в лист 
		String tempStr = "";
		int sumNum = 0;
		for(int i = 0; i < str.length(); i++) {	
			if(str.charAt(i) > 47 && str.charAt(i) < 60) {
				tempStr = tempStr.concat(Character.toString(str.charAt(i)));		
			}else if(str.charAt(i) < 47 || str.charAt(i) > 60){		
				numsArr.add(tempStr);
				tempStr = "";
			}
		}
	
		for(int i = 0; i < numsArr.size(); i++) {//считаем сумму всех чисел в листе
			if(numsArr.get(i) != "") {
				sumNum += Integer.parseInt(numsArr.get(i));
			}
		}
		return sumNum;
	}
}
