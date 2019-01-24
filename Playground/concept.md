### Index

Page | Link |
----|----------|
K-ONE 공용개발환경의 개요 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/readme.md)
K-ONE 공용개발환경의 개념 및 설계 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/concept.md) |
K-ONE 공용개발환경의 구성현황 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/status.md) |
K-ONE 공용개발환경의 활용사례 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/usecases.md) |
K-ONE 공용개발환경의 개선계획 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/plan.md) |

# K-ONE 공용개발환경 개념 및 설계
<?--
## 기술적 배경
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5D5G-leveraged_Converged_SDI.png)
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DOpen-Source_SW_and_HW.png)
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DSmartX_Composable_Playground_and_Boxes.png)
--?>

K-ONE 공용개발환경은 에지 클라우드 형태의 클러스터 테스트베드 모델인 K-Cluster를 기본요소로 하여, 이를 멀티사이트에 분산 배포하고 네트워크로 상호 연계한 멀티사이트 에지 클라우드 테스트베드를 추구하고 있습니다. K-ONE 공용개발환경의 개념 및 역할을 이해하려면 가장 핵심 요소인 K-Cluster를 이해하고, 멀티사이트로 배포된 복수의 K-Cluster를 하나로 묶는 K-ONE 타워를 중심으로 확장하는 멀티사이트 K-ONE 공용개발환경의 전체 설계에 대해 이해하는 것이 필요합니다.

## K-Cluster의 개념
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/K-Cluster_Concept_Design-v0.3.png)

K-Cluster는 SDN/NFV/Cloud 기반의 소프트웨어-정의 인프라 기술을 통합적으로 실증할 수 있는 경제적인 소규모 클러스터를 의미합니다. 통합적인 공용개발환경을 제공하기 위해 SDN/NFV에 대응하는 미들박스 역할을 수행하면서 클라우드 자원 클러스터를 제공하는 Edge-Cloud 모델에 대응해야 하며, 동시에 사물인터넷에서 발생하는 데이터를 신속하게 처리하기 위해 유연한 네트워킹 또한 제공될 필요가 있습니다. 이를 위해서 K-Cluster를 융합형 화이트 박스로 구성하고 중앙의 DevOps 도구들로 K-Cluster 전체를 자동 관리함으로써 데이터 중심의 다양한 서비스 실증을 할 수 있는 경제적인 테스트베드로 구성해야 합니다.

K-Cluster의 정의 및 요구사항에 기반하여 K-Cluster를 위의 그림과 같은 구성으로 설계합니다. K-Cluster를 구성하고 있는 K-Tower, K-Cube, K-Fabric, 그리고 사물인터넷 연계를 위한 IoT-Cloud Hub 항목에 대해서는 아래와 같이 설명할 수 있습니다.

* **K-Post:** K-Cluster 전체를 DevOps 관점에서 자동 관리 및 운영하기 위해 박스의 관제(Monitor & Control)를 전담하며, 동시에 K-Cluster의 대표 인터페이스 역할을 수행

* **K-Cube:** 동종의 K-Small 박스들로 구성된 Compute/Storage/Networking 자원 클러스터로 SDN/NFV/Cloud를 위한 자원을 제공하는 역할을 수행

* **K-Fabric:** 오픈소스 네트워킹 박스인 K-Switch들로 구성되며, K-Cluster 중앙에 위치하여 구성 요소 사이의 빠르고 유연하며 안정된 연결성을 제공하는 역할을 수행

* **IoT-Cloud Hub**: K-Cluster를 사물인터넷과 연계하여 개발 및 실증할 필요가 있을 때, K-Cluster와 IoT Things 사이의 연결성을 제공하는 교두보 역할을 수행. IoT-Cloud Hub는 GIST에 위치하는 K-Cluster 모델에 시험적으로 적용 및 검증을 진행중.

## K-ONE 공용개발환경 구축설계
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DK-ONE_Playground_design.png)

앞서 설명한 기본 개념들을 기반으로 K-ONE 공용개발환경은 위의 그림과 같이 설계되었습니다. 공용개발환경을 구성하는 핵심 자원 클러스터인 K-Cluster를 K-ONE 컨소시엄 참여기관에 배포한 후, 이를 국내 선도 연구망인 KREONET을 통해 1G/10G 급으로 상호 연동하여 멀티사이트 클러스터 자원을 준비합니다.

그리고 K-ONE 타워를 구축하여 운영자에게는 멀티사이트 클러스터를 대상으로 한 효율적인 운영을 위한 DevOps 도구를 개발 및 운영할 수 있는 자원을 제공하고, 동시에 개발자에게는 멀티사이트 인프라 실증을 손쉽게 수행할 수 있도록 자원을 제공합니다. 초기에는 자동화된 공용개발환경에 집중하여 K-ONE DevOps Center의 구축만을 고려하였으나 공용개발환경을 운영하면서 겪었던 보안 위협과 데이터 중심의 지능화된 인프라 연구동향의 저변 확대에 대응하기 위해 K-ONE Integrated Security Center, SmartX Datalake Box, SmartX Intelligence Box를 추가한 K-ONE 타워의 구성을 설계하였습니다.
