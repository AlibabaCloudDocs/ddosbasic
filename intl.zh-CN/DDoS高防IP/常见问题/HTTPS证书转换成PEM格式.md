# HTTPS证书转换成PEM格式 {#concept_40526_zh .concept}

PEM 格式的证书文件（\*.pem）一般为以下格式：

**说明：** PEM 格式证书文件可用 notepad++ 等文本编辑器打开。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79639/154693059935286_zh-CN.png)

对于 CER / CRT 格式的证书，您可通过直接修改证书文件扩展名的方式进行转换。例如，将“server.crt”证书文件直接重命名为“server.pem”即可。

## PFX 格式证书转换为 PEM 格式 { .section}

PFX 格式的证书一般出现在 Windows Server 服务器中，您可通过 openssl 工具进行转换。

例如，通过执行以下两条 openssl 命令即可把 certname.pfx 证书转换成 PEM 格式。

-   提取私钥命令：`openssl pkcs12 -in certname.pfx -nocerts -out key.pem -nodes` 
-   提取证书命令：`openssl pkcs12 -in certname.pfx -nokeys -out cert.pem` 

## P7B 格式证书转换为 PEM 格式 { .section}

P7B 格式证书一般出现在 Windows Server 和 Tomcat 服务器中，您可通过 openssl 工具进行转换。

## 转换步骤 { .section}

参照以下步骤，将 P7B 格式证书转化为 PEM 格式。

1.  证书转换。例如，执行 `openssl pkcs7 -print_certs -in incertificat.p7b -out outcertificate.cer` 命令将 incertificat.p7b 证书文件转换成 outcertificate.cer 格式。
2.  获取outcertificat.cer 文件中`[-----BEGIN CERTIFICATE-----`与`-----END CERTIFICATE-----]`中的证书内容。
3.  将证书内容保存为 PEM 格式即可。

## DER 格式证书转换为 PEM 格式 { .section}

DER 格式的证书一般出现在 Java 平台中，您可使用 openssl 工具将其转化为 PEM 格式。

例如，通过执行以下两条 openssl 命令可以把 certificate.cer 证书转换成 PEM 格式。

-   提取证书：`openssl x509 -inform der -in certificate.cer -out certificate.pem` 
-   提取私钥：`openssl rsa -inform DER -outform PEM -in privatekey.der -out privatekey.pem` 

