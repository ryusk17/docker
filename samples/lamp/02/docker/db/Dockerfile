# RockyLinux8系のOSを使用
FROM dokken/rockylinux-8

# MySQL8.0のインストール
RUN dnf -y install @mysql:8.0

# 設定ファイル読み込み
COPY ./conf/my.conf /etc

# mysqlの自動起動を設定
RUN systemctl enable mysqld
