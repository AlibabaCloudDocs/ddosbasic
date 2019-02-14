# 云外主机获取真实客户端源IP {#concept_52477_zh .concept}

如果您为阿里云外主机配置了 DDoS 高防 IP 服务，您可以使用本文介绍的方法来获取真实客户端源 IP。

本文介绍的方法支持以下操作系统：

-   Redhat Linux
-   Centos 6.x

在按照步骤进行操作前，请注意以下事项：

-   建议先在测试环境中进行测试，观察环境稳定后再部署正式上线。
-   建议保留原有的内核，如果出现重启失败，可以切换到原有内核进行恢复。

## 操作步骤 { .section}

参照以下步骤，来获取真实客户端源IP。

1.  下载内核安装文件。
    -   [kernel-2.6.32-220.23.2.ali\_github.el6.x86\_64.rpm](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/52477/cn_zh/1491917761209/kernel-2.6.32-220.23.2.ali_github.el6.x86_64.rpm) 
    -   [kernel-firmware-2.6.32-220.23.2.ali\_github.el6.x86\_64.rpm](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/52477/cn_zh/1491917803344/kernel-firmware-2.6.32-220.23.2.ali_github.el6.x86_64.rpm) 
2.  安装内核。定位到安装文件目录，执行以下命令：

    ```
    rpm -ivh kernel-2.6.32-220.23.2.ali_github.el6.x86_64.rpm
    
    ```

    **说明：** CentOS 6.2 以上版本不需要安装 kernel-firmware。

3.  设置 toa 模块启动自动加载。
    1.  创建文件/etc/sysconfig/modules/toa.modules，文件内容如下：

        ```
        !/bin/bash
        if [ -e /lib/modules/uname -r/kernel/net/toa/toa.ko ] ;
        then 
        modprobe toa > /dev/null 2>&1
        fi
        
        ```

    2.  执行以下命令，授予创建 toa 模块可执行权限：

        ```
        sudo chmod +x /etc/sysconfig/modules/toa.modules
        ```

4.  执行`reboot`命令，重启系统。

## 功能测试 {#section_b3q_3lp_fgb .section}

安装完成后，主机应能正常获取真实客户端源 IP。如果仍无法获取客户端源 IP，可执行`lsmod|grep toa`命令检测 toa 模块加载情况。

如果 toa 模块未加载，通过执行`modprobe toa`命令手动加载。加载成功后，重新测试主机能否获取真实客户端源 IP。

## 相关问题 {#section_vh5_jlp_fgb .section}

-   网络连接通过 toa 模块转换，对性能有多大影响？

    toa 模块是部署在旁路的，因此对网络性能几乎没有影响。

-   如果担心加载新的内核模块可能出现稳定性问题怎么办？

    建议保留原有的内核，如果出现重启失败，可以切换到原有内核恢复。另外，当前版本是在Github上开源的。


