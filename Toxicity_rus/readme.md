# Дообучение BERT на данных по токсичности

Работа представлена в двух файлах:
1. [Дообучение](https://github.com/agamai/Portfolio/blob/main/Toxicity_rus/my_toxicity_15ep_final.ipynb)
2. [Тестирование](https://github.com/agamai/Portfolio/blob/main/Toxicity_rus/my_toxicity_15ep_final_test.ipynb)

## Общее описание
Необходимо обучить модель классифицировать тексты (посты и комментарии из российских соцсетей) на предмет токсичности. Тексты были предварительно размечены вручную на наличие токсичности по нескольким категориям: не токсично, мат/нецензурное, грубое высказывание, дискриминация, оскорбление, угроза. Каждому тексту может соответствовать несколько категорий. Таким образом, задача сводится к классификации с несколькими метками (multi-label classification). Мы будем использовать предобученную модель  [*rubert-tiny-toxicity*](https://huggingface.co/cointegrated/rubert-tiny-toxicity), опубликованную на [*huggingface*](https://huggingface.co/). Имеющийся датасет будем использовать для дообучения модели. Обучаем на GPU, 15 эпох, learning_rate - 1e-5.

## Инструменты
* **python**
* **pandas**
* **numpy**
* **matplotlib**
* **tqdm**
* **re**
* sklearn.model_selection.**train_test_split**
* sklearn.utils.**shuffle**
* **torch**
* transformers.**Trainer**
* transformers.**TrainingArguments**
* transformers.**BertTokenizer**
* transformers.**BertForSequenceClassification**
* tensorflow.keras.metrics.**CategoricalAccuracy**
* tensorflow.keras.metrics.**CategoricalCrossentropy**
* tensorflow.keras.metrics.**Precision**
* tensorflow.keras.metrics.**Recall**
* tensorflow.keras.metrics.**AUC**

## Выводы
