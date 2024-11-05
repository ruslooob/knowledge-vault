Пессимистичная блокировка - блокировка на уровне базы данных.
Можно наложить с помощью:
- уровней изоляции транзакций
- select for update
- explicit locking (https://postgrespro.ru/docs/postgresql/9.6/sql-lock)

Оптимистичная блокировка - блокировка на уровне приложения.
Реализауется с помощью version-колонки

- [Lost Update и способы решения. Vlad Mihalcea](https://vladmihalcea.com/a-beginners-guide-to-database-locking-and-the-lost-update-phenomena/)