# Домашная работа №4. Настройка IPv6-адресов на сетевых устройствах
  Топология

![image](https://github.com/user-attachments/assets/62793421-e776-40d6-9889-00431164cbe6)


Таблица адресации
| Устройство | Интерфейс | IPv6-адрес | Link local IPv6-адрес | Длина префикса | Шлюз по умолчанию |
| ---------- | --------- | ---------- | --------------------- | ------------ | ----------------- |
| R1 | G0/0/0 | 2001:db8:acad:a::1 | fe80::1 | 64 | - |
|  | G0/0/1 | 2001:db8:acad:1::1 | fe80::1 | 64 | - |
| S1 | Vlan 1 | 2001:db8:acad:1::b | fe80::b | 64 | - |
| PC-A | NIC | 2001:db8:acad:1::3| SLACC | 64 | fe80::1 |
| PC-B | NIC | 2001:db8:acad:a::3 | SLACC | 64 | fe80::1 |

## Задачи
### Часть 1. Настройка топологии и конфигурация основных параметров маршрутизатора и коммутатора
### Часть 2. Ручная настройка IPv6-адресов
### Часть 3. Проверка сквозного соединения

## Решение 
### Для начала строим сеть как указано в топологии, далее настраиваем коммутатор и маршрутизатор базовые настройки как в предыдущих домашних заданиях
### Примеры настройки указаны ниже
![image](https://github.com/user-attachments/assets/ff02f3ff-5f00-4b58-9a06-4f0a69644078)

### 

### Настраиваем маршрутизатор согласно топологии и пропысываем интерфейсы g0/0 и g0/1 которые "смотрят" на PC-B и на наш коммутатор, это link-local адрес и сам ipv6 
![image](https://github.com/user-attachments/assets/7902c5a9-9c7c-4357-b37a-80898da000a2)


![image](https://github.com/user-attachments/assets/8d47921e-7c31-4a52-9081-c309fb079ec8)

### Так же настраиваем ipv6 и link-local коммутатору
![image](https://github.com/user-attachments/assets/0d78195e-1bb2-4509-a64b-32983258b105)

### В итоге мы настроили маршрутизатор и коммутатор по нашим данным из адресной таблице, а так же статические ipv6 адреса на PC-A и PC-B 
### Теперь проверяем сквозное подключение с PC-A на FE80::1. Это локальный адрес канала, назначенный G0/1 на R1 и так же на S1
![image](https://github.com/user-attachments/assets/0e331991-2c2f-4c43-b1fa-2fcf0ab1f80c)

### Эхо-запрос успешно отправлен с PC-B на PC-A и с PC-B отправляем эхо-запрос на локальный адрес канала G0/0 на R1.
![image](https://github.com/user-attachments/assets/0b864015-1bf1-4a1e-8619-0c7459f0a8de)














