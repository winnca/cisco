## Практическое задание 8: VLAN, 2 коммутатора

### Файл для скачивания

[Практическое задание 8: VLAN, 2 коммутатора](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%208.pkt)

### Описание

1. Постройте схему сети: 4 пк, 2 коммутатора.
2. У каждого коммутатора 2 пк из разных VLAN.
3. Соедините 2 коммутатора.
4. Создайте 2 VLAN.
5. Доступны пк только из своей VLAN.

### Реализация

1. Создать сеть.

<details>
  <summary>Схема</summary>
  <br>

  <img width="542" height="402" alt="image" src="https://github.com/user-attachments/assets/52392e81-0377-4651-bfa9-d970bc9f02e3" />
</details>

2. ПК

<details>
  <summary>1</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/4b900635-a901-40e8-a764-284219f21188" />
</details>

<details>
  <summary>2</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/b82eab2b-4f42-41b4-a767-d650bb8dd179" />
</details>

<details>
  <summary>3</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/577e7217-8d68-4f32-bec5-3522e8035bfa" />
</details>

<details>
  <summary>4</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/4b900635-a901-40e8-a764-284219f21188" />
</details>

3. Коммутатор 1, пропишите следующие команды (как в предыдущем задании) для сетевых интерфейсов, подключённых к пк.

<details>
  <summary>CLI</summary>
  <br>

   * enable
   * conf t
   * vlan 20
   * interface fastEthernet 0/1
   * switchport mode access
   * switchport access vlan 20
   * exit
   * vlan 30
   * interface fastEthernet 0/2
   * switchport mode access
   * switchport access vlan 30
</details>

5. Сделать тоже самое для коммутатора 2

6. Теперь настроим транковые порты, зайдите в каждый коммутатор -> в разделе config выберете FastEthernet0/3 -> выберете транковый порт (скриншот)

<details>
  <summary>Транковый порт</summary>
  <br>

  <img width="470" height="163" alt="image" src="https://github.com/user-attachments/assets/cb7cdd16-ba0c-4f20-a381-006b15ab768c" />
</details>

6. Посмотрим на существующие VLAN и trunk порты.

<details>
  <summary>Транковые порты</summary>
  <br>

  <img width="639" height="576" alt="image" src="https://github.com/user-attachments/assets/39fd419a-eecf-44d3-bda8-3c5a76e6a688" />

  <img width="639" height="571" alt="image" src="https://github.com/user-attachments/assets/7d851e4f-03c9-42be-8a80-d7d70d5d3157" />
  
  > 802.1Q — это сетевой стандарт IEEE. Определяет ***способ тегирования*** (добавления специальной информации) кадров Ethernet для создания виртуальных локальных сетей (VLAN). В одной из практических заданий, применим данный формат, чтобы передавать данные между разными VLAN.
</details>

7. Пропингуем пк.

<details>
  <summary>ping</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/285ec28c-fcb6-4439-8cca-af0b3562b557" />

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d9b2f5f9-67ed-44f8-932a-ee4fdbece3f5" />  
</details>


