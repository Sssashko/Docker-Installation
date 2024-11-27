# Инструкция по установке Docker

## Системные требования
- **ОС**: Linux (Ubuntu 20.04+), Windows 10/11, macOS 10.15+
- **RAM**: Минимум 2 ГБ
- **Диск**: Свободно 2 ГБ

## Установка на Ubuntu

1. **Обновите пакеты**:  
   Убедитесь, что все установленные пакеты на вашей системе обновлены.
   ```bash
   sudo apt update && sudo apt upgrade -y
Удалите старые версии Docker:
Если ранее были установлены старые версии Docker, их нужно удалить.

bash
Копировать код
sudo apt remove docker docker-engine docker.io containerd runc
Установите необходимые зависимости:
Установите пакеты для управления репозиториями через HTTPS.

bash
Копировать код
sudo apt install -y ca-certificates curl gnupg lsb-release
Добавьте ключ GPG Docker:
Добавьте официальный ключ репозитория Docker.

bash
Копировать код
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
Добавьте репозиторий Docker:
Добавьте Docker в список источников APT.

bash
Копировать код
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
Обновите список пакетов:
Обновите список пакетов, чтобы включить новый репозиторий.

bash
Копировать код
sudo apt update
Установите Docker Engine:
Установите последнюю стабильную версию Docker и дополнительные утилиты.

bash
Копировать код
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
Проверьте установку Docker:
Убедитесь, что Docker установлен и работает.

bash
Копировать код
docker --version
Запустите тестовый контейнер:
Проверьте работу Docker, запустив тестовый контейнер.

bash
Копировать код
sudo docker run hello-world
Добавьте пользователя в группу Docker (опционально):
Чтобы использовать Docker без sudo, добавьте текущего пользователя в группу Docker.

bash
Копировать код
sudo usermod -aG docker $USER
Перезапустите терминал или выполните:

bash
Копировать код
newgrp docker
Проверьте запуск Docker без sudo:
Убедитесь, что команды Docker работают без sudo.

bash
Копировать код
docker run hello-world
