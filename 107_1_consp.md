**107.1 Управление пользователями, группами и соответствующими
системными файлами**

Студент должен уметь создавать, удалять, приостанавливать и изменять
учетные записи пользователей.

**Изучаем**:

-   создание, изменение и удаление пользователей и групп;

-   управление информацией о пользователях и группах в соответствующих
    базах данных;

-   создание и управление специальными и ограниченными учетными
    записями.

Раньше пароли хранились в **/etc/passwd**, но это файл был всем доступен
для чтения, и теперь пароли лежат в **/etc/shadow**, доступной для
чтения только суперпользователю root (это и есть механизм теневых
паролей).

В **/etc/passwd** хранится информация о пользователях в следующем
формате:

***имя пользователя : пароль : uid : gid : сведения : домашняя папка :
оболочка***

Файл теневых паролей **/etc/shadow** имеет следующий формат (пароли
хранятся в зашифрованном виде):

***имя пользователя : пароль : время после смены пароля : минимальный
срок действия пароля : максимальный срок действия пароля : срок
предупреждения : время работы с истекшим паролем : срок для блокировки
пароля***

Файл с информацией о группах **/etc/group** (обычно пароль для группы не
указывается, но может пригодиться если пользователь захочет сменить
членство в группе):

***имя группы : пароль : gid : члены группы***

Файл теневых групп **/etc/gshadow** имеет следующий формат (доступы и
суть файла такая же, как и у файла теневых паролей):

***имя группы : пароль : gid : члены группы***

Если группа является основной для пользователя, то его логин не указан в
качестве члена группы в вышеприведённых файлах групп.

\_\_

Команда **useradd** позволяет создать пользователя (имеет множество
ключей, указывающих дополнительные параметры создания).

Для изменения свойств учетной записи пользователя (в том числе
блокировка, добавление в группу и т.д.) используется команда
**usermod**.

Для удаления ученой записи служит команда **userdel**.

Отдельно стоит упомянуть директорию **/etc/skel** в которой можно
создать необходимое дерево папок и файлов, которые будут автоматически
копироваться в профиль нового пользователя в момент его создания (при
указании ключа ***--m*** команде ***useradd***).

[*Например*:]{.ul}

***sudo useradd --d /home/leopold --m --G sambashare,semaev leopold***
(создать пользователя leopold, создать для него указанную домашнюю папку
/home/leopold и добавить его в группы sambashare и semaev);

***sudo passwd leopold*** (установить пользователю пароль);

***sudo usermod --L leopold*** (заблокировать учетную запись Леопольда);

***sudo userdel --r leopold*** (удалить пользователя Лепольд и его
домашнюю папку).

\_\_

Для создания группы используется команда **groupadd** c множеством
опциональных ключей (например, указание конкретного gid для группы).
Аналогично работе с пользователями для групп есть команды **groupmod**
(изменение свойств группы) и **groupdel** (удаление группы).

При помощи утилиты **chage** можно узнать информацию о сроках действия
учетной записи и изменить их параметры (например, срок действия пароля).
Например,

***sudo chage --E 2016-01-01*** (указать срок истечения действия пароля)

Утилита **getent** позволяет получать информацию о пользователях и
паролях из указанных баз данных. Например,

***sudo getent passwd semaev***