一、 获取本机的IP号centos7

###### ifconfig ens33|awk 'NR==2'|awk -F'[ ]+' 'BEGIN{OFS="\n"}{print $3,$5,$7}'    

二、centos6 获取本机IP

ifconfig eth0|awk 'NR>1 {print $2}'|awk -F':' 'NR<2 {print $2}'    

###### ifconfig eth0|grep Bcast|awk -F':' '{print $2}'|awk '{print $1}'

###### ifconfig eth0|grep Bcast|awk '{print $2}'|awk -F: '{print $2}'

ifconfig eth0|awk NR==2|awk -F '[ :]+' '{print $4RS$6RS$8}'

三、启动nginx
sbin/nginx -c /usr/local/nginx/conf/nginx.conf
sbin/nginx -s reload
四、追加环境变量启动PHP
echo 'export PATH=PATH:/usr/local/php/bin' >> /etc/profile
service php-fpm start /systemctl start hph-fpm

五、mysql 密码的设置
mysql_seurce_installation
第二个为no 其他都为yes

六、==统计网站访问量==
ss -antp|grep 80|awk '{states[$1]++};END{for(i in states){print i,states[i]}}'
