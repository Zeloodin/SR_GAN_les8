---

## Обучение нейронной сети на производственном датасете

### Введение
В данной работе мы обучим нейронную сеть на большом датасете изображений древесных дефектов. Задача заключается в классификации изображений на дефектные и бездефектные на основе предварительно обработанных изображений по их визуальным характеристикам. Мы будем использовать предобученную архитектуру VGG19, адаптируя её к нашей задаче с целью улучшения качества обучения.

---

### Шаги выполнения

1. **Загрузка и подготовка данных**:
   - Использовали датасет, доступный на Kaggle.
   - Загрузили изображения и соответствующие им bounding box'ы, сохранив их в формате NumPy для дальнейшей обработки.

2. **Обработка изображений**:
   - Изменили размер всех изображений до 256x256 пикселей.
   - Нормализовали данные и разделили их на обучающий и тестовый наборы.

3. **Обучение модели**:
   - Использовали VGG19, замороженную для использования извлеченных ранее признаков.
   - Добавили полносвязные (dense) слои для классификации.

4. **Метрики и оценка модели**:
   - Оценка точности и фреймерной меры (F1-score).
   - Проведение анализа моделей KNN для выбора наилучшего количества соседей.

5. **Использование PCA**:
   - Применили метод главных компонент, чтобы упростить данные и улучшить производительность модели.


---

### Анализ результатов
- В ходе тренировки и оценки на тестовых данных, мы заметили, что заморозка слоев базовой модели VGG19 позволяло более эффективно извлекать признаки из изображений.
- Сравнение результатов с различным числом соседей в KNN показало, что наилучшая производительность достигается при определённом значении.
- Применение PCA также улучшило параметры и скорость работы модели, что значительно ускорило время обработки.

---

### Вывод
Полный процесс обучения нейронной сети и последующего анализа показал, как важно применять предобученные модели, чтобы снизить временные затраты на тренировки и улучшить качество предсказаний за счёт извлеченных признаков. Эффективная обработка изображений и правильно выбранные метрики значительно влияют на итоговую результативность.
