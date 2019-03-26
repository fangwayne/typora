# 操作步骤

1. 安装 HomeAssistant 

   安装:

   ```bash
   sudo pip3 install homeassistant
   ```

    

   升级:

   ```bash
   sudo pip3 install homeassistant --upgrade
   ```

   

2. 启动 HomeAssistant 

   启动homeAssistant的命令为hass:

   ```bash
   hass
   ```

   hass启动后会自行安装升级相应的文件，当系统出现Timer：starting 时，表示已经启动完成。启动完成后，会作为服务一直运行。

   我们可以用bash 命令

   ```bash
   netstat  -an||grep 8123
   ```

   来查看端口情况。

   我们通过bash命令

   ```bash
   cat home-assistant.log
   ```

   来查看日志文件。

3. 第一次启动，创建用户，登录 

   在浏览器访问树莓派端口  192.168.21.124:8123 

   创建homeAssistant用户和密码

4. 创建隐藏文件 .homeassistant 的镜像链接文件为可见文件夹 homeassistant

   ```bash
   ln -s .homeassistant/ homeassistant
   ```

   ```bash
   ls -a      #显示当前目录下的全部文件包括隐藏文件
   
   ls -d .*   #仅显示当前目录下的所有隐藏文件
   ```

   

5. 查看 HomeAssistant 的错误日志 

6. 查看并修改 HomeAssistant 的配置文件 





# 参考

- ⚫  HomeAssistant命令 

- ⚫  yaml格式 https://www.hachina.io/docs/335.html 

- ⚫ 比特币配置 sensor: 

  ......
   \- platform: bitcoin 

  display_options:
   \- exchangerate
   \- trade_volume_btc 