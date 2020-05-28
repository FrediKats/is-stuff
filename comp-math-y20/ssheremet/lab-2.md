#### Ивницкий Алексей, M3205
## Лабораторная работа №2

Найти $x$ при $f(x) = 2 - 0.5 *x^2 - 0.5 * x^{-1} * sin(x) - x$

1. Решение методом половинного деления
```C
for (int i = 0; i < 100; i++)
{
    double middle = (left + right) / 2;
    double funcLeft = func(left);
    double funcRight = func(right);
    double funcMiddle = func(middle);
    if (funcLeft < funcRight && funcMiddle <= 0
        || funcLeft > funcRight && funcMiddle >= 0)
    {
        left = middle;
    }
    else
    {
        right = middle;
    }
}
return right;
```
Результат = 1,04243007461172

2. Решение методом хорд
```C
for (int i = 0; i < 100; i++)
{
    double funcLeft = func(left);
    double funcRight = func(right);
    double newPoint = left -funcLeft * (right - left)
                                        / (funcRight - funcLeft);

    if (func(newPoint) <= 0 && func(left) <= 0
        || func(newPoint) >= 0 && func(left) >= 0)
    {
        left = newPoint;
    }
    else
    {
        right = newPoint;
    }
}
return left;
```
Результат = 1,04243007461172

3. Решение методом касательных
```C
for (int i = 0; i < 10; i++)
{
    double value = func(point);
    double coeff = der(point);
    point -= value / coeff;
}
return point;
```
Результат = 1,04243007461172