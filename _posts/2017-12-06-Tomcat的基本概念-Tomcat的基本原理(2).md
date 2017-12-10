---
layout: post
title: Tomcat的基本概念-Tomcat的基本原理(2)
comments: true
author: "Yin Haomin"
tags:
    - 基本概念
    - Tomcat
    - 原理
---

研究Tomcat的基本原理，需要研究清楚Tomcat的基本组成.<br>
#### 1. Key point<br>
Tomcat是一个Web应用服务器，它可以运行JSP和Servlet. <br>
1. Tomcat启动的核心，就是启动Catalina容器<br>
2. <CATALINA_HOME>/conf/目录下的context.xml和web.xml在部署任何webapp时都会启动，他们定义一些默认行为，而具体每个webapp的  META-INF/context.xml  和  WEB-INF/web.xml  则定义了每个webapp特定的行为。<br>
3. tomcat根目录在tomcat中叫<CATALINA_HOME> <br>
4. 管理Tomcat的地址: http://localhost:8080/manager/html<br>
5. Tomcat的基本组成分为：Server, Service, Connector, Engine, Host, Context等模块。<br>

#### 2. 从表面看Tomcat<br>
(1). Tomcat的各个路径的含义<br>
<CATALINA_HOME>/lib：存放Tomcat运行需要的库文件(JARS)<br>
<CATALINA_HOME>/logs：存放Tomcat执行时的LOG文件; <br>
<CATALINA_HOME>/temp：<br>
<CATALINA_HOME>/webapps：Tomcat的主要Web发布目录(包括应用程序示例); <br>
<CATALINA_HOME>/work：存放JSP编译后产生的class文件; <br>

(2). Tomcat的各个配置的含义<br>
Server.xml，主要是这个Server的相关描述。<br>
![gras](/images/Tomcat/Tomcat-server.xml-info.tiff)<br>










