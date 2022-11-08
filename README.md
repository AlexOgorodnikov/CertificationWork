Подготовка инфраструктуры к выполнению проекта.

1. Установка необходимого ПО. На управляющей ноде установлено следующее ПО:
  - Jenkins
  - Terraform
  - Python(включая все необходимые модули для работы Ansible)
  - Ansible
  - Awscli

2. Предварительные настройки ПО:
  - Добавление необходимых credentials в Jenkins
  - Конфигурация Awscli

3. Подготовка файлов для сборки и запуска приложения
  - Подготовен Dockerfile app-server https://github.com/AlexOgorodnikov/AppDockerfile.git


После выполнения проекта приложение доступно по ссылке app-server.instance.public.dns:8080/hello-1.0/