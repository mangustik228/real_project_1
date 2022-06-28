### Проект для общественной организации  
  
<br></br>
**Программа для решения следующих проблем:**
- Существовало 2excel файла, надо было их объединить и привести к общему формату
- Есть ежедневные выгрузки эквайринга в формате .xlxs их необходимо вносить в базу данных которая ведетеся также в excel (необходимо автоматизировать по максимум процесс, где то должно вносится по имени, где то по номеру билета)
- Существует основная база данных с членами организации на сайте, но из за медленности штатных программистов и длительного времени ожидания выгрузки базы, было принято решения написать парсер, который должен собирать данные членов организации(необходима авторизация на сайте)
- Так как пользоваться будет человек не связанный с программированием, то необходим графический интерфейс
- Помимо эквайринга также были единоразовые выгрузки из 1С и еще откуда то, которые надо было привести к порядку. при этом в платежках могли указывать что угодно, из разряда "Здравствуйте, я Иванов, плачу за себя"


**Технологии:**
- `tkinter` - графический интерфейс программы
- `request`, `BeatifulSoup`, `fake_user` - парсинг данных
- `pandas` - предобработка данных
- `re`(регулярные выражения) - вытаскивания правильных телефонов, имен
- `natasha` - извлечение именновых сущностей из кривых платежек(где регулярки явно не помогут) (справилась плохо. как правило отчество не распознает), толи не разобрался с библиотекой, толи лучше работает все таки со статьями(как и задумывалось авторами)


**Файлы**
- main.py - Основная логика программы. tkinter/препроцесс
- parsing/pars.py - Часть программы связанная с парсингом данных с сайта
- preprocessing/clean_data.ipynb - чистка выгруженных данных, сверка с базой Excel, которая ведется сотрудником
- preprocessing/joining.ipynb - Объединение двух таблиц
- preprocessing/extractor.ipynb - Извлечение информации о платежах из выгрузки 1С