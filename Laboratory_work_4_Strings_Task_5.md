/*
 Лабораторная работа 4, задача 5.
 Дан массив слов. Заменить последние три символа слов, 
 имеющих выбранную длину на символ "$".
 */

import java.util.Arrays;

public class Main {
	
	static String []myArray = {"Беларусь", "Канада", "Австралия", "Польша", 
			"Германия", "Турция", "Египет", "Израиль", "Россия", "Бельгия"};
	static int wordLength = 6;//длинна слов над которыми будет проводится преобразование 
	static String s = "$";
	public static void main(String []args) {
		
		System.out.println("Массив слов: " + Arrays.toString(myArray));
		transformWord();
		System.out.println("Преобразованый массив слов: " + Arrays.toString(myArray));
	}
	
	static void transformWord() {
		for(int i = 0; i < myArray.length; i++) {
			if(myArray[i].length() == wordLength) {
				myArray[i] = myArray[i].substring(0, 3);
				myArray[i] = myArray[i].concat(s);
				
			}
		}
	}
}
