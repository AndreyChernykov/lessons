# lessons

package laboratory_work_1;

public class Main {
	static int a, b, x, u;
	static int iTask = 0;// счёт примеров
	static int iVar = 1;// счёт вариантов
	final static double E = 2.71828;
	final static double Pi = Math.PI;
	public static void main(String []args) {
		
		String taskStr;
		double result;//вычисляемый результат
		
		a = rand(1, 100);//формируем a в пределах [1; 100]
		b = rand(a, 100);//формируем b в пределах [a; 100]
		u = rand(1, 100);//формируем u в пределах [1; 100]
		do {//входит в пределы присваиваем его x, если нет крутим рандом снова
			x = rand(1, 100);//формируем x в пределах [1; 100]
		}while(x > a && x < b);
		System.out.println("LABORATORY WORK 1");
		System.out.println();
		System.out.println("x = " + x + "\n" + "u = " + u  + "\n" + "e = " + E + "\n" + "Pi = " + Pi);
		
		Var1 var1 = new Var1();//создаём объект класса первого варианта
		Var2 var2 = new Var2();//создаём объект класса второго варианта
		Var3 var3 = new Var3();//создаём объект класса третьего варианта
		
		result = var1.task1(x, u);// первый вариант 1 пример
		taskStr = "log(x + u/(5 * x))";
		print(taskStr, result);
		
		result = var1.task2(x);// первый вариант 2 пример
		taskStr = "pow(x, 4) * sin(x)";
		print(taskStr, result);
		
		result = var1.task3(x, E);// первый вариант 3 пример
		taskStr = "cos(x + log(x)) + pow(E, x)";
		print(taskStr, result);
		
		result = var1.task4(x, u);// первый вариант 4 пример
		taskStr = "3 + pow(x + u, 1.0/4)";
		print(taskStr, result);
		
		result = var1.task5(x, Pi);// первый вариант 5 пример
		taskStr = "log(pow(cos(Pi * x), 2))";
		print(taskStr, result);
		
		result = var2.task1(E, u, x);// второй вариант 1 пример
		taskStr = "pow(E, -x) /( x - 10 * u)";
		print(taskStr, result);
		
		result = var2.task2(u, x);// второй вариант 2 пример
		taskStr = "x * [x + u]";
		print(taskStr, result);
		
		result = var2.task3(u, x);// второй вариант 3 пример
		taskStr = "(x + u) / pow(x + 25, 2)";
		print(taskStr, result);
		
		result = var2.task4(u, x);// второй вариант 4 пример
		taskStr = "sqrt(u - pow(x, 2))";
		print(taskStr, result);
		if(u - Math.pow(x, 2) < 0) {// проверяем положительное ли число
			System.out.println("ОШИБКА! " + "u - pow(x, 2)" + " < " + 0 + "\n" + "Корень из отридцательного числа ");
		}
		
		result = var2.task5(x);// второй вариант 5 пример
		taskStr = "pow(x, 3) + pow(x, 2) - 15";
		print(taskStr, result);
		
		result = var3.task1(Pi, x, u);// третий вариант 1 пример
		taskStr = "tan(Pi * (x + u))";
		print(taskStr, result);
		
		result = var3.task2(x);// третий вариант 2 пример
		taskStr = "x - 1 + 1 / (x - 1)";
		print(taskStr, result);
		
		result = var3.task3(x, u);// третий вариант 3 пример
		taskStr = "log(-u * x + 5)";
		print(taskStr, result);
		if((-u * x + 5) < 0) {// проверяем положительное ли число
			System.out.println("ОШИБКА! " + "-u * x + 5" + " < " + 0 + "\n" + "логарифм из отридцательного числа ");
		}
		
		result = var3.task4(x, u);// третий вариант 4 пример
		taskStr = "pow(x / 5, 1.0/3) - 1 + 1.0/(u * x - 3)";
		print(taskStr, result);
		
		result = var3.task5(x, Pi);// третий вариант 5 пример
		taskStr = "(x + 5.0) / tan(Pi * x)";
		print(taskStr, result);
		
		switch(iVar){
		case 3:
			System.out.println();
			System.out.println("THIS IS THE END!");
		}
	}
	
	static int rand(int sta, int fin) {//рандом
		int rd = (int)(Math.random() * (fin + 1 - sta)) + sta;
		return rd;
	}
	
	static void print(String taskStr, double result) {//вывод на экран: вариант, номер примера, пример и ответ

		switch(iTask){//считаем номер примера и номер варианта
			case 5: 
				iTask = 0;
				iVar++;
			case 0: 
				System.out.println();
				System.out.println("Вариант № " + iVar);
				break;
		}

		iTask++;
		System.out.println(iTask + ") " + taskStr +  " = " + result);
		
	}
}

class Var1{//первый вариант
	
	static double task1(int x, int u) {
		double result = Math.log(x + u/(5 * x));
		return result;
	}
	
	static double task2(int x) {
		double result = Math.pow(x, 4) * Math.sin(x);
		return result;
	}
	
	static double task3(int x, double E) {
		double result = Math.cos(x + Math.log(x)) + Math.pow(E, x);
		return result; 
	}
	
	static double task4(int x, int u) {
		double result = 3 + Math.pow(x + u, 1.0/4);
		return result;
	}
	
	static double task5(int x, double Pi) {
		double result = Math.log(Math.pow(Math.cos(Pi * x), 2));
		return result;
	}
}

class Var2{//второй вариант
	
	static double task1(double E, int u, int x) {
		double result = Math.pow(E, -x) /( x - 10 * u);
		return result;
	}
	
	static double task2(int u, int x) {
		double result = x * Math.abs(x + u);
		return result;
	}
	
	static double task3(int u, int x) {
		double result = (x + u) / Math.pow(x + 25, 2);
		return result;
	}
	
	static double task4(int u, int x) {
		double result = Math.sqrt(u - Math.pow(x, 2));
		return result;
	}
	
	static double task5(int x) {
		double result = Math.pow(x, 3) + Math.pow(x, 2) - 15;
		return result;
	}
}

class Var3{//третий вариант
	
	static double task1(double Pi, int x, int u) {
		double result = Math.tan(Pi * (x + u));
		return result;
	}
	
	static double task2(int x) {
		double result = x - 1 + 1.0/(x - 1);
		return result;
	}
	
	static double task3(int x, int u) {
		double result = Math.log(-u * x + 5);
		return result;
	}
	
	static double task4(int x, int u) {
		double result = Math.pow(x / 5, 1.0/3) - 1 + 1.0/(u * x - 3);
		return result;
	}
	
	static double task5(int x, double Pi) {
		double result = (x + 5.0)/Math.tan(Pi * x);
		return result;
	}
}
