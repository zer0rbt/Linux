# Backup Daemon

Backup Daemon представляет собой демон для автоматического регулярного резервного копирования данных из одного каталога в другой.

## Как собрать

1. Клонируйте репозиторий и перейдите в каталог с исходным кодом.

```bash
git clone https://github.com/zer0rbt/Linux/course2/daemon
cd daemon
```

2. Создайте каталог для сборки и выполните сборку с помощью CMake.

```bash
mkdir build
cd build
cmake ..
make
cd ..
```

## Как настроить

1. Создайте конфигурационный файл `backup.ini` и укажите необходимые параметры.

```ini
[src]
path = /путь/к/исходному/каталогу

[dst]
path = /путь/к/каталогу/для/резервных/копий

[frequency]
sec = 3600
```

2. Скопируйте конфигурационный файл в `/etc/`.

```bash
sudo cp backup.ini /etc/
```

## Как установить как службу

1. Скопируйте файл службы `backup-daemon.service` в `/etc/systemd/system/`.

```bash
sudo cp backup-daemon.service /etc/systemd/system/
```

2. Перезагрузите systemd и запустите Backup Daemon.

```bash
sudo systemctl daemon-reload
sudo systemctl start backup-daemon
sudo systemctl enable backup-daemon
```

## Как управлять и мониторить

1. Для приостановки и возобновления демона используйте:

```bash
sudo systemctl kill -s SIGTSTP backup-daemon  # Приостановить
sudo systemctl kill -s SIGCONT backup-daemon  # Возобновить
```

2. Для остановки демона используйте:

```bash
sudo systemctl stop backup-daemon
```

3. Для просмотра логов используйте:

```bash
journalctl -u backup-daemon
```

## Дополнительные действия

В файле `backup_actions.sh` предоставлены скрипты для управления Backup Daemon из командной строки:

```bash
./backup_actions.sh start    # Запустить демона
./backup_actions.sh stop     # Остановить демона
./backup_actions.sh restart  # Перезапустить демона
./backup_actions.sh status   # Проверить статус демона
./backup_actions.sh build   # Сборка программы
```
