## Практическое задание 4: Статическая маршрутизация (последовательность маршрутизаторов)

### Файл для скачивания

[Практическое задание 4: Статическая маршрутизация (последовательность маршрутизаторов)](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%204.pkt)

### Описание

1. Составить схему сети из последовательности маршрутизаторов.
2. Каждый маршрутизатор соединяется хабами.
3. К каждому хабу подключено конечное устройство из своей сети.
4. Проверьте работоспособность сети.

### Реализация

1. Построить сеть.

<details>
  <summary>Схема</summary>
  <br>

  <img width="1346" height="413" alt="image" src="https://github.com/user-attachments/assets/642a9d3e-f716-4cb2-9abb-3f03c15f7f71" />
</details>

2. Настроить сеть 11.0.0.0/8.

<details>
  <summary>Сервер</summary>
  <br>
  
  <details>
    <summary>IP-configuration</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/a354b7b7-5515-46f2-860a-195f1422c40e" />
  </details>

  <details>
    <summary>DNS-записи</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/4c0ff830-f355-401a-b785-005ca165da93" />
  </details>

  <details>
    <summary>index.html</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/a07dc83e-7b18-45a4-ba4c-8bcdd2339b0f" />
  </details>
</details>

2. Настроить сеть 12.0.0.0/8.

<details>
  <summary>Сервер</summary>
  <br>
  
  <details>
    <summary>IP-configuration</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/97a4c24f-3c82-4045-b113-915c539bed7d" />
  </details>

  <details>
    <summary>DNS-записи</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/c7f9e4f6-cb3e-462e-b8a6-5d1ae04b1936" />
  </details>

  <details>
    <summary>index.html</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/192ccf87-f661-4293-8445-98953e9afd41" />
  </details>
</details>

3. Настроить маршрутизатор, соединяющий сеть 11.0.0.0/8, 12.0.0.0/8, 13.0.0.0/8.

<details>
  <summary>Маршрутизатор</summary>
  <br>

  <details>
    <summary>Новый слот</summary>
    <br>
    <img width="634" height="565" alt="image" src="https://github.com/user-attachments/assets/034cd047-6b84-4544-abc6-13c19aef16a9" />
    <br>
    В слот 0 вставим модуль WIC-1ENET, даёт возможность подключить ещё 1 провод (зажмите мышкой или тачпадом перетяните в слот 0). Данную процедуру делать при выключенном оборудовании. После включите оборудование.
  </details>
  
  <details>
    <summary>Сетевые интерфейсы</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/1689da91-cfdd-45c8-8888-77ccb41e6530" />
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/52809e4d-48ef-4042-bbeb-b8e9813ea08f" />
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/08d67edf-c072-4c7d-bb4b-c1964986c817" />
  </details>

  <details>
    <summary>Таблица</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/6a89f2e0-3a02-4a9f-81c3-6247ec53f9cf" />
  </details>
</details>

4. Настроить сеть 13.0.0.0/8 - провайдер.

<details>
  <summary>Сервер</summary>
  <br>
  
  <details>
    <summary>IP-configuration</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/1a922cbe-89cb-48a1-82ba-97b5c7035947" />
  </details>

  <details>
    <summary>DNS-записи</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/6882cd4d-1f47-4311-845f-bd318fd1a3f4" />
  </details>
</details>

4. Настроить сеть 14.0.0.0/8.

<details>
  <summary>ПК</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/27711f8a-7708-4840-bd10-20c1cd57039d" />
</details>

4. Настроить сеть 15.0.0.0/8.

<details>
  <summary>Сервер</summary>
  <br>
  
  <details>
    <summary>IP-configuration</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/4bf6ca2d-6684-4809-acec-8aa7e3b5e9c3" />
  </details>

  <details>
    <summary>DNS-записи</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/85f61f54-23af-4e4a-b8b9-8bde657941fd" />
  </details>

  <details>
    <summary>index.html</summary>
    <br>
    <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/a5dee50f-2c5d-4aa5-afa0-afbcdb9b7ee3" />
  </details>
</details>

5. Работоспобность сети.

<details>
  <summary>Проверка</summary>
  <br>

  <img width="639" height="938" alt="image" src="https://github.com/user-attachments/assets/a90d5b75-2a7e-459d-9e19-ddca4a052da5" />

  > TTL изначально 128, но уменьшается на 1, когда проходит маршрутизатор.
  
  > Request timed out обычно означает, что устроства обновляют свои ARP таблицы, чтобы затем послать ICMP.
  
  Откроем сайты:
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d44fdcb5-999b-4dac-b0cb-a9b8608a0ed5" />
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/31de8e4b-13d3-48a2-ab93-5b8be8358814" />
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d1eb23e6-d1c1-491a-a03c-332fbe08c2f9" />
</details>













