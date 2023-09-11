# Java_Templates
Шаблоны

## Switch
```
int day = 2;

switch (day) {
    
    case 1:
        System.out.println("Monday");
        break;

    case 2:
        System.out.println("Tuesday");
        break;

    case 3:
        System.out.println("Wednesday");
        break;

    default:
        System.out.println("Wrong day's number");
}
```



## Очерёдность действий в логических выражениях
1. Сначала выполняются действия в круглых скобках.

2. Затем выполняются операции логического отрицания (!)

3. Далее выполняются операции логического И (&&)

4. В последнюю очередь выполняются операции логического ИЛИ (||).

[Таблица истинности](https://ru.wikipedia.org/wiki/Таблица_истинности)

## Инкремент и декремент.
Инкремент ++
Декремент --

Postfix x++ - позже делает.

Prefix ++x  - сейчас делает.

## System.out.printf  или  String.format
**%d**	Задается целое число (int. byte, short, int, long, BigInteger)
```
String.format("Мне уже %d!",20)
```
**%s**	Любой тип, который будет приведен к строке
```
String.format("Привет %s!","мир")
```
[Полная таблица](https://javarush.com/groups/posts/1412-formatiruem-vihvod-chisel-v-java)

## Символьная таблица юников(Unicode)
[юникод](https://en.wikipedia.org/wiki/List_of_Unicode_characters)

## Тернарный оператор

```
int x = 24;

if (x % 2 == 0) {
    System.out.println("Число чётное");
} else {
    System.out.println("Число нечётное");
}
```

тернарный
```
int x = 15;

System.out.println((x % 2 == 0) ? "Число чётное" : "Число нечётное");
```

## Строки
Срез split
```
class Main {
    public static void main(String[] args) {

        String str = "stepik.org";
        System.out.println(delCom(str));
    }
    static String delCom(String str) {
        return str.split("\\.org$")[0];
    }
}
// stepik
```

 **Методы** 
String concat(String s) (аналог «+») — слияние строк;
boolean equals(Object ob) — сравнение строк с учетом регистра;
boolean equalsIgnoreCase(String s) — сравнение строк без учета регистра;
int compareTo(String s) и compareToIgnoreCase(String s) — лексикографическое сравнение строк с учетом и без учета их регистра. Метод осуществляет вычитание кодов первых различных символов вызывающей и передаваемой в метод строки и возвращает целое значение. Метод возвращает значение нуль в случае, когда equals() возвращает значение true;
boolean contentEquals(StringBuffer ob) — сравнение строки и содержимого объекта типа StringBuffer;
String substring(int n, int m) — извлечение из строки подстроки начиная с индекса n и заканчивая индексом m (не включая). Нумерация символов в строке начинается с нуля;
String substring(int n) — извлечение из строки подстроки, начиная с позиции n до конца строки;
int length() — определение длины строки;
int indexOf(char ch)— определение позиции символа  в строке. Возвращает индекс первого появления символа, либо -1, если символ не обнаружен. Аналогично перегруженный метод int indexOf(String str)  поиска индекса начала подстроки str.
int indexOf(char ch, int n), int indexOf(String str, int n) — определение позиции символа  или подстроки, поиск вправо начинается с позиции n. Возвращает -1, если символ/подстрока не обнаружен;
int lastIndexOf(char ch), int lastIndexOf(String str) — определение последней позиции символа или подстроки. Возвращает -1, если символ/подстрока не обнаружен;
int lastIndexOf(char ch, int n), int lastIndexOf(String str, int n) — определение позиции символа  или подстроки, поиск влево начинается с позиции n. Возвращает -1, если символ/подстрока не обнаружен;
String toUpperCase()/toLowerCase() — преобразование всех символов вызывающей строки в верхний/нижний регистр;
String replace(char с1, char с2) — замена в строке всех вхождений первого символа вторым символом. Есть перегрузка этого метода для замены одной подстроки другой:: String replace(String str1, String str2)
String intern() — заносит строку в «пул» литералов и возвращает ее объектную ссылку. Пример использования этого метода показан далее.
String trim() — удаление всех пробелов в начале и конце строки;
char charAt(int position) — возвращение символа из указанной позиции (нумерация с нуля);
boolean isEmpty() — возвращает true, если длина строки равна 0 (пустая строка);
void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin) — извлечение символов строки от символа с индексом srcBegin до символа с индексом srcEnd  (не включая) в массив символов dst , размещение в котором начинается с индекса dstBegin;
String[] split(String regex) — поиск вхождения в строку заданного регулярного выражения (разделителя) и деление исходной строки в соответствии с этим на массив строк.
String[] split(String regex, int limit) — деление исходной строки на массив строк, используя разделитель regex (регулярное выражение). Параметр limit означает максимальное количество строк, которое должно быть получено.
Поскольку литерал является объектом класса String, от его имени можно вызывать все эти методы. 

System.out.println("abc".length()); //будет выведено 3
**Примеры вызовов**
```
import java.util.Scanner;
public class Runner10 {
    public static void main(String[] args) {
        String sample="   Testing strings   ";
        sample = sample.trim(); //удаление пробелов в начале и в конце
        System.out.println("|"+sample+"|");
        System.out.println(sample.charAt(3)); //символ с индексом 3 - это t
        System.out.println(sample.charAt(sample.length() - 1)); //последний символ - это s
        String sub = sample.substring(3, 7); //выделение подстроки ting
        System.out.println(sub);
        String changed = sample.replace('s', 'z'); //замена символов s на z
        System.out.println(changed);
        changed = changed.replace("z", ""); //удаление символов z
        System.out.println(changed);
        int findFirst = sample.indexOf('i'); //поиск символа с начала строки
        System.out.println(findFirst); //выводит 4
        int findLast = sample.lastIndexOf('i'); //поиск символа с конца строки
        System.out.println(findLast); //выводит 11
    }
}
```
**Сравнение строк**
```
public class Example2 {
    public static void main(String[] args) {
        String s1 = "Ivan";
        String s2 = "Ivan";
        String s3 = new String("Ivan");
        String s4 = new String(s1);
        System.out.println(s1 == s2); // true
        System.out.println(s3 == s4); // false
        System.out.println(s1 == s3); // false
        System.out.println(s1.equals(s2)); //true
        System.out.println(s1.equals(s3)); // true
    }
}
```

## Массивы

### Одномерные
int a[]; //синтаксис пришел из С
//можно и так:
int[] a;  //предпочтительный синтаксис

a = new int[5]; //массив из 5 элементов

int[] a = new int[5];

int[] b = new int[]{3, 6, 7}; //массив из 3-х элементов
int[] mas = new int[3]{3, 2, 1}; // ошибка компиляции!!!
double[] c = {0.5, 3.3, 2.7, 1.5}; //массив из 4-х элементов типа double

for(int i = 0; i < b.length; i++){
    System.out.print(b[i] + " ");
}

for(int el:b){
     System.out.print(el + " "); //el - это очередной элемент в массиве
}

Scanner scan = new Scanner(System.in);
int[] mas = new int[scan.nextInt()]; //Ввод количества элементов и создание массива
for(int i = 0; i < mas.length; i++){
    mas[i] = scan.nextInt(); //ввод очередного элемента массива
}


```
import java.util.Arrays;
import java.util.Random;
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int gen = sc.nextInt();
// Создание массива, рандом числами и вывод в консоль

        Random r = new Random(gen);
        int[] a = new int[n];
        for (int i = 0; i <a.length ; i++) {
            a[i] = r.nextInt(-10,11);
            System.out.print(a[i]+ " ");
        }
        System.out.println();
        // Сумма элементов массива

        int sun = 0;
        for (int el: a){
            sun+=el;
        }
        System.out.println("Cумма равна:"+sun);
        // Подсчет количества элементов в массиве, удовлетворяющих некоторому условию
        
        int kol = 0;
        for (int el: a){
            if(el == 0 ){
                kol++;
            }
        }

        System.out.println("Колличество нулей: "+kol);

        // Перебор элементов с четными (нечетными) индексами
        // 1 вар
        /*   double p = 1;
        for (int i = 0; i <a.length ; i++) {
            if(i%2!=0){
                p *= a[i];
            }
        }
        System.out.println("Произведения с нечет индексами "+p);
*/
        double p = 1;
        for (int i = 1; i <a.length ; i+=2) {
                p *= a[i];
        }
        System.out.printf("Произведения с нечет индексами %.2f",p);
        // Поиск максимального значения в массиве
        int max = a[0];
        int imax = 0;
        for (int i = 0; i <a.length ; i++) {
            if (a[i]>=max){
                max = a[i];
                imax = i;
            }
        }
        System.out.println("\nМаксимум = "+max+"\nА его индек "+ imax);

    }
}

```

### Двумерные массивы

int[][] a = new int[3][4]; // создается массив из 3 строк и 4 столбцов

 a[2][1] = 3; // запись значения в строку 2 столбец 1 массива

int[][] array = {{3,5},{6,7},{9,10}};
int[][] ar = new int[][]{{1,2,3},{4,5,6},{7,8,9}};

public class Example5 {
    public static void main(String[] args) {
        Random rand = new Random();
        int[][] a = new int[3][4];
        for (int i = 0; i < a.length; i++){ //a.length - количество строк
            for (int j = 0; j < a[i].length; j++) { //a[i].length - размер i-й строки
                a[i][j] = rand.nextInt(-10, 11);
                System.out.print(a[i][j] + "\t");
            }
            System.out.println();
        }
    }
}

int[][] b = new int[3][]; //создается массив из 3 х массивов
b[0] = new int [2]; //первая строка из 2 х элементов
b[1] = new int [4]; //вторая строка из 4 х элементов
b[2] = new int [3]; //третья строка из 3 х элементов
//все элементы по умолчанию инициализируются нулями
for (int i = 0; i < b.length; i++){ //b.length равно 3
    for (int j = 0; j < b[i].length; j++) { //b[i].length - длина текущей строки
          System.out.print(b[i][j] + "\t");
    }
    System.out.println();
}
 В результате на консоли мы увидим:

0    0    
0    0    0    0    
0    0    0 

**Пример**. Пользователь вводит количество строк и столбцов двумерного массива, а затем начальное значение генератора случайных чисел. Создать целочисленный массив указанной размерности и инициализировать его случайными числами от 0 до 20. Массив вывести на консоль в виде таблицы, элементы которой отделяются знаками табуляции. 

Найти среднее арифметическое элементов массива и подсчитать количество элементов, меньших этого среднего. Вывести с новой строки среднее арифметическое (округленное до 2-х знаков после десятичной точки) и, через пробел, найденное количество.
```
import java.util.Random;
import java.util.Scanner;

public class Example6 {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int[][] array = new int[scan.nextInt()][scan.nextInt()];
        Random rand = new Random(scan.nextLong());
        double average = 0;
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                array[i][j] = rand.nextInt(21);
                System.out.print(array[i][j] + "\t");
                average += array[i][j];
            }
            System.out.println();
        }
        average /= (array.length*array[0].length); 
        int kol = 0;
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                if ( array[i][j] < average) {
                    kol++;
                }
            }
        }
        System.out.printf("%.2f %d", average, kol);
    }
}
```

Задача
**Удаление строк**
Напишите три статических метода для работы с двумерным массивом:

1) initArray() - инициализирует двумерный массив случайными числами от 0 до 10;

2) printArray() - выводит двумерный массив на консоль в виде таблицы (элементы строках отделяются знаками табуляции, и знак табуляции должен быть в конце каждой строки)

3)  deleteRow() - создает новый двумерный массив из исходного (первый параметр метода), удаляя строку, индекс которой передается в качестве второго параметра. Если индекс неверный (отрицательный или больше последнего индекса строк), то ничего не происходит.

В методе main() вводятся четыре целых числа: количество строк и количество столбцов массива, начальное значение генератора случайных чисел и номер строки для удаления.

Двумерный массив создается и выводится в виде таблицы. Затем выводится новый массив. Код метода main() менять нельзя!

Тестовые данные
Sample Input:

4 3 77 2
Sample Output:

9	6	7	
9	4	2	
6	5	5	
6	0	9	

9	6	7	
9	4	2	
6	0	9
Решение
```
import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
       Scanner scan = new Scanner(System.in);
        int[][] mas = new int[scan.nextInt()][scan.nextInt()];
        long seed = scan.nextLong();
        int ind = scan.nextInt();
        initArray(mas, seed);
        printArray(mas);
        System.out.println();
        mas = deleteRow(mas, ind);
        printArray(mas);
    }
   public static int[][] deleteRow(int[][] a, int ind){
        if (ind < 0 || ind >= a.length){
            return a;
        }
        int[][] b = new int[a.length-1][];
        //первая версия - когда старый массив сохранять не нужно
//        for (int i = 0; i < ind; i++) { //переписываем ссылки до удаляемой строки
//            b[i] = a[i];
//        }
//        for (int i = ind + 1; i < a.length; i++) { //переписываем ссылки после удаляемой строки
//            b[i - 1] = a[i];
//        }
        //вторая версия - когда старый массив не должен измениться, 
        // копируем все элементы
        for (int i = 0; i < ind; i++) { 
            b[i] = new int[a[i].length];
            for(int j = 0; j < a[i].length; j++) {
                b[i][j] = a[i][j];
            }
        }
        for (int i = ind + 1; i < a.length; i++) {
            b[i-1] = new int[a[i].length];
            for (int j = 0; j < a[i].length; j++) {
                b[i-1][j] = a[i][j];
            }
        }
        return b;
    }
    public static void initArray(int[][] a, long seed){
        Random rand = new Random(seed);
        for( int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[i].length; j++) {
                a[i][j] = rand.nextInt(11);
            }
        }
    }
    public static void printArray(int[][] a){
        for( int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[i].length; j++) {
                System.out.print(a[i][j] + "\t");
            }
            System.out.println();
        }

    }
}
```
## Объекты класса java.util

### Random

import java.util.Random;

Random rand = new Random(21); //начальное значение генератора 21
Random random = new Random(); //начальное значение генератора всегда разное

```
public static void main(String[] args) {
    Scanner scan = new Scanner(System.in);
    int[] a= new int[6];
    long seed = scan.nextLong(); //вводим начальное значение генератора
    Random rand = new Random(seed); //Создаем объект класса Random
    for(int i = 0; i < a.length; i++){
         a[i] = rand.nextInt(-5, 6); //числа от -5 до 5
         System.out.print(a[i] + " ");
    }
    System.out.println();
}
```

```
 public static void main(String[] args) {
     Scanner scan = new Scanner(System.in);
     long seed = scan.nextLong(); //вводим начальное значение генератора
     Random rand = new Random(seed); //Создаем объект класса Random
     double[] b = new double[10];
     for(int i = 0; i < b.length; i++){
         b[i] = rand.nextDouble(10., 20.); //от 10.0 до 20.0
         System.out.printf("%.1f ",b[i]);
     }
     System.out.println();
}
```

### Arrays

**Метод Arrays.toString()**
String toString(Object[] a)
Этот метод принимает ссылку на массив (перегружен для всех базовых типов данных), а возвращает строковое представление массива. Например:
```
int[] mas = {1, 2, -3, 4, 25, 6, 17, -1, 9, 6};
String str=Arrays.toString(mas);
System.out.println(str);
```
На консоль будет выведено:
```
[1, 2, -3, 4, 25, 6, 17, -1, 9, 6]
```

**Метод Arrays.sort()**
void sort(Object[] a)
Выполняет сортировку (упорядочивание) массива по возрастанию. Может может применяться только к таким массивам,  для элементов которых реализована операция сравнения  (на больше-меньше). Для всех базовых типов и типа String это выполняется.

Реализует быструю сортировку (QuickSort).

Отсортируем массив mas и выведем его на консоль:
```
Arrays.sort(mas);
System.out.println(Arrays.toString(mas));
Получим упорядоченный по возрастанию массив:

[-3, -1, 1, 2, 4, 6, 6, 9, 17, 25]
```
Для массивов примитивных типов отсортировать массив по убыванию методом Arrays.sort() не получиться. А вот для массива строк - пожалуйста!  Для этого нужно вторым аргументом в метод sort() передать метод Collections.reverseOrder() (импортировать класс Collections тоже нужно, разумеется).
```
String[] list = {"Даша", "Яна", "Андрюха", "Ромка"};
Arrays.sort(list, Collections.reverseOrder());
System.out.println(Arrays.toString(list));
На консоли получим:

[Яна, Ромка, Даша, Андрюха]
```
Если нужно отсортировать только часть массива, то используется следующая перегрузка метода sort():

void sort(Object[] a, int fromIndex, int toIndex)
Сортируется часть массива a от fromIndex (включая) до toIndex (не включая).
```
int[] mas = {1, 2, -3, 4, 25, 6, 17, -1, 9, 6};
Arrays.sort(mas, 3, 8);
System.out.println(Arrays.toString(mas));
Будет выведено на консоль (отсортированную часть массива я выделила красным цветом:

[1, 2, -3, -1, 4, 6, 17, 25, 9, 6]
```

**Метод Arrays.binarySearch()**
 int binarySearch​(Object[] a, Object key)
Методом бинарного поиска находит в массиве a  индекс элемента key.  Массив a должен быть предварительно отсортирован! Если в массиве таких элементов несколько, то находится индекс одного из них (какого именно - не гарантируется). Если искомый элемент в массиве отсутствует, то метод вернет отрицательное число.
```
int[] mas = {1, 2, -3, 4, 25, 6, 17, -1, 9, 6};
Arrays.sort(mas);
System.out.println(Arrays.toString(mas));
int ind = Arrays.binarySearch(mas, 5);
if(ind >= 0) {
     System.out.println("Индекс элемента = " + ind);
}else{
     System.out.println("Элемент отсутствует");
}
```
Поскольку значения 5 нет в массиве, будет выведено "Элемент отсутствует".

**Метод Arrays.fill()**
void fill(Object[] a, Object val)
Заполняет массив a одинаковыми значениями val.  Работает только с одномерными массивами.

Например, вещественный массив b заполняется значениями 2.5:
```
double[] b = new double[5];
Arrays.fill(b, 2.5);
System.out.println(Arrays.toString(b));
Получаем:

[2.5, 2.5, 2.5, 2.5, 2.5]
```
Заполнить можно не только весь массив, но и его часть: от индекса fromIndex до индекса toIndex (не включая):

void fill(Object[] a, int fromIndex, int toIndex, Object val)
Если применить к полученному ранее массиву b следующий код:
```
Arrays.fill(b, 2, 4, 0.8);
System.out.println(Arrays.toString(b));
То на консоли получим:

[2.5, 2.5, 0.8, 0.8, 2.5]

```
**Метод Arrays.copyOf()**
int[] copyOf(int[] original, int newLength)
Создает новый массив и копирует в него элементы массива original. Параметр newLength - это длина нового массива. Если она меньше длины исходного массива original, то лишние элементы игнорируются. Если больше - то в конце элементы заполняются нулями.

Существуют перегрузки этого метода для всех базовых типов. Для ссылочных типов нужно понимать, что копируются в новый массив только ссылки, а сами объекты, на которые они ссылаются, остаются те же.
```
int[] mas = {1, 2, -3, 4, 25, 6, 17, -1, 9, 6};
int[] c = Arrays.copyOf(mas, 5);
System.out.println(Arrays.toString(c));
На консоли получим:

[1, 2, -3, 4, 25]

int[] mas = {1, 2, -3, 4, 25, 6, 17, -1, 9, 6};
int[] d = Arrays.copyOf(mas, 15);
System.out.println(Arrays.toString(d));
Получаем:

[1, 2, -3, 4, 25, 6, 17, -1, 9, 6, 0, 0, 0, 0, 0]

Пример со строками:

String[] list = {"Даша","Яна", "Андрюха","Ромка"};
String[] list2 = Arrays.copyOf(list,3);
System.out.println(Arrays.toString(list2));
На консоли получаем:

[Даша, Яна, Андрюха]
```

 **Метод Arrays.copyOfRange()**
int[] copyOfRange(int[] original, int from, int to)
Создает  массив и копирует в него элементы массива original с индекса from до индекса to (как обычно, не включая этот элемент). Аналогично методу copyOf() существуют перегрузки для различных типов элементов массива.
```
int[] mas = {1, 2, -3, 4, 25, 6, 17, -1, 9, 6};
int[] d = Arrays.copyOfRange(mas, 4,8);
System.out.println(Arrays.toString(d));
Получаем на консоли:

[25, 6, 17, -1]
```
С остальными методами класса Arrays рекомендую познакомиться в официальной документации по Java:  [vot](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html)