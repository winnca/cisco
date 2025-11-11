## Практическое задание 9: VLAN, 2 коммутатора и маршрутизатор

### Файла для скачивания

[Практическое задание 9: VLAN, 2 коммутатора и маршрутизатор](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%209.pkt)

### Описание
* Возьмите файл предыдущего задания.
1. Построить схему сети: 4 пк, 2 коммутатора.
2. У каждого коммутатора 2 пк из разных VLAN.
3. Соедините 2 коммутатора.
4. Добавьте маарщрутизатор и соедините с коммутаторами.
5. Создайте 2 VLAN.
6. Все пк доступны друг другу.

### Реализация

1. Создайте сеть.

<details>
  <summary>Схема</summary>
  <br>

  <img width="484" height="419" alt="image" src="https://github.com/user-attachments/assets/48b37bea-426d-4d0f-8a9c-f29c0eb36521" />
</details>

2. ПК со шлюзами для маршрутизатора.

<details>
  <summary>1</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/fbd6a10d-de17-44b7-9860-f61d6472cdb9" />
</details>

<details>
  <summary>2</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/0cb8682a-1583-490f-8bf4-db1879752642" />
</details>

<details>
  <summary>3</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/4c64595b-62cb-46af-a4d4-dc574966eadc" />
</details>

<details>
  <summary>4</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/00d342ea-be43-45b6-a609-4d7326f602af" />
</details>

3. Настроим порт 4 на обоих коммутаторах.

<details>
  <summary>CLI</summary>
  <br>

  Коммутатор 1:
   * enable
   * conf t
   * int fa0/4
   * switchport access vlan 20
   * exit 2 раза
   * sh vl br
  > Порт 4 добавится к vlan 20 при команде sh vl br
  
  Коммутатор 2:
     * enable
     * conf t
     * int fa0/4
     * switchport access vlan 30
     * exit 2 раза
     * sh vl br
  > Порт 4 добавится к vlan 30 при команде sh vl br
</details>

4. Маршрутизатор.

<details>
  <summary>Сетевые интерфейсы</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/f273f2f8-f11c-4f2e-b2eb-f8d84c7b09ba" />

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/91ff1570-64dd-47a0-941d-026dfc682eed" />
</details>

7. Работоспобность сети. Каждый пк должен быть доступен в сети.

<details>
  <summary>Проверка</summary>
  <br>

  <img width="639" height="770" alt="image" src="https://github.com/user-attachments/assets/5491fded-7979-4048-ac77-3c2617b1f12f" />
</details>


