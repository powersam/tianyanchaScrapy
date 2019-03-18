# tianyanchaScrapy

#### 项目介绍
天眼查( https://www.tianyancha.com/ ) 公司信息采集

#### 界面预览  
![tyc_list](https://github.com/TonyK-T/github_images/blob/master/tycAndQcc/tyc_list.png)
![tyc_info_title](https://github.com/TonyK-T/github_images/blob/master/tycAndQcc/tyc_info_title.png)
![tyc_info_detail](https://github.com/TonyK-T/github_images/blob/master/tycAndQcc/tyc_info_detail.png)

#### 执行过程
![tyc_run](https://github.com/TonyK-T/github_images/blob/master/tycAndQcc/tyc_run.png)

#### 执行结果
![tyc_data](https://github.com/TonyK-T/github_images/blob/master/tycAndQcc/tyc_data.png)

#### 软件架构
软件架构说明  
1、Scrapy + Scrapy-redis 分布式爬取  
2、bloomfilter 过滤、redis sadd去重  
3、数据入mysql(sqlalchemy) ，数据入mongodb(motor异步)  
4、User-Agent代理，IP代理，cookies登录态  
5、scrapyd-client打包  
6、gerapy 爬虫管理平台   

#### 安装教程
安装Python库    
安装redis    
安装mysql，mongodb    
搭建gerapy环境 - 略    

#### 懒人专享 一键docker
1、安装docker-略  
2、下载docker镜像：https://pan.baidu.com/s/1JU9xqbsDkYh-3ehhiuK1Jg  (需要安装Mysql,redis,mongo 并zai mode.py 中修改成 mysql+pymysql://root:root_password)

3、加载镜像(耗时)：docker load -i  centos7:python3.tar    
4、创建并运行容器：docker  run -itd -p 8002:8001 -p 6802:6800  --privileged=true  centos7:python3  /usr/sbin/init  
5、访问gerapy管理部署爬虫： http://IP:8002/    

如果访问 http://IP:8002/ 报500，解决方式如下：  
  1.查看容器的CID：docker ps -a  
  2.进入容器命令行： docker exec -it  容器CID /bin/bash  
  3.容器命令行里重启gerapy服务：  
      ps -ef|grep gerapy   
      kill -9 gerapy进程ID  
      /gerapy/gerapy_start.sh    # 重启gerapy脚本    
 ![docker_python3](https://github.com/TonyK-T/github_images/blob/master/docker/docker_Python3.png) 

#### 使用说明
1、纯脚本运行：Python run.py    (centos7 docker 运行Unhandled error in Deferred: 未解决,待解决中)

2、gerapy 爬虫管理平台： 部署、启动停止删除爬虫 -略    

#### gerapy管理平台
![tyc_gerapy_1](https://github.com/TonyK-T/github_images/blob/master/tycAndQcc/tyc_gerapy_1.png)
![tyc_gerapy_2](https://github.com/TonyK-T/github_images/blob/master/tycAndQcc/tyc_gerapy_2.png)
