# Прогнозирование оттока клиентов (телеком)
[(ipynb)](https://github.com/agamai/Portfolio/blob/main/Customer_churn/telecom_customer_churn.ipynb)

## Общее описание
Для оператора связи необходимо построить прототип модели машинного обучения, которая сможет прогнозировать отток клиентов на основе их персональных данных (личные данные, информация по договорам и подключенным услугам). Задача сводится к тому, чтобы обучить модель бинарной классификации для предсказания оттока клиентов с метрикой ROC-AUC не менее 0.85.

## Инструменты
* **python**
* **pandas**
* **matplotlib**
* **seaborn**
* **time**
* **re**
* phik.**report**
* phik.**plot_correlation_matrix**
* sklearn.model_selection.**train_test_split**
* sklearn.model_selection.**GridSearchCV**
* sklearn.preprocessing.**StandardScaler**
* sklearn.preprocessing.**OrdinalEncoder**
* sklearn.preprocessing.**OneHotEncoder**
* sklearn.linear_model.**LogisticRegression**
* sklearn.ensemble.**RandomForestClassifier**
* sklearn.metrics.**roc_auc_score**
* sklearn.metrics.**accuracy_score**
* sklearn.metrics.**roc_curve**
* sklearn.metrics.**confusion_matrix**
* sklearn.metrics.**precision_recall_curve**
* sklearn.metrics.**precision_score**
* sklearn.metrics.**recall_score**
* catboost.**CatBoostClassifier**
* lightgbm.**LGBMClassifier**

## Выводы
В ходе предобработки данных были проработаны пропуски, определен целевой признак, данные были приведены к нужным типам. На этапе исследовательского анализа данных были созданы синтетические признаки, проведен анализ выбросов, распределения и корреляции, а также был сформирован портрет уходящего пользователя. Признаки были проанализированы на предмет мультиколлинеарности, составлено несколько датасетов с различными комбинациями признаков (для различных моделей и способов кодирования/масштабирования). Далее было обучено четыре модели: LogisticRegression, RandomForestClassifier, CatBoostClassifier, LGBMClassifier. Гиперпараметры подбирались при помощи GridSearchCV (с кросс-валидацией на 5 фолдах). Лучшие результаты показала модель LGBMClassifier (learning_rate: 0.04, n_estimators: 100, num_leaves: 41), обученная на данных, кодированных с помощью OrdinalEncoder. roc_auc: 0.9347, accuracy: 0.8989. По итогам анализа выбранной модели и важности признаков были предложены рекомендации заказчику для удержания клиентов.
