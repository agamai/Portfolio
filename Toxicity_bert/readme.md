# Определение токсичности комментариев с BERT (английский язык)
[(ipynb)](https://github.com/agamai/Portfolio/blob/main/Toxicity_bert/toxic_bert.ipynb)

## Общее описание
Интернет-магазину нужен инструмент, который будет искать токсичные комментарии пользователей о товарах и отправлять их на модерацию. В нашем распоряжении набор данных с разметкой о токсичности правок. Необходимо обучить модель бинарной классификации текстов со значением метрики качества F1 не меньше 0.75.

## Инструменты
* **python**
* **pandas**
* **numpy**
* **matplotlib**
* **tqdm**
* **re**
* **time**
* **torch**
* torch.nn.utils.rnn.**pad_sequence**
* transformers.**BertTokenizer**
* transformers.**BertModel**
* sklearn.utils.**shuffle**
* sklearn.metrics.**f1_score**
* sklearn.metrics.**accuracy_score**
* sklearn.metrics.**precision_score**
* sklearn.metrics.**recall_score**
* sklearn.model_selection.**train_test_split**
* sklearn.model_selection.**GridSearchCV**
* sklearn.model_selection.**KFold**
* sklearn.linear_model.**LogisticRegression**
* sklearn.ensemble.**RandomForestClassifier**
* sklearn.dummy.**DummyClassifier**
* catboost.**CatBoostClassifier**
* lightgbm.**LGBMClassifier**

## Выводы
На этапе предобработки данных тексты были очищены, дисбаланс классов был преодолен с помощью downsample. Далее была использована предобученная модель [*unitary/toxic-bert*](https://huggingface.co/unitary/toxic-bert), с её помощью произведена токенизация текстов и созданы наборы эмбеддингов. По эмбеддингам были обучены модели LogisticRegression, RandomForestClassifier, CatBoostClassifier, LGBMClassifier, гиперпараметры подобраны при помощи GridSearchCV. Наилучшие результаты продемонстировала модель типа LGBMClassifier (F1: 0.859, Accuracy: 0.97, Precision: 0.764, Recall: 0.982).
