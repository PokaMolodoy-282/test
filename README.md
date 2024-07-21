import java.io.IOException;
import java.util.Scanner;

public class Fianl {
    public static void main(String[] args) throws IOException {
        System.out.println("Запишите свой пример через пробел");//выводит первое сообщение
        Scanner sc = new Scanner(System.in);// ввод данных
        String exp = sc.nextLine();//хз
        System.out.println(calc(exp));// вывод полученного значения
    }

    static String calc(String exp) throws IOException { //
        String[] spltd = exp.split(" ");// вроде создание массива строк(String[]), split убирает данные(в скобках пробел - убирает пробел )
        int ans = 0;                           // заводим переменную равную 0
        if (spltd.length == 5) {               // если количество введеных данных равно 3/ изменяя можно увеличить кол-во символов
            int num1 = Integer.parseInt(spltd[0]);//дает переменной значение первого введенного числа
            char op = spltd[1].charAt(0); //дает переменной значение второго введеного символа  charAt возвращает символ
            int num2 = Integer.parseInt(spltd[2]);
            char op1 = spltd[3].charAt(0);
            int num3 = Integer.parseInt(spltd[4]);//дает переменной значение третьего введенного числа
            if ((num1 > 10 || num1 < 1) || (num2 > 10 || num2 < 1)|| (num3 > 10 || num3 < 1)) {//условие если числа от 1 до 10
                throw new IOException("Только числа от 1 до 10 включительно");//ошибка если числа не проходят if
            }
            switch (op) {
                case '+':
                    ans = num1 + num2 + num3;
                    break;
                case '-':
                    ans = num1 - num2 - num3;
                    break;
                case '*':
                    ans = num1 * num2 * num3;
                    break;
                case '/':
                    ans = num1 / num2 /num3;
                    break;
                default:
                    System.out.println("Формат математической операции не удовлетворяет заданию - два операнда и один оператор (+, -, /, *)");
                    break;
            }
        } else {
            throw new IOException("Строка не является математической операцией");
        }
        return String.valueOf(ans);
    }
}
