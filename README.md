# CTF Infrastructure on Raspberry Pi 5

Бюджетная CTF-инфраструктура для проведения локальных соревнований по кибербезопасности на базе Raspberry Pi 5.

---

## Описание проекта

Данный проект представляет собой автономную CTF-экосистему, построенную на нескольких Raspberry Pi 5.  
Одна плата используется как центральный сервер с платформой CTFd, а остальные — как машины игроков.

Инфраструктура работает внутри локальной сети и позволяет безопасно проводить учебные соревнования, лабораторные работы и практические занятия по информационной безопасности.

---

## Репозиторий проекта

Исходный код, конфигурация инфраструктуры и дополнительные материалы проекта доступны в GitHub-репозитории:

https://github.com/flam0rozovy/CTF-system-based-on-Raspberry-Pi-5

---

## Цель проекта

Создать доступную и масштабируемую CTF-инфраструктуру для проведения соревнований и обучения кибербезопасности без использования дорогостоящего серверного оборудования.

---

## Целевые пользователи

- бюджетные образовательные учреждения  
- студенты и энтузиасты информационной безопасности  
- малые IT-стартапы  
- организаторы CTF-соревнований и олимпиад  

---

## Архитектура инфраструктуры

Инфраструктура построена по клиент-серверной архитектуре.

### Центральный сервер

**Устройство:** Raspberry Pi 5  
**Операционная система:** Ubuntu Server 24.04 LTS  

Используемое ПО:

- CTFd
- Docker
- Docker Compose
- MySQL
- Redis
- Python
- Gunicorn
- Git

---

### Машины игроков

**Устройство:** Raspberry Pi 5  
**Операционная система:** Kali Linux  

Основные инструменты:

- Nmap  
- Burp Suite  
- Metasploit Framework  
- John the Ripper  
- Wireshark  

---

# Скачивание проекта

Клонирование репозитория:

```bash
git clone https://github.com/flam0rozovy/CTF-system-based-on-Raspberry-Pi-5.git
```

Переход в директорию проекта:

```bash
cd CTF-system-based-on-Raspberry-Pi-5
```

---

# Установка программного обеспечения

## Установка Docker

```bash
sudo apt update && sudo apt upgrade -y

sudo apt install -y \
apt-transport-https \
ca-certificates \
curl \
software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo \
"deb [arch=$(dpkg --print-architecture) \
signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] \
https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

sudo apt install -y docker-ce docker-ce-cli containerd.io
```

Проверка установки:

```bash
docker --version
```

---

## Установка Docker Compose

```bash
sudo curl -L \
"https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" \
-o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose
```

Проверка установки:

```bash
docker-compose --version
```

---

# Развертывание CTFd

Клонирование репозитория CTFd:

```bash
git clone https://github.com/CTFd/CTFd.git
cd CTFd
```

Запуск платформы:

```bash
docker compose up -d
```

Проверка контейнеров:

```bash
docker ps
```

Остановка платформы:

```bash
docker compose down
```

Перезапуск:

```bash
docker compose restart
```

Просмотр логов:

```bash
docker compose logs -f
```

После запуска платформа будет доступна по адресу:

```text
http://localhost:8000
```

---

## Категории заданий

В инфраструктуре могут использоваться задачи следующих категорий:

- Web  
- Cryptography  
- Reverse Engineering  
- Steganography  
- Network Security  

---

## Тестирование

После развертывания инфраструктуры проводится тестовая CTF-игра, позволяющая проверить:

- регистрацию пользователей  
- загрузку задач  
- прием флагов  
- корректность таблицы лидеров  

---

## Преимущества решения

- низкая стоимость инфраструктуры  
- низкое энергопотребление  
- простота развертывания  
- масштабируемость  
- автономная работа в локальной сети  

---

## Источники

- https://docs.ctfd.io  
- https://ubuntu.com/download/raspberry-pi  
- https://www.kali.org  
- https://servermall.ru  
- https://unify-lab.ru  
