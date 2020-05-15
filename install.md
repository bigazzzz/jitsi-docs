### Инсталяция jitsi

(c)https://community.jitsi.org/t/changing-the-default-language/15978

Устанавливаем OpenJDK Java Runtime Environment (JRE) 8
Для платформы Jitsi Meet требуется установка Java Runtime Environment. Выполняем команду в терминале:

sudo apt install -y openjdk-8-jre-headless nginx

cd

wget -qO - https://download.jitsi.org/jitsi-key.gpg.key | sudo apt-key add -

sudo sh -c "echo 'deb https://download.jitsi.org stable/' > /etc/apt/sources.list.d/jitsi-stable.list"

sudo apt update -y

sudo apt install -y jitsi-meet

Проверяем конфиг nginx (возможно задвоение server_names_hash_bucket_size 64)

nginx -t

Запускаем http-сервер

service nginx restart

Ставим сертификат

sudo /usr/share/jitsi-meet/scripts/install-letsencrypt-cert.sh



