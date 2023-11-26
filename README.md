**Ansible Playbook для установки и настройки Nginx, PHP, MySQL и phpMyAdmin**


Этот Ansible playbook автоматизирует процесс установки и настройки Nginx, PHP, MySQL и phpMyAdmin на целевом сервере. 

**Обратите внимание, что предполагается использование данного playbook'а в тестовой среде, и перед его выполнением необходимо добавить соответствующие сервера в файл инвентаря (inventory) и настроить доступ по SSH.**

**Предварительные требования**

Перед запуском этого playbook убедитесь, что:

Ваш целевой сервер доступен и имеет чистую операционную систему на основе Ubuntu.
Ansible установлен на машине, с которой вы будете запускать playbook.
Настройка инвентаря (Inventory)
Откройте файл inventory и добавьте IP-адреса или доменные имена ваших целевых серверов под соответствующими группами. 

Пример:

[web_servers]
server1 ansible_ssh_host=your_server1_ip ansible_ssh_user=your_ssh_user ansible_ssh_private_key_file=/path/to/your/private_key
server2 ansible_ssh_host=your_server2_ip ansible_ssh_user=your_ssh_user ansible_ssh_private_key_file=/path/to/your/private_key
Замените your_server1_ip, your_server2_ip, your_ssh_user и /path/to/your/private_key на соответствующие значения для ваших серверов и настроек SSH.


Измените переменные, такие как defdir, defconf, newconfig и db_pass в файле playbook'а в соответствии с вашими требованиями.
Убедитесь, что файл шаблона phpmyadmin.j2 и файл дампа SQL dump.sql доступны по указанным путям.
Запустите Ansible playbook:

**Структура Playbook'а**
playbook1.yml - запуск playbook'a
nginx_phpadmin_install: Основной файл playbook'а, содержащий задачи для установки и настройки.
phpmyadmin.j2: Файл шаблона Jinja2 для конфигурации phpMyAdmin в Nginx.
dump.sql: Файл дампа SQL с примером для базы данных MySQL.

**Примечания**

Этот playbook предназначен для систем на основе Ubuntu и может потребовать настройки для других дистрибутивов.
Пересмотрите задачи и переменные, чтобы настроить playbook в соответствии с вашей конкретной средой.
