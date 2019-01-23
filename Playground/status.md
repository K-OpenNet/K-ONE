### Index
Page | Link |
----|----------|
K-ONE 공용개발환경의 개요 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/readme.md)
K-ONE 공용개발환경의 개념 및 설계 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/concept.md) |
K-ONE 공용개발환경의 구성현황 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/status.md) |
K-ONE 공용개발환경의 활용사례 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/usecases.md) |
K-ONE 공용개발환경의 개선계획 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/plan.md) |

# K-ONE Playground 구축 현황

## K-ONE Playground 전체 구축 현황도
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DK-ONE_Playground_Current_Overall_Config.png)
<sub>현재 K-ONE 공용개발환경은 위의 구성도와 같이 국내 5개의 사이트(GIST, KAIST, SSU, KU, POSTECH)에 융합형 자원 박스들로 구성된 K-Cluster가 배포되었고, 이들을 KOREN/KREONET 네트워크로 연동함으로써 멀티-사이트 실증 환경이 구축된 상태입니다.</sub>

<sub>멀티-사이트 실증을 제공하기 위해 국내 5개의 사이트 별로 클라우드 환경을 구성한 후, 사이트 사이의 상호연결성(Inter-connect)을 위해 각 사이트에 가상스위치, 가상라우터 VNF를 자동으로 배치합니다. 그리고 SDN 제어기를 활용하여 VxLAN 기반의 L2 연결 또는 BGP 기반의 L3 연동을 자동화함으로써 SDN/NFV/Cloud를 활용하는 멀티-사이트 인프라 실증 환경이 구축됩니다. 마지막으로, 각 사이트 별로 구성된 독립적인 오픈스택 클라우드의 인증 정보를 중앙에서 관리하는 멀티-리전(Multi-Region) 실증 환경을 제공할 수 있습니다.</sub>

## K-Cluster 배포
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/K-Cluster_Hardware_Specification.png)
K-Cluster를 구성하는 박스들은 다양한 후보 장비들을 심사숙고하는 과정을 통해 결정되어 위와 같은 형태로 구축되었습니다. 

전체 구축 현황도에서 설명하였듯 상기 구성의 K-Cluster를 K-ONE 컨소시엄 5개 사이트에 배포한 후 이들을 국내 첨단연구망인 KREONET을 통해 상호 L3 연결함으로써 멀티사이트 에지 클러스터 테스트베드 환경을 제공합니다.

## K-ONE Tower 구축
멀티사이트에 배포된 K-Cluster들을 중앙에서 통합 관제(Monitor & Control)하기 위한 K-ONE Tower의 하드웨어 박스들을 GIST 사이트에 구축하는 노력을 4차년도에 수행하였습니다. 

![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DK-ONE_Playground_Current_Tower_config1.png)
GIST 사이트의 K-ONE Rack 상에 K-ONE DevOps Center, K-ONE Integrated Security Center, SmartX DataLake Box를 위의 그림에 기술된 박스를 구매하여 추가하였습니다. 각 Box의 역할은 다음과 같습니다.

- K-ONE DevOps Center: 멀티사이트 인프라 규모의 Provisioning, Orchestration, Visibility 기능을 수행하는 박스 입니다. 운영자는 K-ONE DevOps Center 내에 DevOps 자동화 소프트웨어들을 설치 및 활용하여 멀티사이트 공용개발환경의 효과적인 운영이 가능합니다. 또한 K-ONE DevOps Center는 공용개발환경의 사용자인 개발자들도 활용할 수 있으며, 개발자들은 K-ONE DevOps Center 상에 멀티사이트를 대상으로 개발한 소프트웨어를 실행함으로써 멀티사이트 인프라 규모의 Cloud/SDN/NFV 실증을 수행할 수 있습니다.

- K-ONE Integrated Security Center: 공용개발환경의 보안을 총괄하는박스로써 각 사이트의 K-Post로부터 보안 관련 이벤트 정보들을 수신하고, 동시에 보안 취약점을 개선하기 위해 K-Post에 설정을 지시하는 작업을 수행합니다.

- SmartX DataLake Box: 멀티사이트에 배포된 K-Cluster로부터 발생하는 많은 양의 실시간 데이터를 저장하는 역할을 담당합니다. 본 DataLake Box 또한 개발환경 운영 측면의 데이터와 개발자의 멀티사이트 실증에서 발생하는 데이터를 모두 저장하도록 활용될 수 있습니다.

SmartX DataLake Box의 효과적인 운영을 위하여, 이를 단독 활용하는 것이 아니라 Ceph 클러스터 형태로 구성하여 활용하고 있습니다.

![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DK-ONE_Playground_Current_Tower_config2.png)데이터 중심의 지능화된 기술에 대한 연구 주제가 활발히 진행됨에 따라, 본 동향을 반영하는 Cloud/SDN/NFV 지능화 연구를 지원하기 위해 SmartX Intelligence Box를 K-ONE Tower 내에 구축하였습니다.

베어메탈 자원을 그대로 활용하는 분석 클러스터의 성능은 그대로 유지하면서 유연성 및 관리 효율성 측면의 단점을 개선할수 있도록, CNCF Kubernetes 클러스터 상에 Apache Spark의 워크로드를 컨테이너 형태로 쉽게 배포할 수 있는 컨테이너 기반의 분석 클러스터를 구성하여 운영하고 있습니다.
