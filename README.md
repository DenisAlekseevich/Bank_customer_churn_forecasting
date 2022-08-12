# Прогнозирование оттока клиента Банка

## Задача проекта

Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. В наше распоряжение предоставлены исторические данные о поведении клиентов и расторжении договоров с банком. 

Требуется построить модель с предельно большим значением *F1*-меры(от 0.59 или выше). Дополнительно проверим *F1*-меру на тестовой выборке.

А так же будем измерять *AUC-ROC* и сравнивать её значение с *F1*-мерой.

Источник данных: [https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling](https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling) 


## Инструменты и навыки

`Pandas`
`Matplotlib`
`Scikit-learn`
`Numpy`
`машинное обучение`

## Краткое описание выполнения проекта

На входе имеем исторические данные о поведении клиентов и расторжении договоров с банком.

Обрабатываем пропуски. Так как целевой признак не сбалансирован, обучаем несколько моделей машинного обучения без учета дисбаланса и учитывая его. Выбираем наилучшую модель. Сравниваем её с константной моделью.

## Данные и выводы

При учёте несбалансированности классов целевого признака и балансировании весов их значимости все модели, кроме К-ближайших соседей, показывают лучшие результаты, чем без учета баланса классов. Наилучшие показатели снова у Случайного леса: *F1*-мера - 0.6396, *AUC-ROC* - 0.8583.

Выбранная нами модель показывает максимальный показатель *F1*-меры на валидационной и тестовой выборках, что доказывает правильность выбора модели и её гиперпараметров. Так же модель прошла проверку при сравнении с константой.

Данная модель готова к работе по предсказанию вероятности ухода клиента из банка.
