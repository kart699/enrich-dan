## dan   
  https://www.dan.me.uk/torlist/ 

### Overview
 dan provides with list of IP  used to create Tor ban list

#### dan IP feed
This feed includes
- Tor begin nodes
- Tor exit nodes

##### PRE-REQUISITES to use dan and DNIF  
Outbound access required to request dan IP feed API

| Protocol   | Source IP  | Source Port  | Direction	 | Destination Domain | Destination Port  |  
|:------------- |:-------------|:-------------|:-------------|:-------------|:-------------|  
| TCP | AD,A10 | Any | Egress	| github.com | 443 |
| TCP | AD,A10 | Any | Egress	| dan.me.uk | 443 | 

### Using the dan feed API
 The dan feed API is found on github at

https://github.com/dnif/enrich-dan

#### Getting started with badips feed API

1. #####    Login to your AD, A10 containers  
   ACCESS DNIF CONTAINER VIA SSH : [Click To Know How](https://dnif.it/docs/guides/tutorials/access-dnif-container-via-ssh.html)
2. #####    Move to the ‘/dnif/<Deployment-key/enrichment_plugins’ folder path.
```
$cd /dnif/CnxxxxxxxxxxxxV8/enrichment_plugins/
```
3. #####   Clone using the following command  
```  
git clone https://github.com/dnif/enrich-dan.git dan
```
### API feed output structure
  | Fields        | Description  |
| ------------- |:-------------:|
| EvtType      | An IP |
| EvtName      | The IOC      |
| IntelRef | Feed Name      |
| IntelRefURL | Feed URL      |
| ThreatType | DNIF Feed Identification Name |      

An example of API feed output
```
{'EvtType': 'IPv4',
'EvtName': '129.10.115.241',
'AddFields': {
'IntelRef': ['DAN'],
'IntelRefURL': ['https://www.dan.me.uk/torlist/'],
'ThreatType': ['torlist'] }}
```
