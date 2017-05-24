### K-Cluster 중심의 K-ONE 공용개발환경
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/K-Cluster-centric_K-ONE_Playground.png)

<sub>K-ONE 공용개발환경(Playground)은 K-ONE 컨소시엄의 SDN/NFV/Cloud 오픈소스 프로젝트 공동 개발 및 실증 환경을 제공하기 위해서, Edge-Cloud 모델에 대응하는 클러스터형 테스트베드 K-Cluster와 단일 클러스터로 실증이 어려운 멀티-사이트, 멀티-도메인 관련 실증을 통합적으로 제공하기 위해 국내 다수 지역(GIST, KAIST, SSU, KU, POSTECH)에 상기 K-Cluster를 분산 배포하고, 네트워크로 연동하여 구축된 멀티-사이트 클러스터 테스트베드를 의미합니다. 더 나아가 글로벌 개발자 생태계를 구성하기 위해서 국내 다수 지역에 분포하는 OF@KOREN Playround와 EU 및 동남아시아를 중심으로 하는 OF@TEIN Playground까지 연계를 구상하고 있습니다.</sub>


<sub>K-ONE 공용개발환경은 SDN/NFV/Cloud에 초점이 맞춰진 오픈소스 네트워킹 소프트웨어 개발을 위한 글로벌 개발자 생태계로써 의의가 있습니다. 오픈소스 개발자는 K-ONE 공용개발환경을 통해 Compute/Storage/Networking으로 구성된 초-융합형(Hyper-Converged) Box 자원을 동적으로 재구성하여 활용할 수 있습니다. 이는 오픈소스 개발자가 SDN/NFV/Cloud 통합으로 구성되는 미래형 소프트웨어-정의 인프라(SDI)를 실증적으로 개발할 수 있는 환경을 제공합니다.</sub>

## K-Cluster
### K-Cluster의 컨셉 디자인
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/K-Cluster_Concept_Design-v0.3.png)

<sub>K-Cluster는 SDN/NFV/Cloud 기반의 소프트웨어-정의 인프라 기술을 통합적으로 실증할 수 있는 경제적인 소규모 클러스터를 의미합니다. 통합적인 공용개발환경을 제공하기 위해 SDN/NFV에 대응하는 미들박스 역할을 수행하면서 클라우드 자원 클러스터를 제공하는 Edge-Cloud 모델에 대응해야한다. 동시에 사물인터넷에서 발생하는 데이터를 신속하게 처리하기 위해 유연한 네트워킹 또한 제공될 필요가 있습니다. 이를 위해서 K-Cluster를 융합형 화이트 박스로 구성하고 중앙의 DevOps 도구들로 K-Cluster 전체를 자동 관리함으로써 데이터 중심의 다양한 서비스 실증을 할 수 있는 경제적인 테스트베드로 구성해야 합니다.</sub>

<sub>K-Cluster의 정의 및 요구사항에 기반하여 K-Cluster를 위의 그림과 같은 구성으로 설계합니다. K-Cluster를 구성하고 있는 K-Tower, K-Cube, K-Fabric, 그리고 사물인터넷 연계를 위한 IoT-Cloud Hub 항목에 대해서는 아래와 같이 설명할 수 있습니다.</sub>

* <sub>**K-Tower:** K-Cluster 전체를 DevOps 관점에서 자동 관리 및 운영하기 위해 박스의 관제(Monitor & Control)를 전담하며, 동시에 K-Cluster의 대표 인터페이스 역할을 수행</sub>

* <sub>**K-Cube:** 동종의 K-Small 박스들로 구성된 Compute/Storage/Networking 자원 클러스터로 SDN/NFV/Cloud를 위한 자원을 제공하는 역할을 수행</sub>

* <sub>**K-Fabric:** 오픈소스 네트워킹 박스인 K-Switch들로 구성되며, K-Cluster 중앙에 위치하여 구성 요소 사이의 빠르고 유연하며 안정된 연결성을 제공하는 역할을 수행</sub>

* <sub>**IoT-Cloud Hub:** 사물인터넷과 K-Cluster와의 연계하기 위한 교두보 역할을 수행</sub>

### K-ONE 공용개발환경 구성현황도
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/%5B170104%5DK-ONE_Playground_Current_Configuration.png)



<!--

K-ONE 공용개발환경 은 오픈소스 네트워킹 소프트웨어 R&D 개발을 위한 글로벌 개발자 생태계입니다.<br>
K-ONE IoT Cloud Testbed is global developer environment for R&D on opensource networking software.

이 공용개발환경은 GIST주도로 진행되고 있으며, [SmartFIRE FP7 FIRE 공동연구와 OF@TEIN 커뮤니티 활동](http://opennetworking.kr/projects/k-one-playground/wiki/SmartFIRE_FP7_FIRE_&_OF@TEIN) 을 통해 EU 및 동남아시아를 중심으로 한 30여개 기관에 속한 글로벌 개발자 생태계 구성을 시도하는 것이 가능한 상태입니다.

개발자가 구상하는 응용의 목적 및 요구사항에 맞춰 SmartX Box들로 구성된 자원집합 인프라를 만들고, 이를 설정 및 제어, 그리고 가시화하는 요소 기술은 매우 중요합니다. 따라서 K-ONE 공용개발환경을 활용하면서 융합형 SmartX Box자원을 각 개발자에게 동적으로 재구성하는 것은 필수적입니다. 이때 단일화된 Box 개념의 공통 하드웨어로 준비된 융합형 SmartX Box(Type B*, Type C, Type S, Type M 등)를 이용하면 효과적으로 SDN/NFV/Cloud 통합으로 구성되는 미래형 소프트웨어-정의 인프라를 실증적으로 구현하면서 활용할 수 있습니다.

아래는 K-ONE 공용개발환경에 대한 전체적인 다이어그램입니다.

### K-Cluster 중심의 K-ONE 공용개발환경
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/K-Cluster-centric_K-ONE_Playground.png)

### K-Cluster의 컨셉 디자인
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/K-Cluster_Concept_Design-v0.3.png)

### K-ONE 공용개발환경 구성현황도
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/%5B170104%5DK-ONE_Playground_Current_Configuration.png)
-->

<!--

# K-ONE Playground

K-ONE 공용개발환경 은 오픈소스 네트워킹 소프트웨어 R&D 개발을 위한 글로벌 개발자 생태계입니다.<br>
K-ONE IoT Cloud Testbed is global developer environment for R&D on opensource networking software.

이 공용개발환경은 GIST주도로 진행되고 있으며, [SmartFIRE FP7 FIRE 공동연구와 OF@TEIN 커뮤니티 활동](http://opennetworking.kr/projects/k-one-playground/wiki/SmartFIRE_FP7_FIRE_&_OF@TEIN) 을 통해 EU 및 동남아시아를 중심으로 한 30여개 기관에 속한 글로벌 개발자 생태계 구성을 시도하는 것이 가능한 상태입니다.

개발자가 구상하는 응용의 목적 및 요구사항에 맞춰 SmartX Box들로 구성된 자원집합 인프라를 만들고, 이를 설정 및 제어, 그리고 가시화하는 요소 기술은 매우 중요합니다. 따라서 K-ONE 공용개발환경을 활용하면서 융합형 SmartX Box자원을 각 개발자에게 동적으로 재구성하는 것은 필수적입니다. 이때 단일화된 Box 개념의 공통 하드웨어로 준비된 융합형 SmartX Box(Type B*, Type C, Type S, Type M 등)를 이용하면 효과적으로 SDN/NFV/Cloud 통합으로 구성되는 미래형 소프트웨어-정의 인프라를 실증적으로 구현하면서 활용할 수 있습니다.

아래는 K-ONE 공용개발환경에 대한 전체적인 다이어그램입니다.

### K-Cluster 중심의 K-ONE 공용개발환경
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/K-Cluster-centric_K-ONE_Playground.png)

### K-Cluster의 컨셉 디자인
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/K-Cluster_Concept_Design-v0.3.png)

### K-ONE 공용개발환경 구성현황도
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/images/%5B170104%5DK-ONE_Playground_Current_Configuration.png)


-->
