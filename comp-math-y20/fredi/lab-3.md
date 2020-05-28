#### Ивницкий Алексей, M3205
## Лабораторная работа №3

Вычислить приближенно методом Симсона интеграл
$$\int_1^{2.6} \frac {dx}{\alpha+\beta\cdot x^3}$$
взяв шаг $h=0.2,\alpha=1.1,\beta=2.6$.

```C
const double h = 0.2;
double even = 0;
double odd = 0;
for (var i = from; i <= to; i += h * 2)
    odd += f(i);
for (var i = from + h; i <= to; i += h * 2)
    even += f(i);
return h / 3 * (f(from) + f(to) + 2 * even + 4 * odd;
```
Ответ: $0,20013435498244$