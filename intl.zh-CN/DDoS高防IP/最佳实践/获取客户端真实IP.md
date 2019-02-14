# 获取客户端真实IP {#concept_40535_zh .concept}

为Web业务部署DDoS防护后，您可以参照本文介绍的方法，获取客户端真实IP。

## 四层接入（非网站防护） {#section_bz3_bsp_fgb .section}

按照以下不同的部署配置场景，选择适合您的源站获取客户端IP方式。

-   高防 \> 阿里云ECS

    通过TCP端口转发流量的情况，您无需做任何改动。源站服务器上看到的客户端IP就是真实的客户端IP。同时，ECS的安全组配置对象也可以针对真实的客户端IP进行设置。

    **说明：** 如使用UDP端口转发，源站ECS将无法获取真实客户端IP。

-   高防 \> SLB \> ECS

    默认支持获取客户端真实IP。

    通过TCP端口转发流量的情况，您无需做任何改动。源站服务器上看到的客户端IP就是真实的客户端IP。

    **说明：** 

    -   负载均衡SLB访问控制设置白名单中必须添加[高防回源IP段](intl.zh-CN/DDoS高防IP/快速入门/防护网站业务/步骤2：放行回源IP段.md#)。
    -   如使用UDP端口转发，源站ECS将无法获取真实客户端IP。
    **注意：** 

    -   2018年10月后创建的ECS实例，默认支持获取客户端真实IP，即在源站ECS服务器上看到的客户端IP就是真实访问源IP。
    -   2018年10月前创建的ECS实例，默认情况下无法获取客户端真实IP，您需提交工单申请开通相关配置。
-   高防 \> 阿里云外服务器

    部分情况下支持获取客户端真实IP，具体方法参考[高防如何支持云外主机获取客户端IP](intl.zh-CN/DDoS高防IP/最佳实践/云外主机获取真实客户端源IP.md#)。


## 七层接入（网站防护） { .section}

当一个七层代理服务器（如高防IP）把用户的访问请求转到后端服务器时，源站默认看到的是这个七层代理服务器（如高防IP）的回源IP。而真实的客户端IP会被七层代理服务器放在HTTP头部的X-Forwareded-For字段，格式如下：`X-Forwarded-For: 用户真实IP, 高防代理IP`。

如果中间经过不止一个代理服务器（如经过了WAF、CDN等等代理服务器），此时HTTP头部的X-Forwarded-For字段的格式如下：`X-Forwarded-For: 用户真实IP, 代理服务器1-IP, 代理服务器2-IP, 代理服务器3-IP, …`。

经过多层代理服务器，请求用户的真实IP处于第一个位置，而后面包含所有经过的中间代理服务器的IP。因此，只要获取HTTP头部的X-Forwarded-For字段的内容即可。

**常用的获取X-Forwarded-For字段内容方式**

-   ASP

    ```
    Request.ServerVariables(“HTTP_X_FORWARDED_FOR”)
    
    ```

-   ASP.NET\(C\#\)

    ```
    Request.ServerVariables[“HTTP_X_FORWARDED_FOR”]
    
    ```

-   PHP

    ```
    `$_SERVER[“HTTP_X_FORWARDED_FOR”]
    
    ```

-   JSP

    ```
    request.getHeader(“HTTP_X_FORWARDED_FOR”)
    
    ```


获取到HTTP头部的X-Forwarded-For字段的相关内容后，以“,”作为区分符，截取其中的第一个IP地址即可获取客户端真实IP。

## 附录：常见Web服务器获取真实IP的方法 {#section_vpb_kfd_ggb .section}

**Nginx配置方案**

1.  确认 http\_realip\_module 模块已安装。Nginx作为负载均衡获取真实IP是使用http\_realip\_module模块。

    **说明：** 通过一键安装包安装的Nginx默认不安装此模块，可以使用 `# nginx -V | grep http_realip_module` 查看此模块有无安装。

    如果 http\_realip\_module 模块未安装，需要重新编译Nginx并加装此模块。

    ```language-shell
    wget http://soft.phpwind.me/top/nginx-1.0.12.tar.gz
    tar zxvf nginx-1.0.12.tar.gz
    cd nginx-1.0.12
    ./configure --user=www --group=www --prefix=/alidata/server/nginx --with-http_stub_status_module --without-http-cache --with-http_ssl_module --with-http_realip_module
    make
    make install
    kill -USR2 `cat /alidata/server/nginx/logs/nginx.pid`
    kill -QUIT `cat /alidata/server/nginx/logs/ nginx.pid.oldbin`
    
    ```

2.  修改Nginx对应server的配置。 在`location / {}`中添加以下内容。

    ```language-shell
    set_real_ip_from ip_range1;
    set_real_ip_from ip_range2;
    ...
    set_real_ip_from ip_rangex;
    real_ip_header    X-Forwarded-For;
    
    ```

    **说明：** 这里的 `ip_range1,2,...` 指的是高防IP的回源IP地址，需要添加多条。如果高防IP后还有WAF、CDN，则需要写WAF、CDN的回源IP地址，即需要写离源站最近的一层七层代理的回源IP段。

3.  修改日志记录格式 log\_format。log\_format一般在nginx.conf中的HTTP配置中：

    ```
    log_format  main  '$http_x_forwarded_for - $remote_user [$time_local] "$request" ' '$status $body_bytes_sent "$http_referer" ' '"$http_user_agent" ';
    
    ```

    添加x-forwarded-for字段，替换原本的remote-address。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79579/154710607435035_zh-CN.png)

4.  重启Nginx使配置生效 `nginx -s reload`。

**IIS 6 配置方案**

IIS 6通过日志可获取来访者真实IP。

1.  安装[F5XForwardedFor.dll 插件](http:////docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/cn/slb/0.0.121/assets/F5XForwardedFor2008.zip)。
2.  根据您服务器的操作系统版本将x86\\Release或者x64\\Release目录下的F5XForwardedFor.dll拷贝到本地目录（例如C:\\ISAPIFilters）。同时，确保IIS进程对该目录有读取权限。
3.  打开IIS管理器，选择当前开启的网站右键，单击**属性**。
4.  在属性对话框，单击**ISAPI筛选器**，单击**添加**。
5.  在添加对话框中，在**筛选器名称**处填写“F5XForwardedFor”，在**可执行文件处**填写F5XForwardedFor.dll的完整路径，单击**确定**。
6.  重启IIS服务器，配置生效。

**IIS 7 配置方案**

IIS 7可通过F5XForwardedFor模块获取来访者真实IP。

1.  下载并安装 [F5XForwardedFor 插件模块](http:////docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/cn/slb/0.0.121/assets/x_forwarded_for.rar)。
2.  根据您服务器的操作系统版本将x86\\Release或者x64\\Release目录下的F5XFFHttpModule.dll和 F5XFFHttpModule.ini文件拷贝到本地目录（例如 C:\\F5XForwardedFor\\）。同时，确保对IIS进程对该目录有读取权限。
3.  打开IIS管理器，选择**IIS服务器**选项。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79579/154710607435036_zh-CN.png)

4.  双击打开**模块**功能，单击**配置本机模块**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79579/154710607435037_zh-CN.png)

5.  在配置本机模块对话框中，单击**注册**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79579/154710607435038_zh-CN.png)

6.  添加已下载的 F5XFFHttpModule.dll文件。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79579/154710607435039_zh-CN.png)

7.  添加完成后，选中刚才注册的模块，单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79579/154710607435040_zh-CN.png)

8.  在API 和CGI限制窗口添加 F5XFFHttpModule.dll文件，并设置为**允许**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79579/154710607435041_zh-CN.png)

9.  重启IIS服务器，配置生效。

**Apache配置方案**

**Windows操作系统**

在Apache 2.4及以上版本的安装包中已自带remoteip\_module模块文件（mod\_remoteip.so），您可以通过该模块获取访问者真实IP地址。

1.  在Apache的extra配置文件夹（conf/extra/）中，新建httpd-remoteip.conf配置文件。

    **说明：** 为减少直接修改httpd.conf配置文件的次数，避免因操作失误而导致的业务异常，通过引入remoteip.conf配置文件的方式加载相关配置。

2.  在httpd-remoteip.conf配置文件中，添加以下访问者真实IP的获取规则。

    ```
    ＃加载mod_remoteip.so模块
    LoadModule remoteip_module modules/mod_remoteip.so
    ＃设置RemoteIPHeader头部
    RemoteIPHeader X-Forwarded-For
    ＃设置回源IP段
    RemoteIPInternalProxy 112.124.159.0/24 118.178.15.0/24 120.27.173.0/24 203.107.20.0/24 203.107.21.0/24 203.107.22.0/24 203.107.23.0/24 47.97.128.0/24 47.97.129.0/24 47.97.130.0/24 47.97.131.0/24
    ```

3.  修改conf/httpd.conf配置文件，插入httpd-remoteip.conf配置文件。

    ```
    Include conf/extra/httpd-remoteip.conf
    ```

4.  在httpd.conf配置文件中，修改日志格式。

    ```
    LogFormat "%a %l %u %t \"%r\" %>s %b \"%{Referer}i\" \"%{User-Agent}i\"" combined
    LogFormat "%a %l %u %t \"%r\" %>s %b" common
    ```

5.  重启Apache服务，使配置生效。

**Linux操作系统**

您可以通过安装Apache的[mod\_rpaf](http://stderr.net/apache/rpaf/)第三方模块，获取访问者真实IP地址。

1.  执行以下命令，安装mod\_rpaf模块。

    ```
    wget http://stderr.net/apache/rpaf/download/mod_rpaf-0.6.tar.gz
    tar zxvf mod_rpaf-0.6.tar.gz
    cd mod_rpaf-0.6
    /alidata/server/httpd/bin/apxs -i -c -n mod_rpaf-2.0.so mod_rpaf-2.0.c
    ```

2.  修改Apache配置文件/alidata/server/httpd/conf/httpd.conf，在文件最后添加以下内容：

    **说明：** 其中，`RPAFproxy_ips ip地址`不是负载均衡提供的公网IP。具体IP可参考Apache的日志，通常会有两个IP地址。

    ```
    LoadModule rpaf_module modules/mod_rpaf-2.0.so
    RPAFenable On
    RPAFsethostname On
    RPAFproxy_ips ip地址
    RPAFheader X-Forwarded-For
    ```

3.  添加完成后，执行以下命令重启Apache服务，使配置生效。

    ```
    /alidata/server/httpd/bin/apachectl restart
    ```


**mod\_rpaf模块配置示例**

```

LoadModule rpaf_module modules/mod_rpaf-2.0.so
RPAFenable On
RPAFsethostname On
RPAFproxy_ips 10.242.230.65 10.242.230.131
RPAFheader X-Forwarded-For
```

**Tomcat配置方案**

开启 Tomcat 的 X-Forwarded-For 功能可获取客户端真实IP。

在 tomcat/conf/server.xml 文件中，修改 AccessLogValve 日志记录功能：

```language-xml
<Valve className="org.apache.catalina.valves.AccessLogValve" directory="logs"
prefix="localhost_access_log." suffix=".txt"
pattern="%{X-FORWARDED-FOR}i %l %u %t %r %s %b %D %q %{User-Agent}i %T" resolveHosts="false"/>

```

