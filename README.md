# [JavaCore](Java%20Core/index.md)

## Основы

- модификаторы доступа
- типы данных
- наследование
- класс Object
- интерфейсы и абстрактные классы

## Исключения

- иерархия исключений
- проверяемые и непроверяемые исключения
- как создать свое исключение
- конструкция try-finally

## Коллекции

- иерархия коллекция, основные интерфейсы [Struchkov](https://struchkov.dev/blog/ru/java-collection-framework/)
- имплементация коллекций [GitHub](https://github.com/openjdk/jdk/tree/master/src/java.base/share/classes/java/util)
- алгоритмическая сложность операций над коллекциями [internal](<Java Core/Collections Operations Time Complexity>)

## Stream API

- зачем придумали stream api [Annimon](https://annimon.com/article/2778#stream)
- промежуточные и терминальные операторы map, filter, reduce,
  collect [Annimon](https://annimon.com/article/2778#intermediate-operators)
- функциональные
  интерфейсы [Jenkov](https://jenkov.com/tutorials/java-functional-programming/functional-interfaces.html)

## Многопоточность

- Класс Thread [Jenkov](https://jenkov.com/tutorials/java-concurrency/creating-and-starting-threads.html)
- блок synchronized [Jenkov](https://jenkov.com/tutorials/java-concurrency/synchronized.html)
- ключевое слово volatile [Jenkov](https://jenkov.com/tutorials/java-concurrency/volatile.html)
- атомики, принцип compare and swap [Jenkov](https://jenkov.com/tutorials/java-concurrency/compare-and-swap.html)
- Пулы потоков:
    - ThreadPool [Jenkov](https://jenkov.com/tutorials/java-concurrency/thread-pools.html)
    - ExecutorService  [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/executorservice.html)
    - ForkJoinPool [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/java-fork-and-join-forkjoinpool.html)
- Locks [Jenkov](https://jenkov.com/tutorials/java-concurrency/locks.html)
- Классы-синхронизаторы:
    - CountDownLatch [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/countdownlatch.html)
    - CyclicBarier [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/cyclicbarrier.html)
    - Phaser [Jenkov]()
    - Exchanger [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/exchanger.html)
    - Semaphore [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/semaphore.html)
- ThreadLocal [Jenkov](https://jenkov.com/tutorials/java-concurrency/threadlocal.html)
- Асинхронное выполнение
    - Future [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/java-future.html)
    - CompletableFuture  [Annimon](https://annimon.com/article/3462)
- Future, CompletableFuture [Jenkov]()
- Java Memory Model [Jenkov](https://jenkov.com/tutorials/java-concurrency/java-memory-model.html)
- Happens-before guarantee [Jenkov](https://jenkov.com/tutorials/java-concurrency/java-happens-before-guarantee.html)
- Проблемы многопоточного программирования:
    - RaceConditions [Jenkov](https://jenkov.com/tutorials/java-concurrency/race-conditions-and-critical-sections.html)
    - DeadLocks [Jenkov](https://jenkov.com/tutorials/java-concurrency/deadlock.html)
    - Starvation & Fairness [Jenkov](https://jenkov.com/tutorials/java-concurrency/starvation-and-fairness.html)
- Многопоточные коллекции:
    - BlockingQueue [Jenkov](https://jenkov.com/tutorials/java-concurrency/blocking-queues.html)
    - ConcurrentHashMap [Jenkov](https://jenkov.com/tutorials/java-util-concurrent/concurrentmap.html)

## [Устройство JVM]()

- Как работает Garbage collection
- Виды сборщиков мусора и в чем фича каждого
- Как устроена память java процесса

# [Spring](Spring\index)

- Жизненный цикл бина [Picture by @aplahuta](Spring/SpringBeanLifeCycle.jpg)
- @Transactional [Baeldung](https://www.baeldung.com/spring-transactional-propagation-isolation)

# [Базы данных](Database/index)

- ACID [LeftJoin](https://leftjoin.ru/all/acid-and-databases/)
- Индексы [Habr. RuVDS](https://habr.com/ru/companies/ruvds/articles/724066/)
- Аномалии данных, уровни изоляций транзакций [PostgresPro](https://postgrespro.ru/docs/postgrespro/10/transaction-iso)
- Пессимистичная и оптимистичная блокировка [internal](Database/PessimisticAndOptimisticLocking.md)
- уровни нормализации [Microsoft](https://learn.microsoft.com/ru-ru/office/troubleshoot/access/database-normalization-description)
- Оптимизация запросов [Youtube. Дорога Багов](https://www.youtube.com/watch?v=JCSv9RDP_lY)
- Offset vs Keyset Pagination [UseTheIndexLuke](https://use-the-index-luke.com/sql/partial-results/fetch-next-page)
- Connection Pool[internal](Database/ConnectionPool.md)

# [JPA & Hibernate](<JPA & Hibernate/index>)

# [Kafka]()

- Общие моменты [Habr. Купер](https://habr.com/ru/companies/kuper/articles/738634/)
- Consumer Metrics [kafka.apache.org](https://kafka.apache.org/20/generated/consumer_metrics.html)

# [Кэширование]()

# [Логирование и мониторинг]()

# [Docker]()

# [K8S]()

# [Алгоритмы и структуры данных]()

# [Паттерны проектирования и принципы разработки ]()

# [System Design]()