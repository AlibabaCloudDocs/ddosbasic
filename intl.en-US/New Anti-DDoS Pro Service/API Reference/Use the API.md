# Use the API {#reference2570 .reference}

When an API call is made, an HTTP GET request is sent to the endpoint of the API. You need to specify request parameters in the request. A response is then returned in reply to the request. The request and response are encoded using the UTF-8 character set.

## Request structure { .section}

Anti-DDoS Pro APIs support RPC-type Web services. You can send HTTP GET requests to make API calls.

The request structure is as follows:

```language-shell
https://Endpoint/?Action=xx&Parameters

```

In the example:

-    `Endpoint` indicates the endpoint of Anti-DDoS Pro APIs. The current endpoint is `ddoscoo.cn-hangzhou.aliyuncs.com`.
-    `Action` indicates the action that you want to perform. For example, you can call `DescribeInstances` to perform queries on all Anti-DDoS Pro instances.
-    `Version` indicates the version of the API. The current version of Anti-DDoS Pro APIs is `2017-12-28`.
-    `Parameters` indicates the request parameters. Separate multiple parameters with ampersands \(&\).
-   Request parameters consist of common parameters and API specific parameters. Common parameters include variables such as the API version and credentials. For more information, see [Common parameters](intl.en-US/New Anti-DDoS Pro Service/API Reference/Common parameters.md#).

The following example calls the DescribeInstances operation to perform queries on Anti-DDoS Pro instances:

**Note:** The sample code has been formatted to make it more readable.

```
https://ddoscoo.cn-hangzhou.aliyuncs.com/?Action=DescribeInstances
&Region=cn 
&InstanceId=ddoscoo-cn-XXXX1
&Format=xml 
&Version=2017-12-28
&Signature=xxxx%xxxx%3D 
&SignatureMethod=HMAC-SHA1 
&SignatureNonce=15215528852396 
&SignatureVersion=1.0 
&AccessKeyId=key-test 
&TimeStamp=2012-06-01T12:00:00Z 
…

```

## Authorization { .section}

To ensure the security of your Alibaba Cloud account, we recommend that you call the APIs as a RAM user. Before you can use a RAM user to call the APIs, you must create a RAM user account and grant corresponding permissions to this account.

## Signature { .section}

Anti-DDoS Pro requires identity authentication for each API request. You must include signature information in either HTTP or HTTPS requests. For more information about the signature calculation process, see [RPC API signatures](../../../../intl.en-US/Alibaba Cloud API/Signature/Sign RPC APIs.md#).

Anti-DDoS Pro implements symmetric encryption through AccessKey ID and AccessKey Secret to authenticate the requester. AccessKey is an identity credential issued to Alibaba Cloud accounts and RAM users \(similar to the login password\). The AccessKey ID is used to identify the user. The AccessKey Secret is used to encrypt the signature string on the client side and to verify the signature string on the server side. The AccessKey Secret must be kept strictly confidential.

When you call an RPC API, you need to add the signature to your request using the following format:

```
https://endpoint/?SignatureVersion=1.0&SignatureMethod=HMAC-SHA1&Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf

```

Take DescribeInstances as an example. Assume that the AccessKey ID is testid and the AccessKey Secret is testsecret. The original request URL is as follows:

```
https://ddoscoo.cn-hangzhou.aliyuncs.com/?Action=DescribeInstances
&Region=cn 
&InstanceId=ddoscoo-cn-XXXX1
&TimeStamp=2016-02-23T12:46:24Z 
&Format=XML 
&AccessKeyId=testid 
&SignatureMethod=HMAC-SHA1
&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf 
&Version=2017-12-28
&SignatureVersion=1.0 

```

Perform the following steps to calculate the signature:

1.  Use the request parameters to create the string to be signed.

    ```
    GET&%2F&AccessKeyId%3Dtestid&Action%3DDescribeDomainNames&Region%3Dcn&InstanceId%3Dwaf_elasticity-cn-0xldbqtm005&Format%3DXML&SignatureMethod%3DHMAC-SHA1&SignatureNonce%3D3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&SignatureVersion%3D1.0&TimeStamp%3D2016-02-23T12%253A46%253A24Z&Version%3D2018-01-17 
    
    ```

2.  Calculate the HMAC value of the string.

    Append an ampersand \(&\) to the AccessKey Secret and use this string as the key to calculate the HMAC value. In this example, the key is `testsecret&`.

    ```
    CT9X0VtwR86fNWSnsc6v8YGOjuE=
    
    ```

3.  Add the signature to the request URL:

    ```
    https://ddoscoo.cn-hangzhou.aliyuncs.com/?Action=DescribeInstances
    &Region=cn 
    &InstanceId=ddoscoo-cn-XXXX1
    &TimeStamp=2016-02-23T12:46:24Z 
    &Format=XML 
    &AccessKeyId=testid 
    &SignatureMethod=HMAC-SHA1 
    &SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf 
    &Version=2017-12-28
    &SignatureVersion=1.0 
    &Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D 
    
    ```


