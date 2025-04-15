# Звіт до роботи

## Тема: Основи побудови графіків у Python. Бібліотека Matplotlib

---

## Мета роботи:

Ознайомитися з основними можливостями бібліотеки **Matplotlib** для візуалізації даних, навчитися створювати графіки різного типу: лінійні, точкові, гістограми та відображення кількох функцій на одному графіку.

---

## Хід виконання:

### Крок 1: Встановлення matplotlib

Для роботи з графіками використано Jupyter Notebook.
На початку було встановлено необхідну бібліотеку:

```python
%pip install matplotlib
%matplotlib inline
```

Після цього ядро було перезапущено.

---

### Крок 2: Імпорт бібліотек

```python
import matplotlib.pyplot as plt
import numpy as np
```

---

### Крок 3: Базовий графік (plot)

Було створено лінійний графік, де значення `y` подано як список. Значення `x` створюється автоматично, починаючи з 0:

```python
plt.plot([1, 2, 4, 8])
plt.show()
```
![Графік plot](https://github.com/vzelinka/matplotlib_vika/blob/main/image/plt.plot.png?raw=true)


---

### Крок 4: Генерація випадкових даних

Згенеровано масиви `x` і `y` випадкових чисел, а також проаналізовано статистичні характеристики:

```python
s = 100
rng = np.random.default_rng(seed=101)
x = rng.integers(0, 5, size=s, endpoint=True)
y = rng.integers(0, 100, size=s, endpoint=True)
```

Після цього було виведено кількість елементів, унікальні значення, максимум, мінімум і середнє.

---

### Крок 5: Точковий графік (scatter)

Побудовано графік розсіювання, де додано підписи осей, заголовок і пунктирну лінію для середнього значення `y`:

```python
plt.scatter(x, y)
plt.xlabel('x')
plt.ylabel('y')
plt.title('Випадкові величини x та y')
plt.plot(y.mean().repeat(x.max()+1), "--")
plt.show()
```

![Графік x та y](https://github.com/vzelinka/matplotlib_vika/blob/main/image/xy.png?raw=true)



---

### Крок 6: Гістограма

Для побудови гістограми використано метод `plt.hist`:

```python
plt.hist(y)
plt.show()
```
![Гістограма](https://github.com/vzelinka/matplotlib_vika/blob/main/image/histogram.png?raw=true)


---

### Крок 7: Графіки декількох функцій

На завершення побудовано одразу кілька функцій на одному графіку з відповідними підписами:

```python
x = np.linspace(0, 5, 100)
ya = (5 - x)/4
yb = (3 - x)**2
yc = (2 - x)
yd = np.full_like(x, 1)

plt.plot(x, ya, label='y = (5 - x)/4')
plt.plot(x, yb, label='y = (3 - x)**2')
plt.plot(x, yc, label='y = 2 - x')
plt.plot(x, yd, label='y = 1')
plt.title('Візуалізація')
plt.xlabel('x')
plt.ylabel('y')
plt.legend()
plt.show()
```

![Візуалізація](https://github.com/vzelinka/matplotlib_vika/blob/main/image/visualization.png?raw=true)



---

## Висновок:

У ході практичного завдання було засвоєно основи побудови графіків за допомогою бібліотеки `matplotlib`. Створено графіки різного типу, проведено аналіз випадкових даних, додано підписи осей, заголовки, легенди. Отримані навички є основою для подальшої роботи з візуалізацією у Data Science та аналітиці.
