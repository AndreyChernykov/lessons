# lessons

//Laboratory_work_2_Array_Task_7
import java.util.Arrays;

public class Main {

	static int []array = new int[10]; 
	static int randNum;
	static int numMin;
	static int numMax;
	static int indexNumMax;
	static int indexNumMin;
	static long result = 1;
	public static void main(String [] args) {
		rand();
		numMax();
		numMin();
		System.out.println("массив "  + Arrays.toString(array));
		System.out.println("индекс первого по порядку минимального элемента " + indexNumMin + "  значение минимального элемента " + numMin);
		System.out.println("индекс последнего по порядку максимального элемента " + indexNumMax + "  значение максимального элемента " + numMax);
		product();
		System.out.println("Произведение элеменнтов находящихся между " + indexNumMin + " и " + indexNumMax + " элементами массива составляет " + result);
		
	}
	
	static int rand() {
		for(int i = 0; i < array.length; i++) {
			randNum = (int) (Math.random() * 100) + 1;
			array[i] = randNum;
		}
		return randNum;
	}
	
	static int numMax() {
		numMax = array[0];
		for(int i = 0; i < array.length; i++) {
			if(array[i] >= numMax) {
				numMax = array[i];
				indexNumMax = i;
			}
		}
		return numMax;
	}
	static int numMin() {
		numMin = array[0];
		for(int i = 0; i < array.length; i++) {
			if(array[i] < numMin) {
				numMin = array[i];
				indexNumMin = i;
			}
		}
		return numMin;
	}
	static long product() {
		if(indexNumMin+1 == indexNumMax || indexNumMin-1 == indexNumMax) {
			result = 0;
		}else {
			if(indexNumMin < indexNumMax) {
				for(int i = indexNumMin+1; i < indexNumMax; i++) {
					result *= array[i]; 
				}
			} else {
				for(int i = indexNumMax+1; i < indexNumMin; i++) {
					result *= array[i]; 
				}
			}
		}


		return result;
	}
}
