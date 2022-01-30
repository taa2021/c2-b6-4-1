# B6.4.1

## Задание

Ссылка: [здесь](./TASK.md)

## Решение

```
# Устанавливаем, запускаем сервис docker-а (НЕ включаем по умолчанию при загрузке ОС)
ansible-playbook playbooks/docker.yml

# (Опционально) устанавливаем сервис mysql (НЕ включаем по умолчанию при загрузке ОС)
# ansible-playbook playbooks/mysql-server--install.yml

# Запускаем сервис mysql
ansible-playbook playbooks/mysql-server--run.yml
```

## Проверка

```
for S in containerd mysql
do
    R=Err
    echo -n "${S} - "; systemctl show ${S} | grep -q ActiveState=active && R=Ok; echo ${R}
done
```
