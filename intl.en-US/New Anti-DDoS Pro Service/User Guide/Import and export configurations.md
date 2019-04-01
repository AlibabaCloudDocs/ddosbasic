# Import and export configurations {#concept_xkh_kj3_kgb .concept}

Anti-DDoS Pro provides batch import and export features to help you quickly download or migrate domain configurations and forwarding rules.

-   You can import and export layer 4 forwarding rules in TXT files.
-   You can import and export domain configurations in XML files, which offer better compatibility. The XML format also provides better readability and extensibility than the TXT format. Meanwhile, you can import and export the configurations of websites that only have their origin server domain names specified.

## Batch import domain configurations {#section_jhg_f43_kgb .section}

1.  Log on to the [Anti-DDoS Pro console](https://yundun.console.aliyun.com/?p=ddoscoo&__consolePageCode=ddoscoo).
2.  In the left-side navigation pane, choose **Management** \> **Websites** and click **Batch Domains Import** at the end of the website list to add multiple domain configurations.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483136941_en-US.png)

3.  In the Add Multiple Rules dialog box that appears, enter the configuration parameters in XML format.

    **Note:** You can copy and paste the contents of the text box.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483136942_en-US.png)

    **XML format**

    Each XML file must start with `<DomainList>` and end with `</DomainList>`. You must enter all domain configurations between these tags. Each domain configuration must start with `<DomainConfig>` and end with `</DomainConfig>`. You must enter all parameters of a domain between these tags. For more information about these parameters, see the following table.

    **Note:** Each domain configuration corresponds to a `<DomainConfig>…… </DomainConfig>` tag pair.

    |XML parameter|Description|
    |`<Domain>a.com</Domain>`|The domain to be configured. You can only enter one domain.|
    |`<ProtocolConfig>``<ProtocolList>http,https</ProtocolList>``</ProtocolConfig>`|The Web protocols used by the domain. Separate multiple protocols with commas \(,\). In this example, the protocols used by the domain are HTTP and HTTPS.|
    |`<InstanceConfig>``<InstanceList>ddoscoo-cn-4590lwcny001</InstanceList>``</InstanceConfig>`|The Anti-DDoS Pro instance that is configured for the domain.**Note:** Each Anti-DDoS Pro instance has only one IP address. You can just enter the instance ID. Separate multiple instance IDs with commas \(,\).

|
    |`<RealServerConfig>``<ServerType>0</ServerType>``<ServerList>1.2.3.4</ServerList>``</RealServerConfig>` |Information about the origin server .    -   `<ServerType>0</ServerType>` indicates that the IP address of the origin server is specified.
    -   `<ServerType>1</ServerType>` indicates that the domain of the origin server is specified.
`<ServerList>1.2.3.4</ServerList>` indicates the address of the origin server. Separate multiple addresses with commas \(,\).**Note:** For each domain, you can only specify either the IP address or the domain of the origin server as the address of the origin server.

|

    **Sample**

    ```
    <DomainList>
     <DomainConfig> 
     <Domain>a.com</Domain> 
     <ProtocolConfig>
     <ProtocolList>http,https</ProtocolList> 
     </ProtocolConfig>
     <InstanceConfig>
     <InstanceList>ddoscoo-cn-4590lwcny001</InstanceList>
     </InstanceConfig>
     <RealServerConfig> 
     <ServerType>0</ServerType> 
     <ServerList>1.2.3.4</ServerList>
     </RealServerConfig> 
     </DomainConfig> 
     <DomainConfig> 
     <Domain>b.com</Domain> 
     <ProtocolConfig> 
     <ProtocolList>http,websocket,websockets</ProtocolList>
     </ProtocolConfig>
     <InstanceConfig>
     <InstanceList>ddoscoo-cn-mp90oeort002,ddoscoo-cn-0pp0o5vz500d</InstanceList> 
     </InstanceConfig> 
     <RealServerConfig>
     <ServerType>1</ServerType>
     <ServerList>q840a82zf2j23afs.gfvip05al.com</ServerList>
     </RealServerConfig>
     </DomainConfig> 
     </DomainList> 
    ```

4.  Click **Next**. If the XML file is correctly formatted, the domain configurations you have entered are displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483136943_en-US.png)

5.  Select the domain configurations you want to import and click **OK** to import these domain configurations.

## Batch export domain configurations {#section_tk4_p43_kgb .section}

1.  In the left-side navigation pane, choose **Management** \> **Websites** and click **Batch Domains Export** at the end of the website list. In the dialog box that appears, click **OK** to export domain configurations.
2.  On the Websites page, click the button in the upper-right corner to view the progress of the export task.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483236945_en-US.png)

3.  After the task is complete, click **Download** in the Tasks dialog box to download domain configurations to your local computer.

    **Note:** If the task status is **Pending Export**, wait for the task to complete.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483236946_en-US.png)


## Batch import forwarding rules {#section_tgz_t43_kgb .section}

1.  In the left-side navigation pane, choose **Management** \> **Port Settings** and click **Batch Operations** at the end of the rules list. Choose **Create Rule** to configure multiple forwarding rules.

    **Note:** You can also choose **Session Persistence/Health Check** or **DDoS Protection Policy Settings** to add corresponding settings.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483236947_en-US.png)

2.  Follow the given examples to enter rules.
    -   Create forwarding rules

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483236948_en-US.png)

    -   Create session persistence/health check settings

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483236949_en-US.png)

    -   Create anti-DDoS protection policies

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483236950_en-US.png)

3.  Click **OK** to add settings.

## Batch export forwarding rules {#section_a3m_y43_kgb .section}

1.  In the left-side navigation pane, choose **Management** \> **Port Settings** and click **Batch Export** at the end of the rules list. Choose **Export Rule** and click **OK** to export forwarding rules.

    **Note:** You can also choose **Export Session/Health Settings** or **Export Anti-DDoS Protection Policy** to export corresponding settings.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79699/155411483236952_en-US.png)

2.  On the Port Settings page, click the button in the upper-right corner to view the progress of the export task.
3.  After the task is complete, click **Download** in the Tasks dialog box to download forwarding rules to your local computer.

    **Note:** If the task status is **Pending Export**, wait for the task to complete.


