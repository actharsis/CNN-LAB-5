# Решение задачи классификации изображений из набора данных Food-101 использованием нейронных сетей глубокого обучения и техники обучения Fine Tuning
## EfficientNet-B0 с оптимальной политикой темпа обучения и аугментации данных
Файл: `CNN-food-101-master/train.py`

Во всех случаях использовались следующие политики: случайное горизонтальное отображение, косинусное затухание с перезапусками с параметрами INITIAL_LEARNING_RATE = 0.001, FIRST_DECAY_STEPS = 100

![legend1](https://github.com/actharsis/lab-5/blob/main/graph/first_train/legend.png)

Метрика качества на валидации:

![gr1](https://github.com/actharsis/lab-5/blob/main/graph/first_train/epoch_categorical_accuracy.svg)

Функция потерь:

![gr2](https://github.com/actharsis/lab-5/blob/main/graph/first_train/epoch_loss.svg)

Максимальная точность на валидации 67.53%

## Fine tuning

![legend2](https://github.com/actharsis/lab-5/blob/main/graph/second_train/legend.png)

Метрика качества на валидации:

![gr3](https://github.com/actharsis/lab-5/blob/main/graph/second_train/epoch_categorical_accuracy.svg)

Функция потерь:

![gr4](https://github.com/actharsis/lab-5/blob/main/graph/second_train/epoch_loss.svg)

Максимальная точность на валидации достигает 68.07% на 1 эпохе(lr=5e-7), однако после 2-ой же эпохи результаты начинают стремительно ухудшаться и к 20-ой эпохе уже составляют всего 52% точности. 

## Анализ результатов
Использование техники Fine tuning помогло нам увеличить точность нейросети на 0.54% и достигнуть результата 67.53% при использовании параметра темпа обучения 5e-7. Скорее всего при коррекции параметров темпа обучения и аугментации данных в сочетании с этой техникой можно было бы достигнуть лучших показателей.
