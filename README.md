Camoflix


Camoflix using ultraviolet and nginx for hosting.

Set up: {
#USING: Ubuntu 24.x
ADD VPS to A record.
A  IP:IP:IP:IP path.example.com
A  IP:IP:IP:IP *.path.example.com

INSTALL: 
$ sudo apt install nginx || sudo apt install git || sudo apt install certbot python3-certbot-dns-cloudflare
$ curl -fsSL https://deb.nodesource.com/setup_23.x | sudo bash - 
$ sudo apt install nodejs
$ sudo npm install pm2 -g

Clone:
$git clone https://github.com/idk/idk.git

Commands:
$cd camoflix-nginx

#Nginx Conf edit domain host to ur domain paths
sudo nano nginx

#Nginx Move
$ mv nginx /etc/nginx/sites-available/camoflix
$ sudo ln -s /etc/nginx/sites-available/camoflix /etc/nginx/sites-enabled/

#Certbot:
$ sudo certbot certonly --manual || --preferred-challenges dns || -d "*.path.example.com" -d path.example.com

#Starting using pm2
$ pm2 start src/index.js --name camobrowser
$ sudo systemctl reload nginx

#Visit Domain
path.example.com
and wildcard *.path.example.com

}


