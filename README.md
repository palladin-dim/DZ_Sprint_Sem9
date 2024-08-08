# Фреймворк Spring (семинары)

## Урок 9. Spring Cloud. Микросервисная архитектура.

#### Задание:<br> Создайте простую микросервисную архитектуру с использованием Spring Cloud.<br> Ваша архитектура должна включать хотя бы два микросервиса и службу распределения.<br><br>

### Описание<br>

- Создание двух простых микросервисов, используя Spring Cloud.<br>
- Реализация взаимодействия между микросервисами с использованием клиента Spring Cloud OpenFeign.<br>
- Добавление балансировщика нагрузки на стороне клиента с использованием Spring Cloud LoadBalancer.<br>

## Домашнее задание

<br>

1. Повторить код с урока.<br>
2. Запустить Eureka, Запустить 2 части (rest + page).<br>
3. В качестве результата работы прислать 1 скриншот со страницы localhost:8761,<br>
   где видно оба запущенных приложения (Instances currently registered with Eureka).<br>
4. **** Попробовать запустить несколько экземпляров (instances) timesheets-rest.<br>
5. **** Поизучать про RestTemplate. Попробовать завести его с использованием аннотации LoadBalanced.<br>
   <br>

## Решение

<br>

## Добавление зависемостей

Кроме зависимостей, необходимых для работы кода и Приложений, необходимо установить в файл pom.xml зависимости
eureka.<br>
В Модуль с Eureka Server установить зависимость:

```xml

<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-server</artifactId>
</dependency>

```

В Модули Приложений и других частей кода (Eureka Client) установить зависимость:

```xml

<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>

```

После успешного запуска частей (модулей), можно открыть страницу приложений в браузере.
<br>
### Проверка работы Eureka Server

http://localhost:8761
<br><br>

### Работа с приложениями

http://localhost:3333/home/timesheets
<br>

http://localhost:3322/home/timesheets

<br><br>

## Дополнительная информация

<br>

- Начальная страница локального сервера (Таблицы)<br><br>

  http://localhost:8080/login<br><br>
  или<br><br>
  http://localhost:8080/home/timesheets<br>

```
http://localhost:8080/home/timesheets

```

- Страница проекта, например :

```
http://localhost:8080/home/projects/1

```

- Страница записи, например :

```
http://localhost:8080/home/timesheets/1

```

## Сборка проект с помощью Maven

- Открыть командную строку и перейти в каталог проекта.
- Выполнить команду Maven для сборки проекта:

```shell
mvn clean install

```

- После успешной сборки. выполнить команду:

```shell
mvn spring-boot:run

```

- Чтобы проверить работу сервера Eureka Server, необходимо открыть веб-браузер и перейдите по адресу<br>
- http://localhost:8761

```
- http://localhost:8761 

```

- **Должна появится страница - консоль Eureka Server.**

<br><br><br>