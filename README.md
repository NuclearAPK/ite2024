# ite2024


## Подключение к брокеру

Адрес брокера: rc1a-2s9sm9ccoj0v6v5c.mdb.yandexcloud.net:9091

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


