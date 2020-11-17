# Программа, прогнозирующая цены валют

#### Данная программа по данным за некоторый исторический период прогнозирует цену на валюту, которая предположительна была некоторое время спустя этого периода.

###### Для того, чтобы прогнозировать данные, программа находит апроксимирующую пряму по последним точкам датасета. Коэффициенты прямой находятся градиентным спуском:


\begin{equation}
L = (y - (ax + b))^2  
\\
\alpha - learning \ rate
\\
\Downarrow
\\
\begin{cases}
   \frac{\partial L}{\partial a}  = -(y - (ax + b))x\\
\frac{\partial L}{\partial a}  = -(y - (ax + b))
 \end{cases}
 \\
 \Downarrow
 \\
\begin{cases}
  a' = a - \frac{\partial L}{\partial a} \alpha\\
  b' = b - \frac{\partial L}{\partial b} \alpha\\
 \end{cases}
\end{equation}
![formula](https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1)

Вычисление градиента loss-функции и измерение параметров `a` и `b` происходит для каждой из рассматриваемых точек в цикле, который включен во внешний цикл, который повторяет это до тех пор, пока не будет превышено предельное колличество эпох, или пока каждая из координат градиента не станет достаточно мала.


###### Данная программа является прототипом. Итоговая версия будет брать данные за последние секунды или доли секунд в реальном времени и прогнозировать цены на доли секунд вперед.
