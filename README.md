# ansible-solar-battle
Коллекция ansible-плейбуков для кибербитв SOLAR (ЦИПР 2024, SOCForum 2023)

## Использованиеэ
1. Установите [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installation-guide)
2. ```sh
   cp inventory.ini.sample inventory.ini
   ```
3. Измените значения в `inventory.ini`
   - `old_password` - пароль от пользователя `admin` (из Excel-таблицы)
   - `new_password` - ваш новый пароль (для смены)
   - `new_user` - новый пользователь (плейбук создает нового пользователя)
   - `velociraptor_deb_link` - ссылка на DEB-установщик Velociraptor'а (если он у вас есть, поддерживает HTTP(S)/FTP `(http|https|ftp)://[user[:pass]]@host.domain[:port]/path`)
   - `kesl_link` и `klnagent_link` - ссылки на установщик KESL (поддерживает HTTP(S)/FTP `(http|https|ftp)://[user[:pass]]@host.domain[:port]/path`)
   - Для каждой машины (IP-адреса) установите список разрешенных портов (как в примере)
4. Запустите `ansible`:
   ```sh
   ansible-playbook -i inventory.ini playbook.yaml
   ```
> [!NOTE]
> Просмотрите `playbook.yaml` перед запуском и закомментируйте задачи, которые вы не планируете делать.

## _obsolete
* `molecule` в репозитории изначально предназначался для автоматизированного тестирования, но необходимости автоматизированного тестирования я не вижу, поэтому он не поддерживается
