# Прогнозирование заказов такси
[(ipynb)](https://github.com/agamai/Portfolio/blob/main/Taxi_orders/taxi_orders.ipynb)

## Общее описание
Для компании агрегатора такси нужно спрогнозировать количество заказов такси на следующий час (на основе исторических данных о заказах такси в аэропортах). Необходимо обучить модель для предсказания количества заказов такси на следующий час со значением метрики RMSE на тестовой выборке не больше 48.

## Инструменты
* **python**
* **pandas**
* **numpy**
* **matplotlib**
* **time**
* sklearn.metrics.**mean_squared_error**
* sklearn.model_selection.**train_test_split**
* sklearn.model_selection.**GridSearchCV**
* sklearn.model_selection.**cross_val_score**
* sklearn.model_selection.**TimeSeriesSplit**
* statsmodels.tsa.seasonal.**seasonal_decompose**
* sklearn.ensemble.**RandomForestRegressor**
* catboost.**CatBoostRegressor**
* lightgbm.**LGBMRegressor**

## Выводы
В ходе предобработки данных временные данные были проверены на монотонность и ресемплированы. Далее были построены графики по тренду, сезонности и остатку за различные периоды, а также сделаны выводы о важности календарных признаков. В датасет были добавлены новые календарные признаки, а также скользящие и отстающие значения. Были обучены модели LGBMRegressor, CatBoostRegressor и RandomForestRegressor, гиперпараметры подбирались при помощи GridSearchCV. Лучшие результаты показала модель типа LGBMRegressor с гиперпараметрами learning_rate=0.1, n_estimators=60, num_leaves=51. RMSE на тестовой выборке - 42.
