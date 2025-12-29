#DevOpsLab_04 Ansible roles

Первым делом, организовала древовидную структуру будующей роли.

<img width="622" height="392" alt="image" src="https://github.com/user-attachments/assets/53c8cc18-2694-43fc-b98a-b35e9ce9a208" />

Была создана сама роль, которая устанавлиявает nginx с vhosts.

<img width="521" height="248" alt="image" src="https://github.com/user-attachments/assets/6abacde6-6a27-4769-8eea-b4c3ca08388c" />

Прописываем первую задачу в ./roles/nginx-vhosts/tasks/main.yml по установке NGINX на хост. В качестве второй задачи: копирование в цикле конфигурации для ВМ.

<img width="623" height="447" alt="image" src="https://github.com/user-attachments/assets/29064029-e9ea-424f-a077-2150e285056f" />

б) Затем создаются файлы site.conf.j2 и index.html.j2 с данными о страницах виртуального сайта

в) Отдельно создается скрипт run_playbook.sh, который помогает запускать плейбук к ролью

Запускаем скрипт плейбука

<img width="837" height="619" alt="image" src="https://github.com/user-attachments/assets/f8f6bf90-a6d9-4ffe-9bfc-5c9efdefdfbe" />

Производим проверку с командной сроки указанем HTTP заголовок host.

<img width="754" height="439" alt="image" src="https://github.com/user-attachments/assets/8b870c67-9ea2-4d81-b308-be14bda34a60" />

Обманываем DNS, изменяя файл hosts, и заходим на сайт mehmat.ru

<img width="1280" height="831" alt="image" src="https://github.com/user-attachments/assets/143fad77-8ad7-48c5-a5f5-34d0b8907f4e" />

Правим /etc/hosts и проверяем через lynx по имени сайта
<img width="370" height="128" alt="image" src="https://github.com/user-attachments/assets/f315770c-f12d-4c7f-af41-24a0ab35adbb" />
<img width="593" height="110" alt="image" src="https://github.com/user-attachments/assets/e53ac10e-ab29-453d-b67c-f638a7aed9a4" />
<img width="843" height="586" alt="image" src="https://github.com/user-attachments/assets/a51bf360-4cbd-40a2-a294-478c4261e275" />

Создаем репозиторий lab_ansible_roles

<img width="1027" height="729" alt="image" src="https://github.com/user-attachments/assets/0459751b-67ec-492a-a622-2999e55b490c" />

Фиксируем изменения в локальном репозитории с сообщением “Files were added”, так же отправляем зафиксированные изменения из локальной ветки main в удалённый репозиторий origin.

<img width="829" height="496" alt="image" src="https://github.com/user-attachments/assets/e032ebac-d253-41a0-8c44-c0f53667137f" />

Создаём файл README.md и записываем в него текст. Потом добавляем файл README.md в индекс Git, фиксируем изменения. И в конце отправляем коммит в удалённый репозиторий.

<img width="835" height="469" alt="image" src="https://github.com/user-attachments/assets/97a09042-e383-4d53-a0c1-845c488d6f34" />

Активируем CI-пайплайны.

<img width="1010" height="848" alt="image" src="https://github.com/user-attachments/assets/0568ffaf-feac-4c08-b374-c0405fa0e768" />

Добавляем сценарий devops_course_pipeline.yml и добавляем сценарии CI в гит.
<img width="704" height="422" alt="image" src="https://github.com/user-attachments/assets/543758c6-9bb4-4be8-9674-1c9dc1263a24" />
<img width="830" height="332" alt="image" src="https://github.com/user-attachments/assets/69cce1a1-c4ec-43c3-9397-fea91aa00cbe" />

Потом добавляем новый "боевой" сценарий lint.yml и просматриваем, как он отрабатывает

