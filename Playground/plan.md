### Index

Page | Link |
----|----------|
K-ONE 공용개발환경의 개요 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/readme.md)
K-ONE 공용개발환경의 개념 및 설계 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/concept.md) |
K-ONE 공용개발환경의 구성현황 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/status.md) |
K-ONE 공용개발환경의 활용사례 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/usecases.md) |
K-ONE 공용개발환경의 개선계획 | [link](https://github.com/K-OpenNet/K-ONE/blob/master/Playground/plan.md) |

# K-ONE 공용개발환경 개선 계획
K-ONE 컨소시엄에서는 개발자마다 상이한 테스트베드 환경을 요구하는 연구개발 실증을 효과적으로 지원하기 위하여 크게 2가지 개선방안을 계획하고 있습니다.

![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5BK-ONE_Playground%5DFuturePlan_Composable_Playground.png)
- Cloud-Native Computing 패러다임의 등장으로 물리/가상/컨테이너 박스를 다양하게 조합하는 p(물리)+v(가상)+c(컨테이너)-Harmonized 인프라가 일반적인 구성으로 자리잡고 있습니다. 

- 예를 들어 복수의 물리박스가 바로 제공되는 p 인프라, 물리박스 상에 구성된 OpenStack 클라우드를 제공하는 p+v 인프라, 물리박스 클러스터 - OpenStack 클라우드 - CNCF Kubernetes 클러스터로 구성되는 p+v+c 인프라 등 다양한 인프라 구성이 유연하게 활용되고 있습니다.

- 따라서 K-ONE Tower를 중심으로 K-ONE 과제를 통해 개발한 SmartX Provisioning Framework와 OpenStack-MultiView Framework를 적용하여, 멀티사이트 K-Cluster로부터 p+v+c 박스들을 유연하게 조립(Compose)함으로써, 공유된 멀티사이트 인프라 상에 복수의 가상 인프라를 동적으로 구축할 수 있도록 고도화된 K-ONE 공용개발환경인 p+v+c Composable Playground를 달성하는 것을 목표로 하고 있습니다. 

- Composable K-ONE Playground를 활용하면 개발자들이 각자 요구하는 테스트베드 구성에 맞춘 실증환경을 제공해 줄 수 있습니다.

![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5BK-ONE_Playground%5DFuturePlan_SecurityResearchSupport.png)
- K-ONE 공용개발환경은 데이터 중심의 지능화된 보안 기술 연구를 위한 멀티사이트 실증환경을 제공하고, 동시에 개발된 기술을 적용하여 공용개발환경의 보안성 측면을 개선할 계획입니다.

- K-Post는 방화벽, 네트워크 장비의 접근 제어, 박스 내의 bpftable (eBPF 기반으로 동작하는 개선된 iptables)를 소프트웨어로 자동으로 관제함으로써 클러스터 범위의 다경계 (Multi-Perimeter) 보안을 제공합니다.

- K-ONE Tower의 Integrated Security Center는 각 사이트의 K-Post들을 관제함으로써 단일 클러스터 범위에 적용된 보안 기능을 멀티사이트 규모에서 조율합니다.

- 그리고 K-Post는 클러스터 내부의 보안 데이터를 수집하여 K-ONE Tower의 DataLake Box로 전달하게 되며, Intelligence Box는 저장된 데이터를 분석 엔진으로 통해 처리하여 보안 취약점 및 이상 징후를 탐지합니다. 탐지된 정보는 K-ONE DevOps Center의 Visibility 기능을 통해 가시화 되며, 동시에 Integrated Security Center에 전달되어 보안성 개선을 위한 조율을 수행하게 됩니다.
