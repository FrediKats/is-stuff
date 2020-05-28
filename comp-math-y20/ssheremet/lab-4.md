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
FiberMethod(IList<double> xList, IList<double> yList)
{
    Validation(xList, yList);
    double k = (yList[yList.Count - 1] - yList[0])
                / (xList[xList.Count - 1] - xList[0]);
    double b = yList[0] - k * xList[0];
    return (k, b);
}
```

```C
LeastSquares(IList<double> xList, IList<double> yList)
{
    Validation(xList, yList);
    double xSum = xList.Sum();
    double ySum = yList.Sum();
    double xSqrSum = 0;
    double xySum = 0;
    foreach(double x in xList)
    {
        xSqrSum += x * x;
    }
    for(int i = 0; i < xList.Count; i++)
    {
        xySum += xList[i] * yList[i];
    }
    double k = (xList.Count * xySum - xSum * ySum)
                / (xList.Count * xSqrSum - xSum * xSum);
    double b = (ySum - k * xSum) / xList.Count;
    return (k, b);
}
```
```C
DeviationSumOfSquares(double k, double b,
                        IList<double> xList, IList<double> yList)
{
    Validation(xList, yList);
    double e = 0;
    for (int i = 0; i < xList.Count; i++)
    {
        e += Math.Pow(yList[i] - k * xList[i] - b, 2);
    }
    return e;
}
```
Для метода натянутой нити $a = 0,272108843537415, b = 4,25510204081633$
Для метода наименьших квадратов $a = 0,253678639752552, b = 4,39895228048846$

Сумма квадратных уклонений
Для метода натянутой нити $S = 0,204084409273915$   
Для метода наименьших квадратов $S = 0,12672247948365$
