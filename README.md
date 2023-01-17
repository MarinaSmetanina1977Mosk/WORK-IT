# WORK-IT
Итоговая проверочная работа.
Задача:

Написать программу, которая из имеющегося массива строк формирует массив из строк, длина которых меньше либо равна 3 символа. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.
Алгоритм решения:

    Делаем перебор значений из исходного массива
    Проверяем каждое значение из массива на соответствие условию: длина строки меньше или равна трем
    Если строка удовлетворяет условию кладем значение в новый массив
    Повторяем пункты 2 и 3 до тех пор пока не достигнем конца исходного массива
    Возвращаем новый заполненый массив как результат

Блок-схема алгоритма:

using System;
using static System.Console;

Clear();

string[] array = AskArray();
string[] result = FindLessThan(array, 3);
WriteLine($"[{string.Join(", ", array)}] -> [{string.Join(", ", result)}]");

string[] FindLessThan(string[] input, int n) {
    string[] output = new string[CountLessThan(input, n)];

    for(int i = 0, j = 0; i < input.Length; i++) {
        if(input[i].Length <= n) {
            output[j] = input[i];
            j++;
        }
    }

    return output;
}

int CountLessThan(string[] input, int n) {
    int count = 0;

    for(int i = 0; i < input.Length; i++) {
        if(input[i].Length <= n) {
            count++;
        }
    }

    return count;
}

string[] AskArray() {
    Write("Введите значения через пробел: ");
    return ReadLine().Split(" ");
}

