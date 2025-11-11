## Практическое задание 5: Динамическая маршрутизация (RIP)

### Файл для скачивания

[Практическое задание 5: Динамическая маршрутизация (RIP)](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%205.pkt)

### Описание

* Создать топлогию из 2 сетей.
* В каждой из них 1 пк, 1 коммутатор, 1 сервер.
* Использовать протокол RIP для маршрутизации.
* Проверить работоспособность сети.

### Реализация

1. Построить сеть.

<details>
  <summary>Схема</summary>
  <br>

  <img width="269" height="520" alt="image" src="https://github.com/user-attachments/assets/520e7ed4-911f-43e1-b575-c0ed5947a9fc" />
</details>

2. Настройки ПК.

<details>
  <summary>ПК11</summary>
  <br>
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/3a86bcc7-a91b-4fd0-bbe4-9c824d6e5ee2" />
</details>

<details>
  <summary>ПК12</summary>
  <br>
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/182f3569-9868-4517-adec-d0a79282ee59" />
</details>

3. Настройки маршрутизаторов.

<details>
  <summary>Маршрутизатор 1</summary>
  <br>
  <details>
    <summary>Cетеввые интерфейсы</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/7d070c58-b2cf-4ba9-9d0e-2f1b9a5fc39d" />
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/04072626-a4bb-4e56-b555-9d59d0d3171b" />
  </details>
</details>

<details>
  <summary>Маршрутизатор 2</summary>
  <br>

  <details>
    <summary>Сетевые интерфейсы</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/c9d099d2-c8b3-4073-bb27-45864fcde153" />
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d5eb3ce6-4c37-48ff-96d8-20bd41693462" />
  </details>
</details>

4. Настройка RIP

<details>
  <summary>Таблица 1</summary>
  <br>
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/6a253cd3-6429-400e-b821-ffed9b6fed4f" />
</details>

<details>
  <summary>Таблица 2</summary>
  <br>
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/358b6db2-a6fa-4cfc-80e0-de2d45cba235" />
</details>

5. Работоспособность сети.

<details>
  <summary>Проверка</summary>
  <br>
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/437a66da-aaa7-4a10-9fde-d75c8a9854b5" />
</details>
