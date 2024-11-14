# Домашнее задание к занятию "`Сетевое взаимодействие в K8S. Часть 1`" - `Макаров Денис"

---

## Задание 1. Создать Deployment и обеспечить доступ к контейнерам приложения по разным портам из другого Pod внутри кластера

### 1. Создать Deployment приложения, состоящего из двух контейнеров (nginx и multitool), с количеством реплик 3 шт.
Созданное пространстванство и Deployment представлены на скриншотах ниже:

![namespace](https://github.com/user-attachments/assets/f965b437-fb49-4b58-9139-60a9d8f5cd3b)

![ns](https://github.com/user-attachments/assets/eaab99af-4f29-447e-97c2-670a293faf6d)

![my_deployment](https://github.com/user-attachments/assets/36f8720b-28ee-44fb-bf73-c15ca5ba5884)

![zapusk deployment](https://github.com/user-attachments/assets/9c151710-1d50-4b82-af86-d6d2bbce5883)


### 2. Создать Service, который обеспечит доступ внутри кластера до контейнеров приложения из п.1 по порту 9001 — nginx 80, по 9002 — multitool 8080.
Созданный Service и выполенение задания представлено на скриншотах ниже:

![svc](https://github.com/user-attachments/assets/44f7b71c-2e13-4290-b5f0-4f3122dc8551)

![get svc](https://github.com/user-attachments/assets/b755152e-924c-4e15-bef9-c495f3f0c19e)

### 3. Создать отдельный Pod с приложением multitool и убедиться с помощью `curl`, что из пода есть доступ до приложения из п.1 по разным портам в разные контейнеры.

Созданный multitool и выполнение задания представлено на скриншотах ниже:

![test_multitool](https://github.com/user-attachments/assets/f3f1325f-a5b9-47b8-832d-8f95c8884745)

Ниже представлены тесты ответа ПОДов по ожидаемым портам:

![curl 80](https://github.com/user-attachments/assets/3fa4a2ce-c1b7-4398-9c55-4088f3b2aaf5)

![curl 8080 2](https://github.com/user-attachments/assets/0cef82c1-1f37-447b-8e9c-35f67573cbaf)

![curl 80 2](https://github.com/user-attachments/assets/f0d54850-eca3-4e34-91c4-08eede131c0b)

![curl 8080 2](https://github.com/user-attachments/assets/b7bd8c6d-a46f-4fba-8937-e378de1f988d)

![curl 8080 3](https://github.com/user-attachments/assets/83015a03-0422-4115-bd88-37bbd81e19a2)

![curl 8080](https://github.com/user-attachments/assets/c27e506b-4559-4de3-a261-dc7592b8daa2)

Ниже представлены тесты где Сервис отвечает по нужным портам:
![curl cluster 9001](https://github.com/user-attachments/assets/0b90859d-7c33-4695-a118-911910c6cf0b)

![curl cluster 9002](https://github.com/user-attachments/assets/dca5d805-ea4e-4330-82bf-b465175b58cb)

```
### 4. Продемонстрировать доступ с помощью `curl` по доменному имени сервиса.

Ниже представлены тесты по доменному имени сервиса:

![curl domain 9001](https://github.com/user-attachments/assets/bbc743dd-59ab-4f58-a4d5-eeb5b043de21)

![curl domain 9002](https://github.com/user-attachments/assets/9f6d28ac-8a97-45b5-9253-73f2b4317669)

### 5. Предоставить манифесты Deployment и Service в решении, а также скриншоты или вывод команды п.4.

------

## Задание 2. Создать Service и обеспечить доступ к приложениям снаружи кластера

### 1. Создать отдельный Service приложения из Задания 1 с возможностью доступа снаружи кластера к nginx, используя тип NodePort.
Созданный Service и выполнение задания представлено на скриншотах ниже:

![svc_nginx_nodeport](https://github.com/user-attachments/assets/3af30eec-35ba-49f6-a30d-ca06c503d711)

![zapusk pod deployment nodeport](https://github.com/user-attachments/assets/fc10ac0e-d056-4553-9a67-3bd316c55fa3)

### 2. Продемонстрировать доступ с помощью браузера или `curl` с локального компьютера.

![curl 30000](https://github.com/user-attachments/assets/1810a3c4-fed7-4c9d-900f-77ef1a04fd2a)

![curl 30001](https://github.com/user-attachments/assets/aee58acc-8382-4051-90b2-93d0e39b72ed)

![site 30000](https://github.com/user-attachments/assets/81c7f4db-f7e5-4e17-98be-4fff8ed612d3)

![site 30001](https://github.com/user-attachments/assets/94708f56-ea27-4fbd-b741-183babd396f6)


### 3. Предоставить манифест и Service в решении, а также скриншоты или вывод команды п.2.

------
