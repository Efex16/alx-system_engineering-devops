Installing HAProxy and configuring HAProxy
$ sudo apt-get install -y haproxy=1.6.\*


echo '
frontend efex16.tech
        bind 0:80
        default_backend web_servers
backend web_servers
        balance roundrobin
        server 154503-web-01 54.159.24.194:80
        server 154503-web-02 54.208.205.82:80
' >> /etc/haproxy/haproxy.cfg

$ service haproxy restart
