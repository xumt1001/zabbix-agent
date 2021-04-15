# 搭建zabbix-agent3.4
克隆
cd /usr/local

https://github.com/xumt1001/zabbix-agent.git

mv zabbix-agent zabbix

cd /usr/local/zabbix/sbin

./zabbix_agent 会报错没有文件夹  
mkdir -p  /usr/local/zabbix/etc/zabbix_agentd.conf.d/

./zabbix_agent 会报错没有zabbix用户
useradd zabbix

./zabbix_agentd


编辑
 /usr/local/zabbix/etc/zabbix_agentd.conf  
修改
server=
serverActive=zabbixserver的公网IP
修改Hostname=xxxxxx


报错：
./zabbix_agentd: error while loading shared libraries: libpcreposix.so.3: cannot open shared object file: No such file or directory
find / -name libpcreposix.so*
ln -s /usr/lib64/libpcreposix.so.0 /usr/lib64/libpcreposix.so.3
