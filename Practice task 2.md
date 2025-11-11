## Практическое задание 2: DHCP, DNS, WEB server

### Файл для скачивания

[Практическое задание 2: DHCP, DNS, WEB server](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%202.pkt)

### Описание

* Построить сеть с 3 серверами (DNS, DHCP, WEB) и 1 пк.
* Используйте промежуточное устройство для соединения конечных устройств.
* Устройства должны быть доступны друг другу. ПК должен открывать сайт с браузера.

### Реализация

1. Построить сеть.

<details>
  <summary>Схема</summary>
  <br>

  <img width="558" height="370" alt="image" src="https://github.com/user-attachments/assets/9daafb87-d2b3-4775-bfdb-cd657f922dba" />
</details>

2. Задать IP-configuration и названия в Config -> Global Setting -> Display name для пк и серверов.

<details>
  <summary>ПК (DHCP)</summary>
  <br>

  Для пк выбрать DHCP.

  <img width="348" height="257" alt="image" src="https://github.com/user-attachments/assets/24bb33fe-fb85-451e-b10f-6f364b4bdebc" />
</details>

<details>
  <summary>DNS</summary>
  <br>

  Для DNS сервера.

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/30aee347-3a7d-4e28-97f7-8424ac94f070" />
</details>

<details>
  <summary>DHCP</summary>
  <br>

  Для DHCP сервера.
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d526f330-1916-4ab7-815b-4fada4c7c941" />
</details>

<details>
  <summary>WEB</summary>
  <br>

  Для WEB сервера.
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/fb8a94ae-48f4-4831-b465-a4e317efc5f0" />
</details>

3. Настроим для каждого сервера свои службы.

<details>
  <summary>Сервер DNS-записи</summary>
  <br>

  Для DNS сервера.
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/2a81b629-13dd-492b-a5bd-b8c3f1ba0e1f" />
</details>

<details>
  <summary>DNS</summary>
  <br>

   * При запросе в интернете, когда вбиваем в поисковую строку браузера название хоста. Происходит следующее (в упрощённом варианте):

   > 1. ПК связывается с DNS сервером, отправляет запрос, чтобы узнать его IP-адрес, куда ему нужно обратиться.
   > 2. DNS сервер в ответе для пк даёт IP-адрес.
   > 3. ПК делает запросу WEB серверу по его IP-адресу, в ответе получает, к примеру, HTML-документ.
   
   * A Record - связываем доменное имя сайта с IP-адресом, где расположен HTML-файл.
   
   > Речь идёт в примере о домене верхнего уровня (ru, com, org,...) и домене второго уровня (web-server, yandex, vk, ...).
   
   > web-server (хост) = 10.0.0.3 
   
   * CNAME - связываем доменное имя с поддоменом.
   
   > www - используется в интернете.
   
   > www.web-server.ru = c хост именем web-server.
   
   Реализация DNS может быть куда обширнее, чем представленно здесь. Например:
   
   > Когда ПК связывается с DNS серверами, путь запроса может быть следующим:
   
   > 1. Запрос прийдёт на сервер ***резолвер*** = рекурсивный сервер, пройдётся по всем серверам DNS, чтобы найти нужный IP.
   
   > 2. С резолвера прийдёт на ***корневой*** сервер = обладает информацией, куда нужно дальше стучаться, зависит от домена верхнего уровня. Если .com, то отправит на сервер, отвечающий за домены верхнего уровня .com.
   
   > 3. С корневого сервера прийдёт на ***сервер, отвечающий за домен верхнего уровня*** (.com). Он обладает информацией к какому ***авторитетному серверу*** обратиться за IP-адресом соответствующего домена.
   
   > **Резолвер** может использовать свой кэш для ускорения процессов выдачи IP-адресов.
</details>

<details>
  <summary>Сервер DHCP настройка</summary>
  <br>

  Для DHCP сервера. Для пк выдадут свободный IP-адрес, также маску подсети и DNS сервер (куда ему следует посылать DNS-запрос).

  * DHCP - помогает выдават IP-адреса конечным устройствам.
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/aa5e3ff2-1297-431d-bc28-11346d66fcb5" />
</details>

<details>
  <summary>Сервер WEB index.html</summary>
  <br>

  Для WEB сервера. Нажмите на HTTP -> index.html (кнопка edit) -> можете редактировать файл.
  
  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/0ac3f935-177b-4ec9-91e1-84060c8aaa7c" />
</details>

4. Теперь зона доступности DNS службы на WEB сервере.

<details>
  <summary>Проверка</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/a329b59e-cce9-4c1d-a7d3-d5c3f3ad7965" />

   > Записи server, address = DNS сервер, к которому обращались.
   
   > Остальные записи говорят о том, что это неавторитетный сервер, у которого есть нужные нам DNS-записи. Далее указан домен и IP, а также **aliases** (псевдоним, обычно отличается).
</details>

5. Теперь выдадим IP-configuration.

<details>
  <summary>Конфигурируем</summary>
  <br>

   Зайдите в Commant promt -> введите ipconfig /release (сброс параметров) -> введите ipconfig/renew.
   
   <img width="378" height="318" alt="image" src="https://github.com/user-attachments/assets/d6d05b09-fbd0-4093-9c0e-85ec2e688261" />
</details>

6. Пошлём ping с пк.

<details>
  <summary>Проверка доступности устройств</summary>
  <br>

  <img width="639" height="747" alt="image" src="https://github.com/user-attachments/assets/3a09d6b2-4454-4940-8184-b2f733a3c505" />
</details>

7. На пк в бразуере введите www.web-server.ru.

<details>
  <summary>Браузер</summary>
  <br>

  <img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/b956bffb-cda9-493c-a134-17df4b381f8f" />
</details>

> Для подобной работы, можете объединить DNS и WEB сервер (эффективнее).
