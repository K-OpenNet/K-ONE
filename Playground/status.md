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

## K-Cluster 배포
<sub>현재 K-ONE 공용개발환경은 위의 구성도와 같이 국내 5개의 사이트(GIST, KAIST, SSU, KU, POSTECH)에 융합형 자원 박스들로 구성된 K-Cluster가 배포되었고, 이들을 KOREN/KREONET 네트워크로 연동함으로써 멀티-사이트 실증 환경이 구축된 상태입니다.</sub>

<sub>멀티-사이트 실증을 제공하기 위해 국내 5개의 사이트 별로 클라우드 환경을 구성한 후, 사이트 사이의 상호연결성(Inter-connect)을 위해 각 사이트에 가상스위치, 가상라우터 VNF를 자동으로 배치합니다. 그리고 SDN 제어기를 활용하여 VxLAN 기반의 L2 연결 또는 BGP 기반의 L3 연동을 자동화함으로써 SDN/NFV/Cloud를 활용하는 멀티-사이트 인프라 실증 환경이 구축됩니다. 마지막으로, 각 사이트 별로 구성된 독립적인 오픈스택 클라우드의 인증 정보를 중앙에서 관리하는 멀티-리전(Multi-Region) 실증 환경을 제공할 수 있습니다.</sub>

## K-ONE Tower 구축
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DK-ONE_Playground_Current_Tower_config1.png)
![alt tag](https://github.com/K-OpenNet/K-ONE/blob/master/WWW/images/playground/%5B190123%5DK-ONE_Playground_Current_Tower_config2.png)
