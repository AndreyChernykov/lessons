import java.util.Arrays;

public class Main {
	static int []array = new int[10]; 
	static int negNum;
	static int posNum;
	
	public static void main(String [] args) {
		random();
		System.out.println(Arrays.toString(array));
		nums();
		System.out.println("самое маленькое из положительных чисел массива " + posNum );
		System.out.println("самое большое из отридцательных чисел массива " + negNum );
		
		for(int i = 0; i < array.length; i++) {
			if(array[i] == negNum) {
				array[i] = posNum;
			}else if(array[i] == posNum) {
				array[i] = negNum;
			}
		}
		System.out.println(Arrays.toString(array));
	}
	
	static void random() {
		for(int i = 0; i < array.length; i++) {
			array[i] = (int) (Math.random() * (41))-20;
		}
	}
	static void nums() {


		for(int i = 0; i < array.length; i++) {
			if(array[i] > 0) {
				posNum = array[i];
			}
			if(array[i] < 0) {
				negNum = array[i];
			}
		}
		
		for(int i = 0; i < array.length; i++) {
			if(array[i] > 0 && array[i] < posNum) {
				posNum = array[i];

			}
			if(array[i] < 0 && array[i] > negNum) {
				negNum = array[i];
			}	
		}
	}
	
}
