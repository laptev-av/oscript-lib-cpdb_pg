# oscript-lib-cpdb_pg Загрузка/ выгрузка ИБ PG

## Пример использования

```CMD
#Использовать fs
#Использовать pg_db
#Использовать logos

Перем Отказ;

Отказ = Ложь;

// Уровень лога Отладка
//pg_db.УстановитьУровеньЛога(УровниЛога.Отладка);
// по умолчанию Информация
pg_db.УстановитьУровеньЛога();

Параметры_PG = pg_db.ИнициализацияПараметров_PG();

Архив_Путь = "m:\tmp\pg_tmp";
БД_Имя_From = "1c_test_new_01";
БД_Имя_To = "1c_test_new_02";
Архив_ПолныйПуть = ОбъединитьПути(Архив_Путь, БД_Имя_From); 

pg_db.PG_Dump(БД_Имя_From, Архив_ПолныйПуть, Параметры_PG, Отказ);
pg_db.PG_Restore(БД_Имя_To, Архив_ПолныйПуть, Параметры_PG, Отказ);

```