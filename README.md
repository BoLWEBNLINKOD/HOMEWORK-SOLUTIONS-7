# HOMEWORK-SOLUTIONS-7

Class explanation: Iterator section (Обьяснение кода)
Class Episode — представляет один эпизод с названием и длительностью. Просто контейнер с геттерами.
EpisodeView — обёртка над Episode, позволяющая «начать просмотр» с определённой секунды (например, чтобы пропустить интро).
EpisodeIterator — интерфейс с методами hasNext() и next(), задаёт внешний итератор.
Season — содержит список эпизодов. Поддерживает добавление и создание трёх видов итераторов:
SeasonIterator — обычный порядок (как добавлены).
ReverseSeasonIterator — в обратном порядке.
ShuffleSeasonIterator — перемешанный порядок (по seed, чтобы был воспроизводим). Также реализует Iterable<Episode>, чтобы можно было использовать for (Episode e : season).
Series — сериал, содержащий список сезонов. Предоставляет BingeIterator, который позволяет пройти все серии всех сезонов подряд — как на Netflix без паузы между
сезонами.
SkipIntroIterator — обёртка над EpisodeIterator, которая возвращает EpisodeView и начинает воспроизведение с n-й секунды (декоратор).

TowerMediator — интерфейс диспетчерской башни. Управляет вещанием и доступом к взлётной полосе.
Aircraft — абстрактный класс для всех воздушных судов. Хранит id, уровень топлива, ссылку на диспетчера и базовые методы отправки/получения сообщений.
PassengerPlane, CargoPlane, Helicopter — конкретные виды Aircraft с переопределённым методом receive(String msg) — просто печатают сообщения на консоль.
ControlTower — реализует TowerMediator. Поддерживает очереди посадки/взлёта и централизованно управляет сообщениями. Обрабатывает экстренные случаи (MAYDAY) — сразу пропускает самолёт вперёд и останавливает остальных.
Все эти классы связаны собой и выводят такой пример при запуске главного класса main:
Normal order:
Pilot
Episode 2

Reverse order:
Episode 2
Pilot

Shuffle order:
Episode 2
Pilot

PassengerPlane PX101 received: PX101 says: Requesting landing
Runway granted to PX101
CargoPlane CX999 received: CX999 says: Requesting landing
CX999 added to landing queue.
Emergency from HX777!
PassengerPlane PX101 received: EMERGENCY: HX777 landing now. Hold position.
CargoPlane CX999 received: EMERGENCY: HX777 landing now. Hold position.
Helicopter HX777 received: EMERGENCY: HX777 landing now. Hold position.
Runway granted to HX777
