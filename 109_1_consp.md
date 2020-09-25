**109.1 Основы интернет протоколов**

Студент должен продемонстрировать понимание сетей TCP/IP.

**Изучаем**:

-   классовую и бесклассовую адресацию;

-   маски подсетей;

-   публичные и частные адреса;

-   основные TCP и UDP порты и службы (20, 21, 22, 23, 25, 53, 80, 110,
    123, 139, 143, 161, 162, 389, 443, 465, 514, 636, 993, 995);

-   протоколы TCP, UDP, ICMP;

-   особенности IPv6 и отличие его от IPv4.

Большинство современных сетей, как частных, так и публичных (в том числе
интернет) построены на базе стека протоколов TCP/IP. Знакомство с этим
стеком протоколов позволяет говорить о готовности студентов управлять
сетевыми устройствами, службами и клиеннтами.

IPv4 адрес представляет собой четыре группы цифр (октетов, или восьми
двоичных разрядов), разделенных точкой. Каждый октет представлен в
десятичном виде и может принимать значения от 0 до 255.

***Например, 192.168.0.101***

*Рисунок 1. Пример получения десятичного значения адреса*

![C:\\Users\\semaev\\Desktop\\p1\\Слайд5.JPG](media/image2.jpeg){width="6.496527777777778in"
height="2.8625328083989503in"}

*Рисунок 2. Пример перевода из двоичной в десятичную систему счисления*

![C:\\Users\\semaev\\Desktop\\p1\\Слайд6.JPG](media/image3.jpeg){width="6.496527777777778in"
height="2.8625328083989503in"}

*Рисунок 3. Примеры перевода из десятичной в двоичную систему счисления*

![C:\\Users\\semaev\\Desktop\\p1\\Слайд7.JPG](media/image4.jpeg){width="6.496527777777778in"
height="2.8523818897637794in"}

*Рисунок 4. Формат маски сети*

![C:\\Users\\semaev\\Desktop\\p1\\Слайд8.JPG](media/image5.jpeg){width="6.496527777777778in"
height="2.8523818897637794in"}

*Рисунок 5. Пример маски 255.255.255.0.*

*Рисунок 6. Пример маски 255.255.0.0*

\_\_

[Сети TCP/IP изначально делились на пять классов.]{.ul}

![C:\\Users\\semaev\\Desktop\\p2\\Слайд3.JPG](media/image7.jpeg){width="6.520833333333333in"
height="2.3536132983377076in"}

*Рисунок 7. Классы сетей*

*Рисунок 8. Сети класса А*

![C:\\Users\\semaev\\Desktop\\p2\\Слайд5.JPG](media/image9.jpeg){width="6.496527777777778in"
height="2.6798173665791776in"}

*Рисунок 9. Сети класса B*

*Рисунок 10. Сети класса C*

![C:\\Users\\semaev\\Desktop\\p2\\Слайд7.JPG](media/image11.jpeg){width="6.496527777777778in"
height="1.7966961942257218in"}

*Рисунок 11. Сети класса D*

![C:\\Users\\semaev\\Desktop\\p2\\Слайд8.JPG](media/image12.jpeg){width="6.496527777777778in"
height="1.76624343832021in"}

*Рисунок 12. Сети класса E*

![C:\\Users\\semaev\\Desktop\\p2\\Слайд9.JPG](media/image13.jpeg){width="6.496527777777778in"
height="2.5884601924759405in"}

*Рисунок 13. Первые биты*

![C:\\Users\\semaev\\Desktop\\p2\\Слайд10.JPG](media/image14.jpeg){width="6.496527777777778in"
height="2.5580074365704286in"}

*Рисунок 14. Специальные адреса ipv4*

\_\_\_

**Классовая адресация** -- длина маски фиксирована целыми октетами,
определяет классы сетей.

**VLSM** (variable length subnet mask) -- маска переменной длины,
создает подсети.

**CIDR** (Classless Inter-Domain Routing) -- бесклассовая внутридоменная
маршрутизация, использующая VLSM, может адресовать блоки адресов.

![C:\\Users\\semaev\\Desktop\\p3\\Слайд3.JPG](media/image15.jpeg){width="6.496527777777778in"
height="2.57830927384077in"}

*Рисунок 15. Пример использования VLSM и CIDR*

![C:\\Users\\semaev\\Desktop\\p3\\Слайд4.JPG](media/image16.jpeg){width="6.496527777777778in"
height="2.669666447944007in"}

*Рисунок 16. Маска /24*

![C:\\Users\\semaev\\Desktop\\p3\\Слайд5.JPG](media/image17.jpeg){width="6.496527777777778in"
height="2.3752930883639545in"}

*Рисунок 17. Маска /25*

![C:\\Users\\semaev\\Desktop\\p3\\Слайд6.JPG](media/image18.jpeg){width="6.496527777777778in"
height="2.426046587926509in"}

*Рисунок 18. Маска /26*

![C:\\Users\\semaev\\Desktop\\p3\\Слайд7.JPG](media/image19.jpeg){width="6.496527777777778in"
height="2.7711756342957132in"}

*Рисунок 17. Последние биты маски*

![C:\\Users\\semaev\\Desktop\\p3\\Слайд8.JPG](media/image20.jpeg){width="6.496527777777778in"
height="1.6139807524059493in"}

*Рисунок 18. Маска /23*

![C:\\Users\\semaev\\Desktop\\p3\\Слайд9.JPG](media/image21.jpeg){width="6.496527777777778in"
height="1.573378171478565in"}

*Рисунок 19. Маска /22*

*\_\_\_*

Адреса ipv4 можно поделить на:

-   **Частные** (серые, локальные, внутренние) адреса не
    маршрутизируются в среде интернет.

-   **Публичные** (белые, внешние) адреса маршрутизируются в среде
    интернет.

К частным диапазонам адресов относятся:

-   10.(0-255).(0-255).(0-255)/8

-   172.(16-31).(0-255).(0-255)/12

-   192.168.(0-255).(0-255)/16

Для классификации сетевых протоколов была создана эталонная модель
взаимодействия открытых систем**: OSI/ISO**.

![C:\\Users\\semaev\\Desktop\\p4\\Слайд3.PNG](media/image22.png){width="6.496527777777778in"
height="3.2351662292213472in"}

*Рисунок 20. Модель ISO/OSI*

![C:\\Users\\semaev\\Desktop\\p4\\Слайд4.PNG](media/image23.png){width="2.875in"
height="2.6426771653543306in"}

*Рисунок 21. Соответствие моделей TCP/IP и OSI*

Основными протоколами, организующими работу стека TCP/IP являются:

-   **IP (Internet Protocol)** -- протокол, передающий данные пакетами,
    без гарантированной доставки.

-   **TСP (Transmission Control Protocol)** -- протокол, осуществляющий
    надежную передачу данных.

-   **UDP (User Datagram Protocol)** -- протокол, передающий данные без
    создания специальной среды.

-   **ICMP (Internet Control Message Protocol)** -- протокол,
    используемый для отправки сообщений.

\_\_\_

Взаимодействие устройств по сети осуществляется при помощи сетевых
служб, которые создают слушающие сокеты, привязанные к выделенным
портам.

**Сокет** -- программный интерфейс, предназначенный для обмена данными
по сети.

**Порт** -- число, определяющее программу или процесс на данном сетевом
адресе:

-   0-1023 - общеизвестные порты;

-   1024-49151 - зарегистрированные порты;

-   49152-65535 - динамические порты.

![C:\\Users\\semaev\\Desktop\\p5\\Слайд3.PNG](media/image24.png){width="4.006741032370954in"
height="2.03125in"}![C:\\Users\\semaev\\Desktop\\p5\\Слайд4.PNG](media/image25.png){width="4.025155293088364in"
height="1.9479166666666667in"}![C:\\Users\\semaev\\Desktop\\p5\\Слайд5.PNG](media/image26.png){width="3.9891152668416447in"
height="1.7030446194225721in"}

*Рисунок 22. Примеры портов и служб*

*\_\_\_*

IPv6 -- обновленная версия протокола IP, используемая сейчас во многих
технологиях и частично в интернете. Использует свою систему адресации.
Интересной задачей является организация совместной работы сетей на базе
ipv4 и ipv6.

![C:\\Users\\semaev\\Desktop\\p6\\Слайд2.JPG](media/image27.jpeg){width="6.496527777777778in"
height="2.410002187226597in"}

*Рисунок 23. Формат ipv6-адреса*

![C:\\Users\\semaev\\Desktop\\p6\\Слайд3.JPG](media/image28.jpeg){width="6.496527777777778in"
height="2.6323042432195973in"}

*Рисунок 24. Пример перевода в шестнадцатеричную систему счисления*

IPv6 адреса можно разделить на:

-   **Unicast** -- адрес конкретного интерфейса;

-   **Anycast** -- адрес группы интерфейсов (один получатель);

-   **Multicast** -- адрес группы интерфейсов (все получатели).

![C:\\Users\\semaev\\Desktop\\p6\\Слайд4.JPG](media/image29.jpeg){width="5.322916666666667in"
height="0.8162576552930884in"}

*Рисунок 25. Формат Unicast и Anycast адресов*

![C:\\Users\\semaev\\Desktop\\p6\\Слайд5.JPG](media/image30.jpeg){width="5.208333333333333in"
height="1.9434076990376203in"}

*Рисунок 26. Формат Link-local и Multicast адресов*

В свою очередь Unicast адреса делятся на:

-   **global** - соответствуют публичным ipv4 адресам (сейчас раздаются
    начинающиеся с 2000::/3);

-   **link-local** - соответствует автонастроенным при помощи APIPA ipv4
    адресам (начинается с FE80::/10);

-   **loopback** -- соответствует петлевым ipv4 адресам ( ::1/128 );

-   **unique-local** - соответствует внутренним адресам (начинается с
    FС00 и FD00).

-   **unspecified** -- неопределенный адрес (::/128);

-   **ipv4 embedded** -- встроенные адреса ipv4.

Для ipv6 адресов справедливы следующие правила записи:

-   одну или несколько групп нолей можно заменить на ::

-   ведущие (располагающиеся в начале блока) ноли можно не указывать.

![C:\\Users\\semaev\\Desktop\\p6\\Слайд7.JPG](media/image31.jpeg){width="4.758196631671041in"
height="1.7916666666666667in"}

*Рисунок 27. Пример записи ipv6 адресов*

Для совместного использования ipv4 и ipv6 можно воспользоваться:

-   **двойной стек** (одновременная поддержка обоих стеков);

-   **туннелированние** (перенос пакета ipv6 внутри ipv4);

-   **преобразование** (технология NAT64).

Основные преимущества ipv6:

1.  Большое адресное пространство.

2.  Автоконфигурация адресов.

3.  Постоянное наличие локальных адресов.

4.  Джамбограммы