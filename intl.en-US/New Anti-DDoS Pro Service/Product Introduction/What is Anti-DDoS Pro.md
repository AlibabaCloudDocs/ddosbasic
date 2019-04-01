# What is Anti-DDoS Pro {#concept_69319_zh .concept}

Anti-DDoS Pro provides BGP bandwidth resources to help you mitigate massive DDoS attacks peaking at 1 Tbit/s. Compared with older versions, Anti-DDoS Pro currently supports more reliable networks with less latency, enabling quicker disaster recovery.

Anti-DDoS Pro provides the following benefits:

-   Maximum BGP bandwidth resources in mainland China. Supports mitigating 1.5 Tbit/s DDoS attacks.
-   Top-quality bandwidth resources covering eight major ISP networks in mainland China, including China Telecom, China Unicom, China Mobile, and CERNET.

Only one IP address is needed to quickly access different ISP networks in mainland China.

## Differences between older and current versions of Anti-DDoS Pro { .section}

| |Older version\(China Telecom, China Unicom, and China Mobile networks\)

|Older version\(BGP-line\)

|Current version|
|--|-------------------------------------------------------------------------|---------------------------|---------------|
|ISP networks|Only supports China Telecom, China Unicom, and China Mobile networks.|Supports multiple small and medium-sized ISPs' networks in addition to China Telecom, China Unicom, and China Mobile networks.|Supports multiple small and medium-sized ISPs' networks in addition to China Telecom, China Unicom, and China Mobile networks.|
|Network latency|Average latency of 30 ms in mainland Chinese regions. Cross-network access may occur when using networks provided by small-sized ISPs.|Average latency of 20 ms in mainland Chinese regions. No cross-network access is needed.|Average latency of 20 ms in mainland Chinese regions. No cross-network access is needed.|
|Dedicated line|Not supported. Traffic is forwarded back to the origin server through public networks with latency.|If the origin server is deployed on Alibaba Cloud services, traffic is forwarded back to the origin server through dedicated lines with negligible latency. Otherwise, traffic is forwarded back to the origin server through public networks.|If the origin server is deployed on Alibaba Cloud services, traffic is forwarded back to the origin server through dedicated lines with negligible latency. Otherwise, traffic is forwarded back to the origin server through public networks.|
|Disaster recovery|When a server fault occurs, automatic scheduling of layer 4 traffic is not supported. Due to DNS resolution limits, automatic scheduling of layer 7 traffic cannot take effect immediately.|Supports automatic scheduling of all traffic based on BGP routing. The switchover time can be within several seconds.|Supports automatic scheduling of all traffic based on BGP routing. The switchover time can be within several seconds.|
|IP addresses|Needs more than two IP addresses, which require more configuration workload.|Needs only one IP address.|Needs only one IP address.|
|Maximum protection capability|Supports mitigating up to 1 Tbit/s DDoS attack based on China Telecom or China Unicom networks.|Supports mitigating up to 100 Gbit/s DDoS attacks.|Supports mitigating up to 1.5 Tbit/s DDoS attacks.|
|Layer 4 protection capability|Supports mitigating flood attacks such as SYN floods, ACK floods, and ICMP floods. Filters out abnormal requests, empty requests, and requests from zombies.|The same.|The same.|
|Layer 7 protection capability|Supports mitigating HTTP flood attacks.|Supports mitigating HTTP flood attacks.|Supports mitigating HTTP flood attacks.|

## Scenarios { .section}

We recommend that you use Anti-DDoS Pro if you have the following needs:

-   Reliable networking that supports minimal latency, quick disaster recovery, and multiple ISP networks.
-   Basic protection that offers 20 Gbit/s or more BGP bandwidth.
-   Capability to mitigate DDoS attacks peaking at more than 300 Gbit/s.

