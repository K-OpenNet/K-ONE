### Index

Page | Link |
----|----------|
K-ONE 공용개발환경의 개요 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/readme.md)
K-ONE 공용개발환경의 개념 및 설계 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/concept.md) |
K-ONE 공용개발환경의 구성현황 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/status.md) |
K-ONE 공용개발환경의 활용사례 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/usecases.md) |
K-ONE 공용개발환경의 개선계획 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/plan.md) |

# K-ONE 공용개발환경 개념 및 설계
## 기술적 배경
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5D5G-leveraged_Converged_SDI.png)
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DOpen-Source_SW_and_HW.png)
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DSmartX_Composable_Playground_and_Boxes.png)

## K-Cluster의 컨셉 디자인
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/K-Cluster_Concept_Design-v0.3.png)

<sub>K-Cluster는 SDN/NFV/Cloud 기반의 소프트웨어-정의 인프라 기술을 통합적으로 실증할 수 있는 경제적인 소규모 클러스터를 의미합니다. 통합적인 공용개발환경을 제공하기 위해 SDN/NFV에 대응하는 미들박스 역할을 수행하면서 클라우드 자원 클러스터를 제공하는 Edge-Cloud 모델에 대응해야한다. 동시에 사물인터넷에서 발생하는 데이터를 신속하게 처리하기 위해 유연한 네트워킹 또한 제공될 필요가 있습니다. 이를 위해서 K-Cluster를 융합형 화이트 박스로 구성하고 중앙의 DevOps 도구들로 K-Cluster 전체를 자동 관리함으로써 데이터 중심의 다양한 서비스 실증을 할 수 있는 경제적인 테스트베드로 구성해야 합니다.</sub>

<sub>K-Cluster의 정의 및 요구사항에 기반하여 K-Cluster를 위의 그림과 같은 구성으로 설계합니다. K-Cluster를 구성하고 있는 K-Tower, K-Cube, K-Fabric, 그리고 사물인터넷 연계를 위한 IoT-Cloud Hub 항목에 대해서는 아래와 같이 설명할 수 있습니다.</sub>

* <sub>**K-Tower:** K-Cluster 전체를 DevOps 관점에서 자동 관리 및 운영하기 위해 박스의 관제(Monitor & Control)를 전담하며, 동시에 K-Cluster의 대표 인터페이스 역할을 수행</sub>

* <sub>**K-Cube:** 동종의 K-Small 박스들로 구성된 Compute/Storage/Networking 자원 클러스터로 SDN/NFV/Cloud를 위한 자원을 제공하는 역할을 수행</sub>

* <sub>**K-Fabric:** 오픈소스 네트워킹 박스인 K-Switch들로 구성되며, K-Cluster 중앙에 위치하여 구성 요소 사이의 빠르고 유연하며 안정된 연결성을 제공하는 역할을 수행</sub>

* <sub>**IoT-Cloud Hub**: K-Cluster를 사물인터넷과 연계하여 개발 및 실증할 필요가 있을 때, K-Cluster와 IoT Things 사이의 연결성을 제공하는 교두보 역할을 수행. IoT-Cloud Hub는 GIST에 위치하는 K-Cluster 모델에 시험적으로 적용 및 검증을 진행중.</sub>

## K-ONE 공용개발환경 구성설계
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DK-ONE_Playground_design.png)


