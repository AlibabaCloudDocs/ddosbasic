# 上传HTTPS证书 {#task_221116 .task}

要使新BGP高防IP帮助您清洗HTTPS业务流量，您必须在网站配置中勾选HTTPS协议，并上传HTTPS证书。已上传证书发生变化时，您也要在新BGP高防IP控制台及时更新证书。

-   已添加网站配置（具体操作请参考[步骤1：添加网站配置](cn.zh-CN/新BGP高防IP/快速入门/防护网站业务/步骤1：添加网站配置.md#)）且网站支持HTTPS协议。
-   准备证书文件内容。

    如果您已将证书文件上传到[云盾SSL证书服务](https://yundunnext.console.aliyun.com/?p=casnext)进行统一管理，那么在上传证书时您可以直接选择已有证书；否则您需要准备好网站的证书和私钥文件，以完成上传操作。一般情况下，您需要准备的证书相关内容包括：

    -   \*.crt（公钥文件）或者\*.pem（证书文件）
    -   \*.key（私钥文件）

1.  登录[云盾新BGP高防IP控制台](https://yundunnext.console.aliyun.com/?p=ddoscoo)。
2.  在左侧导航栏，单击**管理** \> **网站配置**。
3.  在网站配置列表中，定位到要操作的域名，单击其**证书状态**列下的上传图标。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/155771870345762_zh-CN.png)


4.  在上传证书和私钥对话框中，选择一种**上传方式**，并完成上传配置。可选择的上传方式包括以下两种： 
    -   （推荐）**选择已有证书** 

        如果您的网站证书已经上传并托管在云盾SSL证书服务中，您可以直接从已有证书中选择并上传。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/155771870345763_zh-CN.png)

        即使您的证书未托管在SSL证书中，您也可以单击**前往SSL证书控制台管理**，上传并管理您的证书；然后再选择已有证书。关于如何在SSL证书服务控制台上传证书，请参考[上传已有证书](../../../../cn.zh-CN/用户指南/上传已有证书.md#)。

    -   **手动上传** 

        填写**证书名称**，并将证书文件和私钥文件中的文本内容分别复制粘贴到**证书文件**和**私钥文件**文本框中。

        **说明：** 

        -   对于.pem、.cer、.crt格式的证书，您可以使用文本编辑器直接打开证书文件，并复制其中的文本内容；对于其他格式（如.pfx、.p7b等）的证书，您需要将证书文件转换成.pem格式后，才能用文本编辑器打开并复制其中的文本内容。

            关于证书格式的转换方式，请参考[HTTPS证书转换成PEM格式](https://help.aliyun.com/document_detail/40526.html)。

        -   如果该HTTPS证书有多个证书文件（如证书链），您需要将证书文件中的文本内容拼接合并后粘贴至**证书文件**文本框中。
        证书文件文本内容样例

        ``` {#codeblock_7kx_qhu_25z}
        -----BEGIN CERTIFICATE----- 
        xxxxxxxxxxxxvs6MTXcJSfN9Z7rZ9fmxWr2BFN2XbahgnsSXM48ixZJ4krc+1M+j2kcubVpsE2cgHdj4v8H6jUz9Ji4mr7vMNS6dXv8PUkl/qoDeNGCNdyTS5NIL5ir+g92cL8IGOkjgvhlqt9vc65Cgb4mL+n5+DV9uOyTZTW/MojmlgfUekC2xiXa54nxJf17Y1TADGSbyJbsC0Q9nIrHsPl8YKkvRWvIAqYxXZ7wRwWWmv4TMxFhWRiNY7yZIo2ZUhl02SIDNggIEeg==
        -----END CERTIFICATE-----
        ```

        私钥文件文本内容样例

        ``` {#codeblock_5qj_l6u_jhb}
        -----BEGIN RSA PRIVATE KEY-----
        xxxxxxxxxxxxtZ3UKHJTRgNQmioPQn2bqdKHop+B/dn/4VZL7Jt8zSDGM9sTMThLyvsmLQKBgQCr+ujntC1kN6pGBj2Fw2l/EA/W3rYEce2tyhjgmG7rZ+A/jVE9fld5sQra6ZdwBcQJaiygoIYoaMF2EjRwc0qwHaluq0C15f6ujSoHh2e+D5zdmkTg/3NKNjqNv6xA2gYpinVDzFdZ9Zujxvuh9o4Vqf0YF8bv5UK5G04RtKadOw==
        -----END RSA PRIVATE KEY-----
        ```

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/188520/155771870345764_zh-CN.png)

5.  单击**确定**。

成功上传证书后，证书状态会更新为有证书。

