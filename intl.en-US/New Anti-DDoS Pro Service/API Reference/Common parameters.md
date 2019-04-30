# Common parameters {#reference1886 .reference}

This topic describes the common parameters required by Anti-DDoS Pro APIs.

## Common request parameters { .section}

Common request parameters refer to the request parameters that all APIs require.

|Name|Type|Required|Description|
|Region|String|Yes|The region where the Anti-DDoS Pro instance is located. Valid value: cn-hangzhou.|
|InstanceId|String|Yes|The ID of the Anti-DDoS Pro instance.|
|Format|String|No|The format of the response. Valid value \(default\):-   JSON
-   XML

|
|Version|String|Yes|The version of the API in the format of YYYY-MM-DD. Valid value: 2017-12-28.|
|AccessKeyId|String|Yes|The AccessKey ID of the API caller.|
|Signature|String|Yes|The signature of the request.|
|SignatureMethod|String|Yes|The algorithm that is used to calculate the signature. Valid value: HMAC-SHA1.|
|Timestamp|String|Yes|The timestamp when the request is signed. The UTC time in ISO-8601 format: YYYY-MM-DDThh:mm:ssZ. For example, 2013-01-10T12:00:00Z indicates 20:00:00, January 10, 2013 Beijing time.|
|SignatureVersion|String|Yes|The version of the signature algorithm. Valid value: 1.|
|SignatureNonce|String|Yes|The unique random number that is used to prevent replay attacks. You must use different random numbers for different requests.|
|ResourceOwnerAccount|String|No|The account owner of the requested resources. Set the value to the logon username.|

**Examples**

```language-shell
https://ddoscoo.cn-hangzhou.aliyuncs.com/?Action=DescribeInstances
&Region=cn
&InstanceId=ddoscoo-cn-XXXX1 
&Timestamp=2014-05-19T10%3A33%3A56Z
&Format=xml
&AccessKeyId=testid
&SignatureMethod=Hmac-SHA1
&SignatureNonce=NwDAxvLU6tFE0DVb
&Version=2017-12-28 
&SignatureVersion=1.0
&Signature=Signature

```

## Common response parameters { .section}

The API response uses a unified format. A 2XX HTTP status code is returned if the call is successful. A 4xx or 5xx HTTP status code is returned if the call has failed. The responses can be returned in JSON or XML format. The XML format is used by default. You can specify the format when calling an API.

Each time you send an API call, the system returns a unique identifier RequestId, no matter whether the invocation is successful or not.

-   XML format

    ```language-xml
    <? xml version="1.0" encoding="utf-8"? > 
        <!—The root node of the response-->
        <API name+Response>
            <!—The request tag returned-->
            <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId> 
            <!—The response data-->
        </API name+Response>
    
    ```

-   JSON format

    ```language-json
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*The response data*/
        }
    
    ```


