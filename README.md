# -# Домашнее задание к занятию "«Кластеризация и балансировка нагрузки»" - `Саблин Никита`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

`было запущено 2 simole python сервера на портах 8001 и 8002`
```
....
listen stats  # веб-страница со статистикой
        bind                    :888
        mode                    http
        stats                   enable
        stats uri               /stats
        stats refresh           5s
        stats realm             Haproxy\ Statistics

frontend example  # секция фронтенд
        mode http
        bind :8088
        default_backend web_servers

backend web_servers    # секция бэкенд
        mode http
        balance roundrobin
        option httpchk
        http-check send meth GET uri /index.html
        server s1 127.0.0.1:8001 check
        server s2 127.0.0.1:8002 check


listen web_tcp

        bind :4000

        server s1 127.0.0.1:8001 check inter 3s
        server s2 127.0.0.1:8002 check inter 3s

```
<img width="563" height="211" alt="image" src="https://github.com/user-attachments/assets/4c03e9e6-c3fe-4482-a6e9-14c7eeb6fe09" />

https://drive.google.com/file/d/1133Hs1AofMLBaDhD5P-RSln7w-6uF-1I/view?usp=sharing

---

### Задание 2


<img width="781" height="400" alt="image" src="https://github.com/user-attachments/assets/9336e94f-be1a-4545-914f-bf94e8247978" />
<img width="1738" height="943" alt="image" src="https://github.com/user-attachments/assets/01f74fbf-3a05-4906-91d5-5a57f401703c" />
<img width="1738" height="943" alt="image" src="https://github.com/user-attachments/assets/3d736225-ff10-4d3e-92b3-589b407d3b31" />





---


![Название скриншота](ссылка на скриншот)`
