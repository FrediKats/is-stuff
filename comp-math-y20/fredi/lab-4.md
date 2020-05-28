#### Ивницкий Алексей, M3205
## Лабораторная работа №4

Даны результаты измерений величин x и y, связанные линейной зависимостью y = a * x + b
| X | 1.1 | 2.5 | 4.1 | 5.9 | 7.6 | 9.5 | 11.1 | 12.6 | 14.1 | 15.4 |
|---|---|---|---|---|---|---|---|---|---|---|
| Y | 1.1 | 2.5 | 4.1 | 5.9 | 7.6 | 9.5 | 11.1 | 12.6 | 14.1 | 15.4 |

1. Найти параметры a и b методом натянутой нити
2. Найти a и b методом наименьших квадратов
3. Вычислить для каждого метода сумму квадратов уклонений:
$$S = \sum{\epsilon^2_i} = \sum{(a\cdot x_i + b - y_i)^2}$$
```C
double pointA = (y.Last() - y.First()) / (x.Last() - x.First());
double pointB = pointA * -x.First() + y.First();
double coefficient = x.Sum() / x.Count() * -1;
double mnkA = (x.Zip(y, (f, s) => f * s).Sum() + y.Sum() * coefficient) / (x.Select(i => i * i).Sum() + x.Sum() * coefficient);
var mnkB = (y.Sum() - x.Sum() * mnkA) / 10.0;
double sumFirst = 0, sumSecond = 0;

double Func(int i, double a, double b) => (a * x[i] + b - y[i]) * (a * x[i] + b - y[i]);
for (var i = 0; i < x.Length; i++)
{
    sumFirst += Func(i, pointA, pointB);
    sumSecond += Func(i, mnkA, mnkB);
}
return (sumFirst, sumSecond);
```
Для метода натянутой нити $a = 0,266, b = 4,308$
Для метода наименьших квадратов $a = 0,264, b = 4,384$

Сумма квадратных уклонений
Для метода натянутой нити $S = 0,121$
Для метода наименьших квадратов $S = 0,080$