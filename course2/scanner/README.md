
# Port Scanner

Простой инструмент для сканирования открытых портов на удаленных узлах.

## Требования

- Python 3.x
- PyQt5
- requests
- scapy
- libpcap

## Установка зависимостей

```bash
pip install PyQt5
pip install scapy
```

## Запуск приложения

```bash
sudo python main2.py
```

## Использование

1. Введите целевой IP-адрес в поле "Target IP".
2. Укажите диапазон портов с помощью "Start Port" и "End Port".
3. Выберите тип сканирования:
   - "Scan ports" для сканирования портов.
   - "Scan IP" для сканирования IP адреса.
4. Результаты сканирования будут отображены в виджете внизу страницы.
5. Для сохранения результатов, нажмите кнопку "Save Results" и выберите файл для сохранения.

## Примечания

- Убедитесь, что у вас есть необходимые разрешения и зависимости установлены перед запуском приложения.
- При возникновении ошибок попробуйте настроить виртуальную среду (venv) и запускать из неё.

