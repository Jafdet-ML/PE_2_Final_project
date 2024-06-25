# PE_2_Final_project

# Приложение API по пересказу содержания текстов

Приложение генерирует краткое содержание введенного текста, используя фреймворк Streamlit и предварительно обученную модель. Текст можно вводить через поле ввода текста, загрузить текстовый файл или загрузить звуковой файл. Краткость содержания текста регулируется механизмом выбора значения (ползунком), который регулирует степень сжатия текста, где 10 - это максимальная степень сжатия, а 100 - это минимальная степень сжатия (развернутый ответ).

Используемая модель: https://huggingface.co/csebuetnlp/mT5_multilingual_XLSum
Модель предварительно обучена на наборе данных XL-Sum 

## Работа с приложением
### Онлайн:
- Перейти по URL https://summarytextpy-9kn5rcfzhb463uwgjdp5s3.streamlit.app/;
- Выбрать один из двух возможных вариантов: «Ввод текста» или «Загрузка файла»;
- В случае загрузки текстового файла, требуется нажатие кнопки: «Создать»;
- Получить краткое содержание введённого текста.

### Локально:
Создать виртуальное окружение:

    python3 -m venv venv
Активировать виртуальное окружение:

    source venv/bin/activate
Установить зависимости из файла requirements.txt в корневой папке PE_2_Final_project

    pip install -r requirements.txt
Запустить приложение:

Перейти в PE_2_Final_project/summary_text:

    cd PE_2_Final_project/summary_text
Запустить приложение:

    streamlit run summary_text.py

Зависимости:
   - streamlit
   - transformers[torch, sentencepiece]
   - flake8
   - chardet
   - accelerate
   - librosa
    
Утилиты для анализа кода:
flake8
Утилита-комбайн, которая органично объединяет в себе несколько других анализаторов кода (pycodestyle, pyflakes и McCabe), 
а также имеет огромную экосистему плагинов, которые могут добавить к стандартной поставке ещё кучу различных проверок. 
На данный момент, это самый популярный линтер для Python-кода.

В проекте используется через git hub actions. Линтинг настроен на действия push и pull request в ветку main. 


## Список тестов

- GET. test_get_base_page. Базовая страница приложения. Проверяет статус-код и возвращаемое сообщение.
- POST. test_post_eng_text. Отправка текста на английском языке. Проверяет статус-код и возврат краткого содержания текста.
- POST. test_post_rus_text. Отправка короткого текста на русском языке. Проверяет статус-код и возврат тестового резюме.
- POST. test_post_empty_string. Отправка пустой строки. Проверяет статус-код и возврат сообщения по умолчанию для пустой строки.
- POST. test_error_empty_json. Отправка пустого JSON. Проверяет статус-код и возврат ошибки.

## Список дружной команды из двух-четырех человек:
- Табакарь Сергей Ильич
- null

Так как команду найти не удалось, код-ревью выполнялся самостоятельно на основе рекомендаций линтера

