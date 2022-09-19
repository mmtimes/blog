1. 安装LAMP环境
```bash
apt-get install apache2 -y
systemctl enable --now apache2
```
2. 安装dokuwiki
```bash
wget https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz
tar -zxvf dokuwiki*.tgz
mv dokuwiki* /var/www/html/dokuwiki
cp /var/www/html/dokuwiki/.htaccess{.dist,}
```
3. 配置apache
```bash
cd /etc/apache2/sites-available
vim /etc/apache2/sites-available/dokuwiki.conf
a2ensite dokuwiki
systemctl reload apache2
```
