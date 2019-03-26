# 操作步骤

1. 自启动配置文件 
2. 设置自启动 
3. 查看日志输出 
4. 手动控制服务 
5. 同样操作，设置 Jupyter-notebook 的自启动 





# 参考
 ⚫ /etc/systemd/system/home-assistant@pi.service 文件 

[Unit]
Description=Home Assistant 
After=network.target
[Service]
Type=simple
ExecStart=/usr/local/bin/hass
User=%i 
[Install] 
WantedBy=multi-user.target 



⚫ /etc/systemd/system/jupyter-notebook@pi.service 文件 

[Unit]
Description=Jupyter Notebook
[Service]
Type=simple 
ExecStart=/usr/local/bin/jupyter-notebook 
User=%i
[Install]
WantedBy=multi-user.target 



⚫ 自启动服务相关命令(以 home-assistant@pi 服务为例) 

```
重载服务配置      :sudo systemctl --system daemon-reload

*将服务加入自启动*:sudo systemctl enable home-assistant@pi

将服务移除自启动  :sudo systemctl disable home-assistant@pi
手工启动服务     :sudo systemctl start home-assistant@pi
手工停止服务     :sudo systemctl stop home-assistant@pi
手工重启服务     :sudo systemctl restart home-assistant@pi

**查看服务输出** :sudo journalctl -f -u home-assistant@pi
```

​      