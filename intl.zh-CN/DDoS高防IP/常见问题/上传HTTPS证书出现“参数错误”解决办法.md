# 上传HTTPS证书出现“参数错误”解决办法 {#concept_40527_zh .concept}

在配置高防 IP 服务过程中，上传 HTTPS 证书时，提示“参数格式错误”。

在上传证书时出现“参数错误”的常见原因和解决方法如下：

-   证书名字过长。

    解决方法：修改证书文件名为 10 个字符以内。

-   证书文件名中包含特殊字符。

    解决方法：仅以英文字符或数字命名证书，不要包含空格、下划线、分隔符等特殊字符。

-   证书内容中存在不规范的内容。

    示例

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79642/154693073235289_zh-CN.png)

    解决方法

    删除证书文件中`---BEGIN CERTIFICATE---`之前的内容。

    -   规范的证书（.pem 文件）内容示例：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79642/154693073235290_zh-CN.png)

    -   规范的私钥（.key 文件）内容示例：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79642/154693073235291_zh-CN.png)


关于 HTTPS 证书的格式转换的信息，请参考[HTTPS证书转换成pem格式](intl.zh-CN/DDoS高防IP/常见问题/HTTPS证书转换成PEM格式.md#)。

