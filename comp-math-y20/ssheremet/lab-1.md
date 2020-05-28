#### Ивницкий Алексей, M3205
## Лабораторная работа №1

Решить систему уравнений на ЭВМ с помощью метода Гаусса:
$$ \begin{alignedat}{3}
    2&x - &6&y + &3&z = -1 \\
    7&x + &2&y - &15&z = -32 \\
    &x - &4&y + &9&z = -5
\end{alignedat} $$
```C
if (matrix.Length == 0) throw new Exception();
foreach (var i in matrix)
{
    if (i.Length != matrix.Length + 1) throw new Exception();
}
double[][] newMatrix = (double[][])matrix.Clone();
```
```C
for (int i = 0; i < matrix[0].Length - 2; i++)
{
    for (int j = i + 1; j < matrix.Length; j++)
    {
        double coeff = matrix[j][i] / matrix[i][i];
        for (int k = i; k < matrix[0].Length; k++)
        {
            matrix[j][k] -= matrix[i][k] * coeff;
        }
    }
}

for (int i = 0; i < matrix.Length; i++)
{
    double coeff = matrix[i][i];
    for (int j = 0; j < matrix[0].Length; j++)
    {
        matrix[i][j] /= coeff;
    }
}
```
```C
for (int i = matrix[0].Length - 2; i > 0; i--)
{
    for (int j = i - 1; j >= 0; j--)
    {
        double coeff = matrix[j][i];
        for (int k = i; k < matrix[0].Length; k++)
        {
            matrix[j][k] -= matrix[i][k] * coeff;
        }
    }
}

double[] solution = new double[newMatrix.Length];
for (int i = 0; i < newMatrix.Length; i++)
{
    solution[i] = newMatrix[i][newMatrix[i].Length - 1];
}
return solution;
```
Ответ:
$$
x = -3;
y = -0,5;
z = 0,6667;
$$
