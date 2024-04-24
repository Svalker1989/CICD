# Домашнее задание к занятию 10 «Jenkins»

## Подготовка к выполнению

1. Создать два VM: для jenkins-master и jenkins-agent.
2. Установить Jenkins при помощи playbook.
3. Запустить и проверить работоспособность.
4. Сделать первоначальную настройку.

## Основная часть

1. Сделать Freestyle Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.
![](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/1.PNG)  
Шаги сборки:  
![](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/1_1.PNG)  
3. Сделать Declarative Pipeline Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.
![](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/2.PNG)  
4. Перенести Declarative Pipeline в репозиторий в файл `Jenkinsfile`.
![](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/3.PNG)  
Скрипт пайплайна:  
![declarative](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/pipeline/declarative)  
5. Создать Multibranch Pipeline на запуск `Jenkinsfile` из репозитория.
6. Создать Scripted Pipeline, наполнить его скриптом из [pipeline](./pipeline).
7. Внести необходимые изменения, чтобы Pipeline запускал `ansible-playbook` без флагов `--check --diff`, если не установлен параметр при запуске джобы (prod_run = True). По умолчанию параметр имеет значение False и запускает прогон с флагами `--check --diff`.
Создан параметр:  
![4](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/4.PNG)  
Пайплайн успешно собран:  
![5](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/5.PNG)  
Скрипт пайплайна:  
[scripted](https://github.com/Svalker1989/CICD/blob/master/09-ci-04-jenkins/pipeline/scripted)  
8. Проверить работоспособность, исправить ошибки, исправленный Pipeline вложить в репозиторий в файл `ScriptedJenkinsfile`.
9. Отправить ссылку на репозиторий с ролью и Declarative Pipeline и Scripted Pipeline.
10. Сопроводите процесс настройки скриншотами для каждого пункта задания!!

## Необязательная часть

1. Создать скрипт на groovy, который будет собирать все Job, завершившиеся хотя бы раз неуспешно. Добавить скрипт в репозиторий с решением и названием `AllJobFailure.groovy`.
2. Создать Scripted Pipeline так, чтобы он мог сначала запустить через Yandex Cloud CLI необходимое количество инстансов, прописать их в инвентори плейбука и после этого запускать плейбук. Мы должны при нажатии кнопки получить готовую к использованию систему.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
