# Аналитик данных.Категоризация данных: Функция для одной строки
Прочитайте файл с отзывами, размещённый по адресу: /datasets/support_log_grouped.csv
Результат выведите на экран.

import pandas as pd
support_log_grouped = pd.read_csv("/datasets/support_log_grouped.csv") #напишите ваш код здесь
print(support_log_grouped)


Напишите функцию alert_group_importance(row), работающую в соответствии со следующей логикой:
Если приоритет 'alert_group' средний, а важность 'importance' оценена в единицу, возвращать команду для отдела поддержки: 'обратить внимание';
Если приоритет высокий, а важность — единица, возвращать: 'высокий риск';
Если приоритет критичный, а важность — единица, возвращать: 'блокер';
Во всех остальных случаях выводить: 'в порядке очереди'.
Проверьте работоспособность функции для разных значений.
Чтобы тренажёр принял решение, оставьте в переменной row_values значение ['высокий', 1]. Не забудьте передать строке датафрейма названия столбцов.
Подсказка
`if alert_group=='средний': if importance==1: return 'обратить внимание'
if alert_group=='высокий': if importance== 1: return 'высокий риск'
if alert_group=='критичный': if importance== 1: return 'блокер'
return 'в порядке очереди'`

Решение:
import pandas as pd
support_log_grouped = pd.read_csv('/datasets/support_log_grouped.csv')

def alert_group_importance(row):
    if row['alert_group'] == 'средний':
        if row['importance'] == 1:
            return 'обратить внимание'
    if row['alert_group'] == 'высокий':
        if row['importance'] == 1:
            return 'высокий риск'
    if row['alert_group'] == 'критичный':
        if row['importance'] == 1:
            return 'блокер'
    return 'в порядке очереди'

row_values = ['высокий', 1]
row_columns = ['alert_group', 'importance']
row = pd.Series(data=row_values, index=row_columns)
print(alert_group_importance(row))
