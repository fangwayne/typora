# Jupter连接RaspBerryPi



1. 安装、配置、使用 Samba ：

   先用apt安装samba协议

   ```bash
   sudo apt-get install samba samba-common
   
   ```

   用vi 进入samba配置文件smb.conf

   ```bash 
   sudo vi /etc/samba/smb.conf
   
   ```

   在==========Share Definitions==========的 [homes] 区间中把

   ```bash
   read only = yes
   ```

   改为

   ```bash
   read only = no
   ```

2. 新增samba的用户并设置密码：

   ```bash
   sudo smbpasswd -a pi
   
   ```

   重启smbd服务

   ```bash
   sudo systemctl restart smbd
   ```

   

3. 用MAC中的```command+k```键 唤出链接窗口，输入刚刚建立的samba账户pi和对应密码，连接树莓派。

    

    

    

4. 安装、配置、使用 Jupyter Notebook：

   ```bash
   sudo pip3 install jupyter
   
   ```

   生成jupyter notebook 的配置文件,用vi修改文件

   ``` bash
   jupyter notebook --generate-config
   
   vi ~/.jupyter/jupyter_notebook_config.py
   ```

   查找 /c.NotebookApp.ip

   去掉前面的注释#，并修改为

   ```bash 
   c.NotebookApp.ip = '0.0.0.0'
   ```

   查找 /c.NotebookApp.open_browser 

   去掉前面注释#，并修改为

   ```bash
   c.NotebookApp.open_browser = False
   ```

   查找/c.NotebookApp.port

   去掉前面注释#，并修改为

   ```bash
   c.NotebookApp.port = 8888
   ```

   查找/c.NotebookApp.notebook_dir

   去掉前面注释#，并修改为

   ```bash
   c.NotebookApp.notebook_dir = '/home/pi'
   ```

5. 设置 Jupyter Notebook 的访问密码

   ```bash
   jupyter notebook password
   ```

   启动 jupyter notebook

   ```bash
   jupyter notebook
   ```

   

6. 在浏览器中输入RaspberryPi的IP地址(8888端口)，输入密码即可进入jupyter notebook！





# 参考

- ⚫  Samba 命令 

  安装:sudo apt-get install samba samba-common 

  增加用户 pi 并设置密码:sudo smbpasswd -a pi 

  重启 samba 服务:sudo systemctl restart smbd 

- ⚫  Samba 配置文件位置 /etc/samba/smb.conf 

  - 用```ls```和```cat```命令可以查看文件的变化

- ⚫  如果共享目录不能显示
   在 Windows 的 DOS 窗口中，运行命令:
   net use z: \\raspiberry_ip\pi password /USER:pi
   修改其中 password 为你的 password，如果要保持 z 盘长久映射，在命令中增加: /PERSISTENT:YES 

- ⚫  Jupyter Notebook 命令

  - 安装:sudo pip3 install jupyter 

  - 生成配置文件:jupyter notebook --generate-config 
  - 设置访问密码:jupyter notebook password 

- ⚫  修改 Jupyter Notebook 的配置(文件位置~/.jupyter/jupyter_notebook_config.py) 在文件中找到下面的 4 个配置项，去除前面的注释符号(#)，并修改等号后的值为下面的值。 

  - c.NotebookApp.ip = '0.0.0.0' 

  - c.NotebookApp.open_browser = False 

  - c.NotebookApp.port = 8888 

  - c.NotebookApp.notebook_dir = '/home/pi/' 