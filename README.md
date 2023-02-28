# Контрольная работа Клименко Александра.  группа "Разработчик"


## Программа разложит введённую строку на массив из слов, а затем выведет те элементы массива, длина которых меньше или равна числу, которое будет указано далее

* Для удобства ввода изначального массива релизован ввод строки, которую программа сама разложит в массив. Разделителями при этом будут считаться знаки: пробел . , ! ; ?

 string[] SplitStringToArray(string s)
{
    char[] separators = new char[] { ' ', '.', ',', '!', ';', '?' };
    string[] subS = s.Split(separators, StringSplitOptions.RemoveEmptyEntries);
    return subS;
}

* Реализован ввод числа для отбора в массиве. Также реализована проверка ввода числа. При некорректном вводе число будет запрошено повторно.

int EnterCount(string welcomeToInput)
{
 bool inputOk = false;
 int count = 0;
 while (!inputOk)
 {
     System.Console.Write(welcomeToInput);
     string inp = Console.ReadLine()!;
     inputOk = int.TryParse(inp, out int n);
     if (inputOk)
         count = n;
     else
         System.Console.Write("Вы ввели не число. ");
 }
 return count;
}