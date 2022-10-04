# RockyLinux8系のOSを使用
FROM dokken/rockylinux-8

# Apache2.4のインストール
RUN dnf -y install httpd httpd-tools httpd-devel && \
# PHP7.4のインストール
    dnf -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm && \
    dnf -y install https://rpms.remirepo.net/enterprise/remi-release-8.rpm && \
    dnf -y module reset php && dnf -y module install php:remi-7.4 && \
    dnf -y install php74 php-mysqlnd php-cli php-json php-devel php-common php-mbstring php-fpm php-gd php-opcache php-pdo php-xml php-intl php-zip php-pear php-bcmath && \
# Composerのインストール
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    sudo mv composer.phar /usr/local/bin/composer && \
# Node.jsとnpmのインストール
    dnf -y install nodejs npm && \
    npm install -g n && n stable && \
    dnf -y remove nodejs npm && exec $SHELL -l && \
# その他ツールのインストール
    dnf -y install wget git unzip mod_ssl openssl

# 設定ファイル読み込み
COPY ./conf/httpd.conf /etc/httpd/conf
COPY ./conf/php.ini /etc

# ソースコードディレクトリパス(laravel)
WORKDIR /var/www/html/

# apacheの自動起動を設定
RUN systemctl enable httpd
