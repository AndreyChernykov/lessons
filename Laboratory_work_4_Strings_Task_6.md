/*
 Лабораторная работа 4, задача 6.
Дано слово. Заменить в слове все маленькие латинские буквы от ‘a’ до ‘y’
 на следующие по алфавиту (для слова “abc2=zx0” получаем “bcd2=zy0”).
 */

import java.util.Arrays;
import java.util.Scanner;

public class Main {
	static String word;
	public static void main(String []args) {
		entWord();
		System.out.println(transWord());
	}
	
	static String entWord() {
		System.out.print("Введите слово ");
		Scanner scan = new Scanner(System.in);
		word = scan.next();
		return word;
	}
	
	static String transWord() {
		char [] wordArr = word.toCharArray();
		for(int i = 0; i < wordArr.length; i++) {
			if(wordArr[i] > 96 && wordArr[i] < 121) {
				wordArr[i] = (char) (wordArr[i]+1);			
			}
		}
		word = word.copyValueOf(wordArr);
		return word;
	}
}
