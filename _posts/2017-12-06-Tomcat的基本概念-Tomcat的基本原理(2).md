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
#### Key point<br>
1. Tomcat启动的核心，就是启动Catalina容器
2. <CATALINA_HOME>/conf/目录下的context.xml和web.xml在部署任何webapp时都会启动，他们定义一些默认行为，而具体每个webapp的  META-INF/context.xml  和  WEB-INF/web.xml  则定义了每个webapp特定的行为
3. tomcat根目录在tomcat中叫<CATALINA_HOME>
4. 管理Tomcat的地址: http://localhost:8080/manager/html
5. Tomcat的基本组成分为：Server, Service, Connector, Engine, Host, Context
