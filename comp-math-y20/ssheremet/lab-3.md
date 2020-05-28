#### Ивницкий Алексей, M3205
## Лабораторная работа №3

Вычислить приближенно методом Симсона интеграл
$$\int_1^{2.4} \frac {dx}{\alpha+\beta\cdot x^3}$$
взяв шаг $h=0.2,\alpha=1.3,\beta=2.4$.

```C
double funcEven = 0;
double funcOdd = 0;
for (double i = left + 2 * h; i < right; i += 2 * h)
{
    funcEven += func(i);
}
for (double i = left + h; i < right; i += 2 * h)
{
    funcOdd += func(left + i * h);
}
return h / 3 * (func(left) + 2 * funcEven + 4 * funcOdd + func(right));
```
Ответ: $0,279333271632691$