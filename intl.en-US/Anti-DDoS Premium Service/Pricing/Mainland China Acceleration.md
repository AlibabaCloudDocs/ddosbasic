# Mainland China Acceleration {#concept_dmb_1fg_4gb .concept}

If your business servers are deployed in regions outside mainland China, you can purchase Mainland China Acceleration \(MCA\) for your Anti-DDoS Premium instances to accelerate the access to your business for users in mainland China.

MCA provides users in mainland China with low-latency access to the businesses deployed in regions outside mainland China. This significantly improves the response time when the business is not under attack.

**Note:** MCA cannot be configured independently. MCA instances do not have any mitigation capabilities and must be used with Anti-DDoS Premium Insurance Plan or Unlimited Plan instances.

For more information about the applicable scenarios, see [Scenarios](reseller.en-US/Anti-DDoS Premium Service/Product Introduction/Scenarios.md#).

After purchasing MCA instances, you can use these instances with Anti-DDoS Premium Insurance Plan instances or Unlimited Plan instances to increase the access speed when your business is not under an attack, as shown in [Configure Anti-DDoS Premium MCA](reseller.en-US/Anti-DDoS Premium Service/Quick Start/Configure Anti-DDoS Premium MCA.md#).

## Pricing {#section_tpf_shg_4gb .section}

The pricing details of Anti-DDoS Premium MCA are shown in the following table.

|Business bandwidth|Price \(USD/month\)|
|------------------|-------------------|
|10 Mbps|1,548|
|20 Mbps|3,096|
|30 Mbps|4,643|
|40 Mbps|6,191|
|50 Mbps|7,739|
|60 Mbps|9,287|
|70 Mbps|10,834|
|80 Mbps|12,382|
|90 Mbps|13,930|
|100 Mbps|15,478|

**Note:** Business bandwidth refers to the maximum normal business bandwidth that can be processed by Anti-DDoS Premium MCA instances when your business is not under attack. Make sure that the business bandwidth of the instance is greater than the peak value of the inbound and outbound traffic of all services connected to the MCA instance.

If the actual traffic volume exceeds the maximum business bandwidth, your business may be subject to traffic restrictions or random packet losses, and your normal business may be unavailable, slowed, or delayed for a certain period of time.

Anti-DDoS Premium MCA instances provide the following business specifications by default:

**Note:** The specification of the MCA instance must be consistent with the corresponding instance business specifications of Anti-DDoS Premium Insurance Plan or Unlimited Plan.

|Business specifications|Descriptions|Default values|
|-----------------------|------------|--------------|
|Number of protected ports|The number of TCP/UDP ports that can be protected by the instance.|The default number is 5. The number of ports must be the same as that of ports to be protected of the Anti-DDoS Premium Insurance Plan instances or the Unlimited Plan instances.|
|Number of protected domains|The number of HTTP/HTTPS domains that can be protected by the instance.|The default number is 10. The number of protected domains must be the same as that of domains to be protected of the Anti-DDoS Premium Insurance Plan instances or the Unlimited Plan instances.**Note:** Every 10 protected domain names contain only one top-level domain and the subdomains or wildcard domains of this top-level domain.

|
|Business QPS|The maximum concurrent HTTP/HTTPS requests per second supported when the system is not under attack.|500 QPS|

