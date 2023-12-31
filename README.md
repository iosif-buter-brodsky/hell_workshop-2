# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Цюприк Егор Васиьевич 
- РИ220936
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.


## Цель работы
Научиться передавать в Unity данные из Google Sheets с помощью Python.

## Задание 1
### Пошагово выполнить каждый пункт раздела "ход работы" с описанием и примерами реализации задач
Ход работы:
 Выберите одну из компьютерных игр, приведите скриншот её геймплея и краткое описание концепта игры. Выберите одну из игровых переменных в игре (ресурсы, внутри игровая валюта, здоровье персонажей и т.д.), опишите её роль в игре, условия изменения / появления и диапазон допустимых значений. Постройте схему экономической модели в игре и укажите место выбранного ресурса в ней.

## Игра - The Legend of Zelda: Breath of the Wild
![breath](https://github.com/iosif-buter-brodsky/hell_workshop-2/assets/146319327/56824170-fb12-4202-acd2-ef303eea8e38)

### Концепт игры
- Action-adventure в открытом мире - Королевстве Хайрул. Главный герой - рыцарь Линк, призванный спасти Королевство Хайрул из лап злого демона Ганона. Игроку доступен огромный проработанный открытый мир для иследования. Мир полон различных тайн и загадок, которые Линк решает при помощи своего загадочого артефакта - камня шиика. 
### Выбранная переменная 
- Для описания была выбрана внутреигровая переменная - Температура окружающей среды.
- Температура является игровой механикой которая присутствует повсюду Игрок может проверить температуру с помощью шкалы в правом нижнем углу экрана. При воздействии экстремальных температур Линк начнет получать урон. Данная механика нужна для большего погружения в игру, так как она добавляет реализма и сложности игре. Так же она является сдерживающим фактором для игрока, пока он достаточно не прокачается и не улучшит снаряжение он не сможет побывать в сложных сюжетных локациях. 
- Температура изменяется в зависимости от локации(биома) прибывания. В снежных и высокогорных локациях - температура низкая, в вулканической и пустынной локации - температура высокая, в равнинных и лесных локациях - температура средняя.
- Есть несколько способов, чтобы находясь в жарких и холодных местах не получать урона: использовать броню с эффектами охлаждения и согревания, использлвать еду с этими эффектами, согреваться от огня и охлаждаться от воды.
- Допустимые значения можно представить в виде шкалы. От 32F до 104F - температура приемлемая, выше или ниже персонаж начинает получать урон, при температуре ниже 14F или выше 122F персонаж получает повышенный урон.
 ![2023-10-29 20 46 38 miro com b43030ca6c8c](https://github.com/iosif-buter-brodsky/hell_workshop-2/assets/146319327/f36e3650-80b7-48bf-8a02-396038ae45e8)

  
## Задание 2
### С помощью скрипта на языке Python заполните google-таблицу данными, описывающими выбранную игровую переменную в выбранной игре.

```py

import gspread
import numpy as np

gc = gspread.service_account(filename='unity-urfu-hell-from-gamedev-8ed40ca87a00.json')
sh = gc.open("zelda_temperature")
price = np.random.randint(-20, 140, 10)
mon = list(range(1, 11))

for i in range(10):
    tempInf = str(tempInf).replace('.', ',')
    sh.sheet1.update('A' + str(i + 1), str(i + 1))
    sh.sheet1.update('B' + str(i + 1), int(price[i]))
    sh.sheet1.update('C' + str(i + 1), str(price[i]))
    print(f"{i + 1}, {price[i]}")
```
![2023-10-29 20 51 47 docs google com 831e5ccdb599](https://github.com/iosif-buter-brodsky/hell_workshop-2/assets/146319327/ba45f523-6dc7-4784-b445-af8cacb69cb6)


## Задание 3
### Настройте на сцене Unity воспроизведение звуковых файлов, описывающих динамику изменения выбранной переменной. Например, если выбрано здоровье главного персонажа вы можете выводить сообщения, связанные с его состоянием.
Ход работы:

- Создаем ключи для передачи данных из google таблицы в Unity
- Создаем проект на Unity, пишем скрипт для воспроизведения звуков 
- Добавляем звуковые файлы
- Запускаем и смотрим как работает


https://github.com/iosif-buter-brodsky/hell_workshop-2/assets/146319327/ca6fb73b-3550-4848-9d05-c97224a79612

 





## Выводы

Мы научились генерировать данные в google таблицы, передавать их напрямую в Unity. Круто.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
