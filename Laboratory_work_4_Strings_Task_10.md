
import java.util.Scanner;

/*
Лабораторная 4, строки, задача 10
Дан текст. Найти сумму имеющихся в нем цифр.
 */

public class Main {

static int sumNum = 0;
static String str, tempStr = "";

public static void main(String [] args) {

	entText();
	numsInText();
	System.out.println("Сумма всех чисел в строке составляет " + sumNum);
}

static void entText() {//читаем введенную строку

	System.out.print("Введите текст с числами ");
	Scanner scan = new Scanner(System.in);
	str = scan.nextLine();
	str = str.concat(" ");//добавляем вконце символ, для прочтения последних символов
}  

static void numsInText() {//читаем текст и подсчитываем сумму чисел
	
	for(int i = 0; i < str.length(); i++) {
		if(str.charAt(i) > 47 && str.charAt(i) < 60){
			
			tempStr = tempStr.concat(Character.toString(str.charAt(i)));
		}
		if (str.charAt(i) < 47 || str.charAt(i) > 60){
			
			sumNum += Integer.parseInt(tempStr);
			tempStr = "0";
		}
		
	}

}


}
