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

2. **Удалите старые версии Docker**:  
   Если ранее были установлены старые версии Docker, их нужно удалить.
   ```bash
   sudo apt remove docker docker-engine docker.io containerd runc
   ```

3. **Установите необходимые зависимости**:  
   Установите пакеты для управления репозиториями через HTTPS.
   ```bash
   sudo apt install -y ca-certificates curl gnupg lsb-release
   ```

4. **Добавьте ключ GPG Docker**:  
   Добавьте официальный ключ репозитория Docker.
   ```bash
   sudo mkdir -p /etc/apt/keyrings
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   ```

5. **Добавьте репозиторий Docker**:  
   Добавьте Docker в список источников APT.
   ```bash
   echo \
     "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```

6. **Обновите список пакетов**:  
   Обновите список пакетов, чтобы включить новый репозиторий.
   ```bash
   sudo apt update
   ```

7. **Установите Docker Engine**:  
   Установите последнюю стабильную версию Docker и дополнительные утилиты.
   ```bash
   sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```

8. **Проверьте установку Docker**:  
   Убедитесь, что Docker установлен и работает.
   ```bash
   docker --version
   ```

9. **Запустите тестовый контейнер**:  
   Проверьте работу Docker, запустив тестовый контейнер.
   ```bash
   sudo docker run hello-world
   ```

10. **Добавьте пользователя в группу Docker (опционально)**:  
    Чтобы использовать Docker без `sudo`, добавьте текущего пользователя в группу Docker.
    ```bash
    sudo usermod -aG docker $USER
    ```

    Перезапустите терминал или выполните:
    ```bash
    newgrp docker
    ```

11. **Проверьте запуск Docker без sudo**:  
    Убедитесь, что команды Docker работают без `sudo`.
    ```bash
    docker run hello-world
    ```

---

```
