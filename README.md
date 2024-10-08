# ite2024

## Что потребуется для участия в мастер-классе

1. Ноутбук с os windows/linux (желательно debian based)
2. Установленная платформа 1С (версия > 8.3.21, желательно самая последняя). Вполне подойдет community вариант лицензции. 
3. Установленный http клиент: postman или insomnia

## Подключение к брокеру

Адрес брокера: 

```bash
rc1a-2s9sm9ccoj0v6v5c.mdb.yandexcloud.net:9091
```

## Подключение через утилиту plumber

```bash
./plumber_win.exe read kafka --topics=testTopic --address="rc1a-2s9sm9ccoj0v6v5c.mdb.yandexcloud.net:9091" --continuous --use-tls --tls-skip-verify --sasl-username=ite2024  --sasl-password=ite2024TheBest
```

в параметре --topics нужно указать имя топика, на который будет подписан консьюмер утилиты plumber

## Устанавливаем сертификат

Linux:

```bash
mkdir -p /usr/local/share/ca-certificates/Yandex && \
wget "https://storage.yandexcloud.net/cloud-certs/CA.pem" \
     --output-document /usr/local/share/ca-certificates/Yandex/YandexInternalRootCA.crt && \
chmod 0655 /usr/local/share/ca-certificates/Yandex/YandexInternalRootCA.crt
```

Windows:

```ps
mkdir $HOME\.kafka; curl.exe -o $HOME\.kafka\YandexInternalRootCA.crt https://storage.yandexcloud.net/cloud-certs/CA.pem
```

## Общая информация

В мастер классе используется расширение [Kafka1CExtension](https://github.com/NuclearAPK/Kafka1CExtension), которое не является законченным и полноценным продуктом, а всего лишь показывает основные механики, методы и приемы работы с Kafka через внешнюю компоненту. Тем не менее, расширение содержит фреймворк, с помощью которого можно в своих продуктах/решениях построить стабильную и надежную интеграцию с Kafka.
