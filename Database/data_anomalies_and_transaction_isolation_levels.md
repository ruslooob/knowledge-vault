При параллельном выполнении транзакций возможны следующие феномены:

1. Потерянное обновление (lost update). Когда разные транзакции одновременно изменяют одни и те же данные, то после
   фиксации изменений может оказаться, что одна транзакция перезаписала данные, обновленные и зафиксированные
   другой транзакцией.
2. «Грязное» чтение (dirty read). Транзакция читает данные, измененные параллельной транзакцией, которая еще не
   завершилась. Если эта параллельная транзакция в итоге будет отменена, тогда окажется, что первая транзакция прочитала
   данные, которых нет в системе.
3. Неповторяющееся чтение (non-repeatable read). При повторном чтении тех же самых данных в рамках одной транзакции
   оказывается, что другая транзакция успела изменить и зафиксировать эти данные. В результате тот же самый запрос
   выдает другой результат.
4. Фантомное чтение (phantom read). Транзакция повторно выбирает множество строк в соответствии с одним и тем же
   критерием. В интервале времени между выполнением этих выборок другая транзакция добавляет новые строки и успешно
   фиксирует изменения. В результате при выполнении повторной выборки в первой транзакции может быть получено другое
   множество строк.
5. Аномалия сериализации (serialization anomaly). Результат успешной фиксации группы транзакций, выполняющихся
   параллельно, не совпадает с результатом ни одного из возможных вариантов упорядочения этих транзакций, если бы они
   выполнялись последовательно.

Поясним кратко, в чем состоит смысл концепции сериализации. Для двух транзакций, скажем, A и B, возможны только два
варианта упорядочения при их последовательном выполнении: сначала A, затем B или сначала B, затем A. Причем результаты
реализации двух вариантов могут в общем случае не совпадать. Например, при выполнении двух банковских операций —
внесения некоторой суммы денег на какой-то счет и начисления процентов по этому счету — важен порядок выполнения
операций. Если первой операцией будет увеличение суммы на счете, а второй — начисление процентов, тогда итоговая сумма
будет больше, чем при противоположном порядке выполнения этих операций. Если описанные операции выполняются в рамках
двух различных транзакций, то оказываются возможными различные итоговые результаты, зависящие от порядка их выполнения.

Сериализация двух транзакций при их параллельном выполнении означает, что полученный результат будет соответствовать
одному из двух возможных вариантов упорядочения транзакций при их последовательном выполнении. При этом нельзя сказать
точно, какой из вариантов будет реализован.

Если распространить эти рассуждения на случай, когда параллельно выполняется более двух транзакций, тогда результат их
параллельного выполнения также должен быть таким, каким он был бы в случае выбора некоторого варианта упорядочения
транзакций, если бы они выполнялись последовательно, одна за другой. Конечно,
чем больше транзакций, тем больше вариантов их упорядочения. Концепция сериализации не предписывает выбора какого-то
определенного варианта. Речь идет лишь об одном из них.

В том случае, если СУБД не сможет гарантировать успешную сериализацию группы параллельных транзакций, тогда некоторые из
них могут быть завершены с ошибкой. Эти транзакции придется выполнить повторно.

Для конкретизации степени независимости параллельных транзакций вводится понятие уровня изоляции транзакций. Каждый
уровень характеризуется перечнем тех феноменов, которые на данном уровне не допускаются.

Всего в стандарте SQL предусмотрено четыре уровня. Каждый более высокий уровень включает в себя все возможности
предыдущего.

1. Read Uncommitted. Это самый низкий уровень изоляции. Согласно стандарту SQL на этом уровне допускается чтение
   «грязных» (незафиксированных) данных. Однако в PostgreSQL требования, предъявляемые к этому уровню, более строгие,
   чем в стандарте: чтение «грязных» данных на этом уровне не допускается.
2. Read Committed. Не допускается чтение «грязных» (незафиксированных) данных. Таким образом, в PostgreSQL уровень Read
   Uncommitted совпадает с уровнем Read Committed. Транзакция может видеть только те незафиксированные изменения данных,
   которые произведены в ходе выполнения ее самой.
3. Repeatable Read. Не допускается чтение «грязных» (незафиксированных) данных и неповторяющееся чтение. В PostgreSQL на
   этом уровне не допускается также фантомное чтение. Таким образом, реализация этого уровня является более строгой, чем
   того требует стандарт SQL. Это не противоречит стандарту.
4. Serializable. Не допускается ни один из феноменов, перечисленных выше, в том числе и аномалии сериализации.

Е.П. Моргунов "Основы языка SQL". Глава 9: Транзакции
https://edu.postgrespro.ru/sql_primer.pdf