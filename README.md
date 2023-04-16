# MetaUni-MiddleWare
Contains docker-compose.yml to build middleware for MetaUni  
此文档帮助您使用Docker构建MetaUni项目中使用到的Middleware（目前包括Consul、MinIO、RabbitMQ和Redis）  
阅读文档前请先确保：  
+ 您使用的操作系统为Windows
+ 您已顺利安装Docker Desktop  

以下条件不是必要，但可以显著增加您的体验：  
+ 您可以流畅访问外网 或 您已为Docker Desktop配置镜像源  

下面进入正题：  
1. 找一个合适的文件夹，将仓库内容拉取下来  
2. 打开CMD，`cd /d yourDir`，跳转至您存取仓库内容的文件夹  
3. 打开Docker Compose.txt文件，在CMD中依次输入文件内记录的命令（`docker compose up -d`）
4. 检查Docker是否正确运行容器  

附：  
1.  MinIO、RabbitMQ等文件夹下的txt文件为单独启动对应Middleware时所运行的命令，您可以选择遵照上文步骤使用`docker compose up -d`命令一次性启动所有容器，也可以选择依次运行单独启动容器的命令。    
2. 执行完启动容器的命令后，MinIO、RabbitMQ等文件夹下会出现名字为“data”（或其它）的文件夹，这些文件夹用于与容器内部的文件进行关联（即Docker中的数据卷挂载，用于将部分重要数据持久化到宿主机中）。  
3. Redis文件夹下有用于对Redis进行配置的redis.conf配置文件，该文件通过数据卷挂载与容器内部的配置文件进行关联。  
4. Consul文件夹下的docker-compose.yml文件用于一次性启动多个consul容器，您可以选择遵照上文步骤在最外层目录使用`docker compose up -d`命令一次性启动所有容器，也可以选择在Consul文件夹下单独运行`docker compose up -d`命令后再依次前往其它文件夹下运行单独启动其它容器的命令（顺序也可以反过来）。   
