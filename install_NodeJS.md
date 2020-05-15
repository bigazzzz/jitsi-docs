### Инсталяция c помощью NodeJS
(c) https://community.jitsi.org/t/changing-the-default-language/15978

Installation and basic configuration of Jitsi-Meet:

wget -qO - https://download.jitsi.org/jitsi-key.gpg.key 2 | apt-key add -

sh -c “echo ‘deb https://download.jitsi.org 4 stable/’ > /etc/apt/sources.list.d/jitsi-stable.list”

apt-get -y update

apt-get -y install jitsi-meet

cd /usr/share/jitsi-meet/scripts

./install-letsencrypt-cert.sh

nano -c /etc/jitsi/videobridge/sip-communicator.properties

org.ice4j.ice.harvest.NAT_HARVESTER_LOCAL_ADDRESS=<Local.IP.Address>
org.ice4j.ice.harvest.NAT_HARVESTER_PUBLIC_ADDRESS=<Public.IP.Address>

/etc/init.d/jitsi-videobridge restart

Installation of NodeJs

curl -sL https://deb.nodesource.com/setup_10.x 9 | sudo -E bash -

sudo apt-get install -y nodejs

sudo apt-get install -y gcc g++ make

Default language change:

git clone https://github.com/jitsi/jitsi-meet.git 42

cd jitsi-meet/

nano -c config.js

uncomment the line:

// defaultLanguage: ‘en’,

and change "en" to "ru".

npm install

make

rm -r /usr/share/jitsi-meet/

cp -r /home/xxx/jitsi-meet /usr/share
