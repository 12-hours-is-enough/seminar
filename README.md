<div align= "center">
    <img src="https://capsule-render.vercel.app/api?type=waving&color=ecf566&height=180&text=💡%20MSA:A%20Tech%20Seminar&animation=&fontColor=ffffff&fontSize=50" />
    </div>
    
<br>

## 목차
1. [👥 팀 소개](#-team-12시간이-모자라)
2. [📋 세미나 개요](#-세미나-개요)
4. [📚 MSA 소개](#-MSA-소개)
5. [🏗️ MSA Architecture](#%EF%B8%8F-msa-architecture)
6. [🚀 모놀리식에서 MSA로 전환 전략](#-모놀리식에서-MSA로-전환-전략)
7. [📆 Q&A](#-QA)

<br>

## 👥 TEAM 12시간이 모자라
### 팀원 소개
<div align=center>


|<img src="https://avatars.githubusercontent.com/u/95984922?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/165532198?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/121565744?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/179544856?v=4" width="150" height="150"/>|
|:-:|:-:|:-:|:-:|
|나홍찬<br/>[@nahong_c](https://github.com/HongChan1412)|김소연<br/>[@ssoyeonni](https://github.com/ssoyeonni)|이은정<br/>[@eundeom](https://github.com/eundeom)|이은준<br/>[@2EunJun](https://github.com/2EunJun)|

</div>

<br><br>

## 📋 세미나 개요
많은 기업들이 도입하였으며, 앞으로도 기업들이 도입을 계획중인 **MSA소개와 처음 접하는 사람들의 쉽게 이해를 도울 수 있도록 함**

<br><br>
## 📚 MSA 소개
### 기존 모놀리식 소개
<img width="2446" alt="image" src="https://github.com/user-attachments/assets/81e9ab21-cc53-4376-b04c-099770a45995" />

> 모놀리식 : 모든 기능이 하나의 애플리케이션으로 통합된 구조로, 단순하지만 확장성과 유지보수에 어려움이 있음
---

### MSA 소개
<img width="2446" alt="image" src="https://github.com/user-attachments/assets/ac3c8294-b41d-4839-9635-4d7ddebddf9b" />

>MSA : 애플리케이션을 독립적인 작은 서비스들로 분리하여 운영하는 구조로, 유연성과 확장성이 뛰어나지만 초기 설계가 복잡함
---

### 모놀리식과 MSA 비교
<img width="2446" alt="image" src="https://github.com/user-attachments/assets/437aab2b-256c-4e75-a63d-15088a2c5075" />

> 모놀리식 : 단일 애플리케이션 구조, 단순하지만 유지보수 어려움, 하나의 공통 DB 사용 <br>
> MSA: 독립적인 작은 서비스들의 조합, 초기 설계는 복잡하지만 유지보수 용이, 서비스별 개별 DB 운영 가능 <br>
---

### MSA 전환 환경적 배경
<img width="2446" alt="image" src="https://github.com/user-attachments/assets/6404084d-5dcb-4d00-a489-43a71d5febca" />

> - 글로벌 서비스 확장 및 트래픽 증가: 전 세계 사용자 증가로 확장성과 가용성이 중요해짐 <br>
> - 멀티 디바이스 & IoT 환경 증가: 다양한 기기 환경에서의 서비스 제공 필요 <br>
> - 개인정보 보안 및 규제 강화: GDPR 등 글로벌 규제 준수를 위한 시스템 구축 필수 <br>
---

### MSA 전환 기술적 배경
<img width="2446" alt="image" src="https://github.com/user-attachments/assets/82faa773-9062-4ab8-a870-e2bfb1f0b4df" />

> - 클라우드 환경의 발전: 필요할 때 자원을 빠르게 확장할 수 있는 유연한 환경 조성 <br>
> - 컨테이너 & 오케스트레이션 기술 발전: 각 서비스가 독립적으로 운영되며 안정적이고 유연한 서비스 제공 <br>
> - CI/CD & DevOps 도구 발전: 배포 속도 향상, 자동 복구 및 운영 효율성 극대화 <br>
---

<br><br>
## 🏗️ MSA Architecture
### 전체 Architecture 소개
<img width="1693" alt="image" src="https://github.com/user-attachments/assets/aaca9acc-7b7c-4bd1-ae0b-3f4475cbbd0d" />

### 사용되는 기술
#### 1. Load Balancer
<img width="2372" alt="image" src="https://github.com/user-attachments/assets/90e7666c-f685-490b-a83f-5cfcc066f8c9" />

MSA 환경에서는 하나의 서비스가 여러개의 서버 인스턴스로 운영될 수 있음. <br>
이 환경에서 사용자가 인터넷을 통해 요청을 보내면, Load Balancer는 해당 요청을 여러 서버로 분배하여 처리함. <br>
<br>

> **Load Balancer 사용 이유**
> 1. 하나의 서버에 트래픽이 집중되는 것을 방지하고, 알고리즘을 사용해 부하를 분삼함. <br>
> 2. 특정 서버에 장애가 발생하더라도 정상적으로 동작하는 서버로 자동 전환함. <br>
> 3. 사용량이 증가하면 서버인스턴스를 추가하여 확장함. <br>
> 4. 클라이언트가 직접 서버와 통신하지 않고, Load Balancer를 거치므로 보안이 강화됨. <br>
---

#### 2. API Gateway
<img width="2446" alt="image" src="https://github.com/user-attachments/assets/c1b7a8ae-ce56-4827-9566-2c6539e491f0" />

API Gateway는 Load Balancer 와 Service 사이에 배치함. <br>
Load Balancer는 여러개의 API Gateway로 트래픽을 분해바게 되는데, API Gateway는 각 요청을 분석하여 적절한 Service로 전달하는 역할. <br>
<br>
> **API Gateway 사용 이유**
> 1. 클라이언트가 여러 Service를 직접 호출하는것은 비효율적이므로, API Gateway가 요청을 분석하고 적절한 Serice로 라우팅함. <br>
> 2. 각 Service마다 개별적으로 보안 설정을 적용하는 것은 어려우므로, API Gateway에서 인증 및 보안검증을 수행함. <br>
---

#### 3. Microservices
<img width="2271" alt="image" src="https://github.com/user-attachments/assets/2d4cf9e6-f6a1-455b-89d3-098fb49e7882" />

Microservice는 각 기능을 독립적인 Service로 개발 및 운영하는 방식. <br>
<br>
> **이상적인 Microservice의 구조**
> 1. 한 Service의 변경이 다른 Service에 영향을 주지 않아야함. <br>
> 2. Service별로 자체 데이터베이스를 관리해야함. <br>
> 3. Serivce간의 의존성을 최소화해야함. <br>
> 4. 특정 Service에 트래픽이 증가할 경우 해당 Serivce만 확장할 수 있도록 설계해아함. <br>
---

#### 4. Containerization
<img width="2284" alt="image" src="https://github.com/user-attachments/assets/24c27414-c60e-4ea2-abd7-0d9ae3bbd67d" />

Microservice를 효과적으로 운영하기 위해서 Container기술이 필수적임. <br>
각 Serivce들은 개별적인 Docker Container에서 운영됨. <br>
<br>
> **Containerizaion 사용 이유**
> 1. Container이미지를 활용하여 신속하게 배포가 가능함. <br>
> 2. 가상머신(VM)보다 가벼워 리소스를 절약할 수 있음. <br>
> 3. 한 Service가 다운되더라도 다른 Service에 영향을 주지 않음. <br>
> 4. 트래픽 증가시 Container를 추가하여 확장할 수 있음. <br>
---

#### 5. Service Registry
<img width="2330" alt="image" src="https://github.com/user-attachments/assets/f14ca36e-fc00-43a4-ac5c-382ee2164a26" />

Microservice는 Container에서 실행되므로, Container가 재시작되거나 새로운 인스턴스가 추가되면 IP와 Port가 동적으로 변경될 수 있음. <br>
API Gateway는 Service Registry에 요청을 보내 각 Service의 최신 위치 정보(IP, Port)를 조회한 후, 요청을 적절한 Service로 전달함. <br>
이를 통해 동적으로 변경되는 Service의 위치를 자동으로 반영할 수 있음. <br>
<br>
> **Service Registry의 동작 순서**
> 1. Service가 실행되면 자신의 위치정보(IP, Port)를 Service Registry에 등록함. <br>
> 2. API Gateway는 Service Registry에서 최신 Service의 위치를 조회하여 요청을 전달함. <br>
> 3. Service가 종료되거나 대체되면 Service Registry는 해당 정보를 제거하거나 업데이트함. <br>
---

#### 6. Message Queue
<img width="2325" alt="image" src="https://github.com/user-attachments/assets/fc9e127f-614a-4d9a-b8c5-54da871a3545" />

---
#### 7. Build & Deploy
---
#### 8. Cloud Config Server
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/411125d5-46a6-40ea-975e-9c28205cb64b" />

---
#### 9. Monitoring
<img width="2257" alt="image" src="https://github.com/user-attachments/assets/f2e63ac6-4e05-4df1-abbc-57a83c4fa271" />

---
#### 10. Ochestration
MSA에서는 여러개의 Container Service가 존재하므로, 이를 수동으로 관리하기 어려움. <br>
Ochestration 도구를 활용하면, Container의 배포와 확장, 장애 복구를 자동화 할 수 있음. <br>

---
#### 11. Docker Registry
Docker Registry는 Container Image를 저장하고 관리하는 중앙 저장소. <br>
MSA에서는 Service들이 Container로 실행되기 때문에, 각 Service의 Image 관리가 중요해 Docker Registry로 Container이미지를 관리하고 공유함. <br>

---
#### 12. Documentation
MSA에서는 설계가 복잡하고, 잦은 배포를 하기 때문에 배포 및 운영 절차, API, Architecture를 문서화하여 공유해, 원할한 협업을 도움. <br>

---
#### 13. RDBMS
관계형 데이터베이스로 데이터를 테이블 형식으로 구조화하여 저장함. <br>
SQL을 사용해 데이터를 관리함. <br>

---
#### 14. NoSQL
비관계형 데이터베이스로 대량의 데이터를 빠르게 저장하고 처리할 수 있도록 설계된 데이터베이스. <br>
정해진 스키마가 없으며, 데이터 구조가 유연하여 확장이 용이함. <br>

---
#### 15. Cache
캐시 저장소로 데이터를 캐싱해 데이터베이스에 반복적으로 접근하는 부담을 줄임. <br>
빠른 응답속도를 제공함. <br>

---

<br><br>
## 🚀 모놀리식에서 MSA로 전환 전략

#### 1. 빅뱅 전환 vs 점진적인 전환
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/f57c4440-cd47-4a41-b211-f614dada28c1" />

<br>

#### 1-1. 빅뱅 전환
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/7bd9a4c2-8662-416b-9865-5d0b1c9c243d" />

#### 1-2. 점진적 전환
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/1b916bb6-866f-46b0-b9f2-97021c47d88b" />

> 리스크 관리 측면에서 많은 기업들은 **점진적인 전환**을 선택
<br>

---

#### 2. 설계 절차
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/d898bac1-19ae-4f5f-a8cb-24ccb7b2fe44" />

> - **적합성 검토**: 시스템이 MSA로 전환이 필요한지 판단
> - **도입 목표 수립**: 도입 목표를 수립하고 달성 기준을 정의
> - **서비스 분할**: 서비스 분할 방식 결정
> - **설계**: 기술 스택 선정
<br>

---

#### 2-1. 적합성 검토
> 시스템이 적합한지 판단하는 단계
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/1348aae1-1559-47b7-bd6c-0ad825061c62" />
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/3a56936a-46c7-4ca4-8163-c5a32e799512" />

<br>

---

### 2-2. 도입 목표 수립
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/fe75ea10-74fe-4ec5-a815-128c27489abc" />
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/e202e312-3de9-48b7-b120-63677c442104" />

> 달성 기준을 구체적이고 수치를 나타내어 작성하여 성공 여부 확인 가능하도록 해야 함
<br>

---


### 2-3. 서비스 분할
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/343c3947-b52d-403a-8b3d-203f2c409e6f" />


<img width="2041" alt="image" src="https://github.com/user-attachments/assets/2e9e24f0-d017-4661-b8ac-d9ee13c0a8d2" />

> - 온라인 쇼핑몰 시스템을 도메인에 따라 서비스 분리 <br>
> - 각 서비스들은 각자 담당한 로직만을 수행, 다른 서비스와 최소한의 통신, 인접 서비스에 미치는 영향이 최소이거나 없도록 서비스의 경계를 구분하여 분할 <br>
<br>
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/7f64654e-b66d-4da9-a8db-d04bd7210848" />

<br>

---


### 2-4. 설계
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/5f49460b-5ee5-4849-a459-f28bdea32ba9" />
<br>

---


### 2-5. 전환 전략 정리
<img width="2041" alt="image" src="https://github.com/user-attachments/assets/939591fc-0e21-43d5-8232-334ff32ec3b2" />

> MSA 전환의 필요성과 가치를 평가한 후, 전환을 결정했다면 명확한 도입 목표를 설정하는 것이 중요 <br>
> 이후, 적절한 서비스 분할 전략을 선정하여 분할 단위를 도출하고, 이를 기반으로 목표에 맞는 시스템 설계를 진행

<br>

---

<br><br>
## 📆 Q&A

#### 개인정보 보호와 관련된 처리를 위해 MSA가 필요한 이유는 무엇인가요?
> 각국의 개인정보 보호 규제(GDPR, CCPA 등)가 상이하여, MSA를 도입하면 국가별 요구사항에 맞춰 특정 서비스만 분리하여 적용할 수 있습니다. 이를 통해 규제 준수를 유연하게 관리하고, 개인정보 보호 강화를 효과적으로 실현할 수 있습니다.

#### 로드 밸런서로 트래픽 분산이 이루어지는 과정 속에서 로드 밸런서 자체에 문제가 생긴다면 장애 극복을 어떻게 할지 궁금합니다.
> 로드 밸런서는 기본적으로 2개 이상의 로드 밸런서로 구성해, 하나는 Active, 나머지는 Standby상태로 둡니다. <br>
> Active 로드 밸런서가 장애가 발생한다면 Standby 로드 밸런서가 자동으로 활성해 장애를 극복합니다.

#### 그림에 CI와 CD 에 공통된 부분이 존재하는데 설명에서는 공통된 부분이 있다고 느껴지지 않아, 다시 설명해 주시면 감사하겠습니다.
>

#### DDD를 설명해주셨는데 효율적인 DDD를 위한 방식이 있을까요?
>

#### msa는 시스템간, 모듈간 결합도가 낮아, CI/CD 방식 중 롤링으로 배포해도 될 것 같은데 카나리로 언급하신 이유가 있으신가요?
>

#### MSA 전환 방법에 대해서 말씀해주셨는데, 안정적인 서비스를 위해서 데이터베이스는 어떻게 분리해야하는지 궁금합니다.
>

#### 실무에서는 Blue/Green 과 카나리아 중 어떤 것으로 배포를 많이 하나요? 그리고 그 이유가 궁금합니다.
>

#### MSA로 점진적으로 변환을 할 때 변환할 서비스 단위는 어떤식으로 운영이 되는지 궁금합니다
>



