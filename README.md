# HOMEWORK-SOLUTIONS-7

Class explanation: Iterator section (Обьяснение кода)
Class Episode — представляет один эпизод с названием и длительностью. Просто контейнер с геттерами.
EpisodeView — обёртка над Episode, позволяющая «начать просмотр» с определённой секунды (например, чтобы пропустить интро).
EpisodeIterator — интерфейс с методами hasNext() и next(), задаёт внешний итератор.
Season — содержит список эпизодов. Поддерживает добавление и создание трёх видов итераторов:
SeasonIterator — обычный порядок (как добавлены).
ReverseSeasonIterator — в обратном порядке.
ShuffleSeasonIterator — перемешанный порядок (по seed, чтобы был воспроизводим). Также реализует Iterable<Episode>, чтобы можно было использовать for (Episode e : season).


