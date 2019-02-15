# frp2ram 在路由器内存中运行frpc
  适用flash小且无sd、usb扩展，ram足够大情况下（至少有10M空闲内存）
  mt7620 LEDE17.09 8M flash / 128M ram 测试通过
  
# 用法：
  将此脚本放到/etc/init.d/目录 并执行chmod +x /etc/init.d/frpc2ram
  启动 /etc/init.d/frpc2ram start
  停止 /etc/init.d/frpc2ram stop
  开机自启动 ln -s /etc/init.d/frpc2ram /etc/rc.d/S99frpc2ram

  在gui中系统--启动项中找到frpc2ram 对应操作也可以

  也可以将脚本所有内容贴到本地启动脚本中（在ext 0直接）实现开机启动
 
# 必要修改的参数：
  server 要连接的服务器域名或ip
  port 要连接的服务器端口
  token 

# 配置文件：
  不存在$exec_conf配置文件的时候set_frpc_default_conf会自己产生
  需要修改自动产生配置文件内容的可改此函数EOF ....EOF之间的内容 
	`set_frpc_default_conf(){`
`cat > $exec_conf<<-EOF`
  `....`
  `EOF`

 winffy2009
2019.02.15
