## Практическое задание 10: VTP

### Файла для скачивания

[Практическое задание 10: VTP только свои VLAN](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%2010%20%D1%82%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE%20%D1%81%D0%B2%D0%BE%D0%B8%20VLAN.pkt)

[Практическое задание 10: VTP маршрутизация](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%2010%20%D0%BC%D0%B0%D1%80%D1%88%D1%80%D1%83%D1%82%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F.pkt)

[Практическое задание 10: ACL](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%2010%20ACL.pkt)

### Терминология

<details>
  <summary>VTP</summary>
  <br>

  **VTP** - VLAN Trunking Protocol — это протокол для управления конфигурациями VLAN в локальных сетях, который позволяет автоматически синхронизировать базу данных VLAN между коммутаторами.

  * Основные режимы работы: клиент и сервер.

  * На сервере мы создаём vlan. У сервера есть домен. Если прописать разные домены для клиента и сервера, клиент инфу от него не получит.

  * Клиент же с одинаковым доменом получит обновлённую бд от сервера о vlan.
  
  > На каждом коммутаторе настраиваются порты доступа со своим/своими vlan.
</details>

<details>
  <summary>ACL</summary>
  <br>

  **ACL** - списки доступа, применяемые на коммутаторах и маршрутизаторах.
  
  + Задают критерии фильтрации в списке опций разрешения и запрета.
  
  + ***permit*** – разрешить.
  + ***deny*** – запретить.
  
  Т.е. либо пропускает пакет по сети, либо нет. Списки распространяются, как на входящий, так и на исходящий трафик.
  
  + ***in*** – на входящий трафик.
  + ***out*** – на исходящий трафик.
</details>

</br>

### Описание
1. Построить сеть.

<details>
  <summary>Схема</summary>
  <br>

  <img width="734" height="439" alt="image" src="https://github.com/user-attachments/assets/40d9f3f6-6def-4401-9a8b-ecb5170f23ad" />
</details>

2. Для каждого vlan доступны только его узлы и сервер.

</br>

### Реализация

1. ПК

<details>
  <summary>0</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/83d13bc2-92c4-49b7-afc9-41450ed76438" />
</details>

<details>
  <summary>1</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/916bd57c-fc3a-45c4-a018-3047d62a82b1" />
</details>

<details>
  <summary>2</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/0cdb87f3-3708-4ae7-992a-b3205944bafd" />
</details>

<details>
  <summary>3</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/8c5c0a47-cd80-4637-836b-3452bff12f49" />
</details>

<details>
  <summary>4</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/e05b05df-2d0b-4a70-a7d8-cac6daafd557" />
</details>

<details>
  <summary>5</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/64f99977-bbb3-45c1-b7eb-ae34baace9ed" />
</details>

2. Сервер

<details>
  <summary>IP-configuration</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/3ba50861-8469-4f3e-a010-3a308a7cc5a2" />
</details>

3. Настроим коммутатор, который будет vtp сервером, а также делаем все задействованные порты транковыми. Но вначале создадим на нём VLAN.

<details>
  <summary>VTP server</summary>
  <br>

   * enable
   
   * conf t
   
   * vlan 10
   * exit
   
   * vlan 11
   * exit
   
   * vlan 12
   * exit
   
   * vlan 13
   * exit
   
   * vtp domain HOME = создаём домен.
   
   * vtp password HOME = задаём пароль для домена.
   
   * vtp mode server = делаем коммутатор vtp сервером.
   
   * exit 2 раза
   
   * sh vtp st = посмотрим информацию о vtp на коммутаторе.

   <img width="514" height="159" alt="image" src="https://github.com/user-attachments/assets/8ef07500-97f6-4131-8b1f-882b7b93b536" />

   * делаем порты транковыми (как в предыдущих заданиях)
</details>

4. Теперь настроим vtp клиентов (демонстрация только 1 коммутатора, остальные по аналогии со своим vlan).

<details>
  <summary>VTP clients</summary>
  <br>

   * enable
   
   * conf t
   
   * vtp domain HOME
   
   * vtp password HOME
   
   * vtp mode client = делаем коммутатор vtp клиентом.
   
   * exit 2 раза
   
   * sh vtp st = посмотрим информацию о vtp на коммутаторе.
   
   * sh vl br

   <img width="624" height="490" alt="image" src="https://github.com/user-attachments/assets/8057c79c-a3b3-4979-b99e-7579e7555bfc" />
</details>

5. Работоспобность сети.

<details>
  <summary>Проверка</summary>
  <br>

  <img width="639" height="886" alt="image" src="https://github.com/user-attachments/assets/0c50b57d-7571-4908-906e-36843a78af27" />

  > Видно, что для пк доступно устройство только из под своей vlan.
</details>

6. Настроим маршрутизацию на сервере. Тоже самое, что и на маршрутизаторе, но вместо привычных сетевых интерфейсов, используются интерфейсы vlan. Прописывем для него IP-адрес.

<details>
  <summary>Настройка</summary>
  <br>

  > После настройки интерфейсов, обязательно включите маршрутизацию (смотрите скриншот).

   * int vlan 10
   * ip address 10.10.0.1 255.255.0.0
   * exit
   
   * int vlan 11
   * ip address 10.11.0.1 255.255.0.0
   * exit
   
   * int vlan 12
   * ip address 10.12.0.1 255.255.0.0
   * exit
   
   * int vlan 13
   * ip address 10.13.0.1 255.255.0.0
   * exit
   
   * ip routing = включаем маршрутизацию
   * exit
</details>

7. Пропингуем пк.

<details>
  <summary>ping</summary>
  <br>

  <img width="639" height="981" alt="image" src="https://github.com/user-attachments/assets/142738e2-9354-43a0-a277-6ca753432ffd" />

  <img width="639" height="563" alt="image" src="https://github.com/user-attachments/assets/eadc56e4-19d6-48a0-8004-ec474f9dc0f6" />
  
  > Теперь все устройства доступны друг другу.
</details>

8. Применим "списки доступа" на коммутаторе-сервере, чтобы для каждого vlan были доступны только свои устройства и сервер.

<details>
  <summary>ACL</summary>
  <br>

   * в режиме конфигурации.
   
   * ip access-list extended 100 = создаём ACL расширенный с номером 100; размещать принято ближе к источнику (в данном контексте приемлимо). При совпадении правила из списка (сверху начинается проверка), проверка заканчивается.
   
   * permit ip any 10.10.0.0 0.0.0.255 = разрешить доступ всем к сети 10.10.0.0 /24.
   
   * permit ip 10.10.0.0 0.0.0.255 any = разрешить доступ сети 10.10.0.0 /24 доступ ко всем.
   
   * permit 10.11.0.0 0.0.0.255 10.11.0.0 0.0.0.255 = разрешить доступ из сети 10.11.0.0 /24 в эту же сеть.
   
   * permit 10.12.0.0 0.0.0.255 10.12.0.0 0.0.0.255 = разрешить доступ из сети 10.12.0.0 /24 в эту же сеть.
   
   * permit 10.13.0.0 0.0.0.255 10.13.0.0 0.0.0.255 = разрешить доступ из сети 10.13.0.0 /24 в эту же сеть.
   
   * exit
   
   * int vlan 10  
   * ip access-group 100 in = применим ACL на интерфейс vlan 10 на входящий трафик.
   * exit
   
   * int vlan 11
   * ip access-group 100 in
   * exit
   
   * int vlan 12
   * ip access-group 100 in
   * exit
   
   * int vlan 13
   * ip access-group 100 in
   * exit

  > Применяется wildcard mask: 0.0.0.255 предназначена для выбора всех IP-адресов в определенной сети, в то время как маска подсети 255.255.255.0 определяет границы этой сети.
  
  > Первые 3 октета должны точно совпадать с проверяемым IP-адресом. Последний октет может быть любым (сколько нужно адресов).
</details>

9. Работоспобность сети.

<details>
  <summary>Проверка</summary>
  <br>

  <img width="639" height="939" alt="image" src="https://github.com/user-attachments/assets/613fbd14-6194-46bc-852c-c6c5ae0acfcb" />
</details>
