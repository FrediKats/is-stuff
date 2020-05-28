#### Ивницкий Алексей, M3205
## Лабораторная работа №6

Вычислить значение производной функции $f(x) = \frac{1}{1 + sin(x)}$ в точке х = 1.5
C помощью полинома Ньютона и шага 0.25 на промежутке [1;2]

C помощью полинома Ньютона:
```C
double[][] coeffs = new double[number][];
coeffs[0] = new double[number];
for (int i = 0; i < coeffs[0].Length; i++)
{
	coeffs[0][i] = func(left + i * step);
}
for (int i = 1; i < coeffs.Length; i++)
{
	coeffs[i] = new double[number - i];
	for (int j = 0; j < coeffs[i].Length; j++)
	{
		coeffs[i][j] = coeffs[i - 1][j + 1] - coeffs[i - 1][j];
	}
}
double t = (point - left) / step;
return 0;
```

$$
y'(1.5) = -0.08980279
$$