# Восстановление золота из руды
[(ipynb)](https://github.com/agamai/Portfolio/blob/main/Gold_recovery/gold_recovery.ipynb)

## Общее описание
Для компании-разработчика решений для эффективной работы промышленных предприятий необходимо подготовить прототип модели машинного обучения, которая должна предсказать коэффициент восстановления золота из золотосодержащей руды. Предоставленные данные включают в себя параметры добычи и очистки. Модель должна оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками. Необходимо обучить модель, которая предскажет коэффициент восстановления золота из золотосодержащей руды со значением метрики sMAPE (Symmetric Mean Absolute Percentage Error) не более 9.

## Инструменты
* **python**
* **pandas**
* **numpy**
* **matplotlib**
* **seaborn**
* sklearn.metrics.**mean_absolute_error**
* sklearn.metrics.**make_scorer**
* sklearn.model_selection.**cross_val_score**
* sklearn.model_selection.**GridSearchCV**
* sklearn.linear_model.**LinearRegression**
* sklearn.linear_model.**Ridge**
* sklearn.ensemble.**RandomForestRegressor**
* sklearn.dummy.**DummyRegressor**
* lightgbm.**LGBMRegressor**
* xgboost.**XGBRegressor**

## Выводы
В ходе предобработки данных были проработаны пропуски, а также произведена проверка расчета целевого признака. Данные, касающиеся различных этапов очистки руды, были изучены на предмет корреляции и выбросов. Были сделаны выводы о важности признаков. Была создана функция для вычисления целевой метрики sMAPE. Далее были обучены модели 4х типов - RandomForestRegressor, XGBRegressor, Ridge и LinearRegression. Гиперпараметры подбирались с помощью GridSearchCV. Лучший результат показала модель случайного леса с гиперпараметрами max_depth = 4, n_estimators = 70. Метрики на тестовой выборке: SMAPE = 8.990, MAE = 5.461.
