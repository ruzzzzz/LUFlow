# Overview
LUFlow is an flow-based intrusion detection data set which contains a robust ground truth through correlation with threat intelligence services. 
LUFlow contains telemetry containing emerging attack vectors through the composition of honeypots within Lancaster University's address space.
The labelling mechanism is autonomous, enabling the constant capture, labelling and publishing of telemetry to this repository.
Flows which were unable to be determined as malicious, but are not part of the normal telemetry profile are labelled as outliers. These are included to encourage further analysis to discover the true intent behind their actions. Known normal traffic is also captured from production services, e.g. ssh and database traffic, and included in this data set.

This data set is constantly updated using the [Citrus](https://github.com/ruzzzzz/Citrus) framework. This repository is structured into the year and month the telemetry was captured. For example, to find telemtry captured within September 2020, the folder 2020/09 is used.

# Features
The telemetry is captured using Cisco's [Joy](https://github.com/cisco/joy) tool. This tool records multiple measurements associated with flows.
Features are engineered from these measurements, which are outlined below:

| Name | Description |
| --- | --- |
| src_ip | The source IP address associated with the flow. This feature is anonymised to the corresponding Autonomous System |
| src_port | The source port number associated with the flow. | 
| dest_ip | The destination IP address associated with the flow. The feature is also anonymised in the same manner as before. 
| dest_port | The destination port number associated with the flow |
| protocol | The protocol number associated with the flow. For example TCP is 6 |
| bytes_in | The number of bytes transmitted from source to destination |
| bytes_out | The number of bytes transmitted from destination to source. |
| num_pkts_in | The packet count from source to destination |
| num_pkts_out | The packet count from destination to source |
| entropy | The entropy in bits per byte of the data fields within the flow. This number ranges from 0 to 8. |
| total_entropy | The total entropy in bytes over all of the bytes in the data fields of the flow |
| mean_ipt | The mean of the inter-packet arrival times of the flow |
| time_start | The start time of the flow in seconds since the epoch. |
| time_end | The end time of the flow in seconds since the epoch |
| duration | The flow duration time, with microsecond precision |
| label | The label of the flow, as decided by Tangerine. Either benign, outlier, or malicious |
