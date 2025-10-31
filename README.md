# ssh-test
## КЕЙС 1. Установка и запуск OpenSSH

* Устанавливаем сервер **OpenSSH**:

```bash
sudo apt install openssh-server
```
* Проверяем статус через 
```bash
sudo service ssh status
```
и 
```bash
запускаем sudo service ssh start
```

![IMAGE 2025-10-31 11:24:59 PM](https://github.com/user-attachments/assets/07b66628-951a-4fc9-b21f-863b29a21954)

## КЕЙС 2
* Подключаемся к удаленному серверу. Логин student1, IP 172.17.0.2
![IMAGE 2025-10-31 11:25:02 PM](https://github.com/user-attachments/assets/d6121085-78da-405a-aedf-84ab8889c96e)

## КЕЙС 3
* Создаем файл
```bash
echo "hello from local" > ~/ssh-homework/testfile.txt
```

* Копируем на сервер
```bash
scp ~/ssh-test/testfile.txt student1@172.17.0.2:/home/student1/testfile_remote.txt
```

* На удаленном сервере
![IMAGE 2025-10-31 11:25:04 PM](https://github.com/user-attachments/assets/88e9dcc4-ef79-4c05-8bb1-edb4cd0f041b)

## КЕЙС 4
* Генерируем пару ключей
```bash
ssh-keygen -t e2559 -f -/.ssh/id_ed2559_sshtest -C "ssh-test"
```
* Смотрим ключи
```bash
ls -l -/.ssh/id_ed2559_sshtest*
```
* Копируем ключи на удаленный сервер 
```bash
ssh-copy-id -i -/.ssh/id_ed2559_pub student1@172.17.0.2
```
* Подключаемся без пароля
```bash
ssh student1@172.17.0.2
```
![IMAGE 2025-10-31 11:25:05 PM](https://github.com/user-attachments/assets/9cf782ee-8d33-49ba-b480-c4ab42c74e20)

