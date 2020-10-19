LUFlow is an flow-based intrusion detection data set which contains a robust ground truth through correlation with threat intelligence services. 
LUFlow contains telemetry containing emerging attack vectors through the composition of honeypots within Lancaster University's address space.
The labelling mechanism is autonomous, enabling the constant capture, labelling and publishing of telemtry to this repository.

# Features
The telemetry is captured using Cisco's [Joy](https://github.com/cisco/joy) tool. This tool records multiple measurements associated with flows.
The features extracted from the telemetry are outlined below:

| Name | Description |
| --- | --- |
| src_ip | The source IP address associated with the flow. This feature is anonymised to the corresponding Autonomous System |
| src_port | The source port number associated with the flow. | 
