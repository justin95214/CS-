**CS 질문 정리**

1. [ 디자인 패턴 ]

> 프로그램을 설계하는데 발생했던 문제점들을 객체 간의 상호 관계 등을 이용하여 해결 할 수 있도록 하나의 ‘규약’형태로 만들어 놓은 것

싱글톤 패턴 :  하나의 클래스에 오직 하나의 인스턴스만 가지는 패턴

Ex) 보통 데이터 베이스 연결 모듈에 많이 사용

장점 : 인스턴스를 다른 모듈들이 공유하며 사용하기 때문에 인스턴스를 생성할 때 드는 비용이 줄어듬

단점 : 의존성이 높음

- 단위 테스트를 할 때, 테스트가 서로 독립적이어야 하는데 어떤 순서로든지 할 수 있는데, 싱글톤 패턴은 미리 생성된 하나의 인스턴스를 기반으로 구현하는 패턴이므로 테스트마다 독립적인 인스턴스를 만들기 힘듬
- 단점 해결 방안 : 의존성 주입 (Dependency Injection)을 통해 모듈간 의 결합을 느슨하게 가능
- 메인 모듈을 직접 하위 모듈에 대한 의존성을 주는 것이 아닌 의존 주입자(Dependency Injector)를 통해 간접으로 의존성 주입
    - 장점 : 모듈을 쉽게 교체 할 수 있는 구조가 됨
    - 단점 : 클래스 증가로 복잡성이 증가할 수 있음
    - 원칙 : 상위 모듈은 하위 모듈에 대해서 어떠한 것도 가져오면 안됨
    - 또한 추상화에 의존해야됨

팩토리 패턴 : 객체를 사용하는 코드에서 추상화 패턴이자 상속 관계에 있는 두 클래스에서 상위 클래스는 뼈대를 결정하고, 하위 클래스에서 객체 생성에 대한 구체적인 내용을 결정짓는 패턴

전략 패턴(정책 패턴) : 객쳉의 행위를 바꾸고 싶은 경우 직접 수정하는 것이 아닌 ‘전략’ 이라고 부는 캡슐화된 알고리즘을 컨텍스트 안에서 바꿔주며 상호 교체가 가능하게 된 패턴

Ex) 결제 방식만 바꿔서 하는 것

옵저버 패턴 :

프록시 패턴과 프록시 서버 :

프록시 패턴 : 대상 객체에 접근하기 전에, 접근에 대한 흐름을 가로체 대상 객체 앞단의 인터페이스 역할을 하는  디자인 패턴

- 객체의 속성, 변환 등을 보완하며 보안, 데이터 검증, 캐싱, 로깅에 사용함

프록시 서버 : 서버와 클라이언트 사이에 클라이언트가 자신을 통해 다른 네트워크 서비스에 간접적으로 접솔 할 수있게 해주는 컴퓨터 시스템이나 응용프로그램

이터레이터 패턴 :이터레이터(iterator)를 사용하여 컬렌션 요소들에게 접근하는 디자인 패턴

- 순회할 수 있는 여러 가지 자료형 구조와 상관없이 이터레이터라는 하나의 인터페이스로 순회 가능

노출 모듈 패턴 : private, public 같이 접근 제어자를 만드는 패턴

MVC 패턴 : 모델, 뷰, 컨트롤러로 이루어진 디자인패턴

애플리케이션의 구성요소를 세 가지 역할로 구분하여 개발 프로세스에서 각각의 구성 요소에만 집중해서 개발 할 수 있습니다. 재사용성과 확장성이 용이하다는 장점

MVP 패턴 : MVC패턴으로 부터 파생되어 Controller가 Presenter로 교체된 패턴

**[ OOP란 ]**

OOP는 현실 세계를 프로그래밍으로 옮겨와 현실 세계의 사물들을 객체로 보고, 그 객체로부터 개발하고자 하는 특징과 기능을 뽑아와 프로그래밍하는 기법

설계원친(SOLID원칙)

단일 책임 원칙 - 모든 클래스는 각각 하나의 책임만 가져야하는 원칙

A라는 로직이 존재한다면 어떠한 클래스는 A에 관한 클래스여야 하고 이를 수정한다고 했을 때도 A와 관련된 수정이어야함

개발-폐쇄 원칙 (OCP Open Closed Principle) -  유지 보수 사항이 생긴다면 코드를 쉽게 확장 할 수 있도록 하고 수정할 떄는 닫혀 있어야하는 원칙 - 기존 코드는 잘변경하지 않으면서도 확장은 쉽게 할 수 있어야 함

리스코프 치환 원칙 - 프로그램의 객체는 프로그램의 정확성ㅇ르 깨뜨리지 앟으면서 하위 타입의 인스턴스로 바꿀 수 있어야하는 것

- 부모 객체에 자식 개체를 넣어도 시스템이 문제없이 돌아가게 만드는 것

인터페이스 분리 법칙 - ISP(Interface Segregation Principle) 하나의 일반적인 인터페이스보다 구체적인 여러개의 인터페이스를 만들어야하는 원칙

의존 역전 원칙 - 자신보다 변하기 쉬운 것에 대한 의존 하던 것을 추상화된 ㅇ인터페이스나 상위 클래스를 두어 변하기 쉬운 것의 변화에 영향받지 않게 하는 원칙

1. [ 데이터베이스 ]

데이터베이스 - 일정한 규칙 혹은 규약을 통해 구조화되어 저장하는 데이터 모음

DMBS -  데이터 베이스를 제어, 관리하느 통합 시스템

DataBase Management’

엔터티 : 사람, 장소, 물건, 사건, 개념 등 여러 개의 속성을 지닌 명사를 의미

약한 엔터티 & 강한 엔터디 : A가 혼자서는 존재하지 못하고, B의 존재여부에 따라 종속적

A - 약한 엔터티 / B - 강한 엔터티

릴레이션 :

- 데이터베이스에서 정보를 구분하여 저장하는 기본 단위, 엔터티에 관한 데이터를 데이터베이스에서는 릴레이션 하나에 담아서 관리
- 엔터티가 데이터베이스에서 관리될때, 릴레이션으로 변화되며
- 관계형 데이터 베이스에서는 테이블
- NoSQL 데이터 베이스에서는 컬렉션

속성 - 릴레이션에서 관리하는 구체적이며 고유한 이름을 갖는 정보

도메인 -

**[ 트랜잭션(Transaction)이란? ]**

**트랜잭션이란 데이터베이스 작업의 단위로써 하나 이상의 쿼리를 처리할 때 동일한 Connection 객체를 공유하여 에러가 발생한 경우 모든 과정을 되돌리기 위한 방법입니다.**

**[ 트랜잭션의 ACID란? ]**

- 
- 원자성(Atomicity): 트랜잭션에 포함된 작업은 전부 수행되거나 전부 수행되지 않아야 한다.
- 일관성(Consistency): 트랜잭션을 수행하기 전이나 후나 데이터베이스는 항상 일관된 상태를 유지해야 한다.
- 고립성(Isolation): 수행 중인 트랜잭션에 다른 트랜잭션이 끼어들어 변경중인 데이터 값을 훼손하지 않아야한다.
- 지속성(Durability): 수행을 성공적으로 완료한 트랜잭션은 변경한 데이터를 영구히 저장해야 한다.



**[커넥션 풀을 사용하는 이유와 장점 그리고 주의점 ]**

**커넥션은 TCP/IP 연결에 의한 3-way handshaking이 발생하여 연결에 오랜 시간이 걸립니다. 하지만 이를 초기에 한 번 생성해두고 관리하면 재사용 할 수 있고, 애플리케이션 초기에 커넥션들을 모아둔 곳이 바로 커넥션 풀입니다.**

**멀티쓰레드 환경에서는 각각의 쓰레드가 커넥션 풀을 점유해서 사용합니다. 커넥션 풀에 커넥션이 부족한 상황에서 커넥션을 요청하게 되면 커넥션 풀이 반환될 때 까지 기다려야 하므로 커넥션 풀이 바닥나지 않도록 주의해야 합니다.**

**[ RDBMS와 NoSQL 차이 ]**

- 
- RDBMS
    - 
    - 2차원의 행과 열로 데이터의 관계를 관리하는 데이터베이스
    - 장점: 스키마에 맞추어 데이터를 관리하기 때문에 데이터의 정합성을 보장할 수 있다.
    - 단점: 시스템이 커질 수록 쿼리가 복잡해지고 성능이 저하되며, 수평적 확장이 어렵다.
- 
- 
- NoSQL
    - 
    - RDBMS가 비대해짐에 따라 관계가 복잡해져, 이를 극복하기 위해 등장하게 된 데이터베이스
        - 장점: NOSQL은 스키마 없이 Key-Value 형태로 데이터를 관리하여 좀 더 자유롭게 데이터를 관리할 수 있다.
        - 단점: 중복된 데이터가 추가 가능하여, 이에 대한 관리가 필요하다.

[운영체제] >> CPU 스케줄링과 프로세스 관리/ 메모리 관리 / 디스크 파일 관리/I/O 디바이스 관리

CPU : Central Processing Unit -  산술논리연산 장치, 레지스터, 제어장치로 구성

CU : 제어장치 Control Unit : 프로세스 조작을 지시하는 CPU 부품

레지스터 : CPU안에 있는 매우 빠른 임시 기억 장치

시스템콜 : 운영체제가 커널에 접근하기 위한 인터페이스, 유저 프로그램이 운영체제의 서비스를 받기 위해 커널 함수를 호출할 때 씀

커널 :  운영체제의 핵심부로 컴퓨터 자원들을 관리하는 것

프로세스 : 컴퓨터에서 실행되고 있는 프로그램 / CPU 스케줄링의 대상이 되는 작업 Task /

스레드 : 프로세스 내 작업의 흐름

- 프로그램이 메모리에 올라가면 프로세스가 되는 인스턴스화가 일어남
- 이후에는 CPU스케줄러에 따라 CPU가 프로세스를 실행함

프로세스와 컴파일 과정

프로세스는 프로그램으로부터 인스턴스화 된 것을 말함

컴파일링 : 프로그램이 컴퓨터가 이해할 수 있는 기계어로 번역되어 실행될 수 있는 파일이 되는 것

목적 코드가 라이브러리를 통해 링커로 실행 가능한 파일이 생성됨

프로그램 내에 있는 라이브러리 함수 도는 다른 파일들과 목적 코드를 결합하여 실행 파일을 만듬

동적 라이브러리 : 프로그램 실행 시 필요할 때만 DLL이라는 함수 정보를 통해 참조하는 방식

정적 라이브러리 : 프로그램 빌드 시 라이브러리가 제공하는 모든 코드를 실행 파일에 넣는 방식

시스템 환경 등 외부 의존도가 낮고 코드 중복 등 메모리 효율성이 떨어짐

IPC = Inter Process Communication

프로세스끼리 데이터를 주고받고 공유 데이터를 관리하는 메커니즘을 뜻함

=>클라이언트와 서버 : 클라이언트는 데이터를 요청하고 서버는 클아이언트 요청에 응답하는 것

IPC의 종류로는 공유 메모리, 파일, 소켓, 익명 파이프, 명명 파이프, 메세지 큐가 있음

이들은 모두 메모리가 완전히 공유되는 스레드 보다는 속도가 떨어짐

**[ Byte Ordering이란 ]**

**Byte Ordering이란 데이터가 저장되는 순서를 의미합니다. Byte Ordering의 방식에는 빅엔디안(Big Endian)과 리틀엔디안(Little Endian)이 있습니다.**

- 
- Big Endian
    - 
    - MSB가 가장 낮은 주소에 위치하는 저장 방식
    - 네트워크에서 데이터를 전송할 때 주로 사용됨
    - 가장 낮은 주소에 MSB가 저장되므로, offset=0인 Byte를 보면 양수/음수를 바로 파악할 수 있다.
- 
- 
- Little Endian
    - 
    - MSB가 가장 높은 주소에 위치하는 방식
    - 마이크로프로세서에서 주로 사용된다.
    - 가장 낮은 주소에 부호값이 아닌 데이터가 먼저 오기 때문에, 바로 연산을 할 수 있다.


CPU 스케줄링

- 비선점형 스케줄링

>FCFS  = First Come First Served

가장 먼저 온것을 가장 먼저 처리하는 알고리즘

Convoy effect 현상이 발생하는 단점이 있음

Convoy effect = 길게 수행되는 프로세스 때문에, 준비 큐에서 오래 기다리는 현상

- 다른 프로세스들이 하나의 긴 포포세스가 CPU를 놓기를 기다리는 것
- 낮은 CPU와 장치 사용률을 보이게 된다

SJF = Shortest Job First

- 실행하기 전 next CPU burst 길이를 예측하기 어렵다
- 선점형 스케줄링

현대 컴퓨터가 쓰는 스케줄링인 우선 순위 스케줄링의 일종

프로세스를 알고리즘에 의해 중단시켜 버리고 강제로 다른 프로세스에 CPU 소유권을 할당하는 방법

라운드 로빈 (RR Round Robin)

- 각 프로세스는 동일한 할당 시간을 주고 그 시간 안에 끝나지 않으면 다시 준비 큐의 뒤로 가는 알고리즘
- 컨텍스트 스위칭이 잦아져서 오버헤드, 비용이 커짐
- 일반적으로 전체 작업시간이 길어지지만 평균 응답시간은 짧아진다

**(4) 시간 할당량(Time Quantum)과 문맥 교환 시간(Context Switch Time)**

- 시간 할당량은 Context Switch time보다 커야 한다.
    - 그렇지 않으면 문맥 교환 오버헤드로 인해 성능이 크게 저하된다.

우선 순위 스케줄링

- CPU는 가장 높은 우선 순위로 가진 프로세스에 할당된다
- 우선 순위가 같은 프로세스는 FCFS 순서로 스케줄링 된다
- SFJ은 일반적인 우선 순위 스케줄링 알고리즘의 특별한 경우이다

다단계 큐

우선 순위에 따른 준비 큐를 여러개 사용하고, 큐마다 라운드 로빈인 FCFS같은 스케줄링 알고리즘을 각각 적용한 것

딥러닝 : 머신러닝 중에 인공 신경망 모델을 활용한 기법으로 인간의 뇌를 착안하여 개발된 학습 기법으로 End-to-End 학습이라고 많이 표현합니다

머신러닝 : 규칙을 프로그래밍하지 않아도 통계 모델을 기반으로 데이터의 패턴을 분석하여 예측하거나 분류하는 기법

머신러닝과 딥러닝 차이 ?: 딥러닝은 머신 러닝의 하위 개념으로, 사람의 개입없이 뉴럴 네트워크 개념으로 학습 시킬 수 있는 것은 딥러닝이고,

통계적 패턴을 분석하는 방식은 머신러닝이다.

머신러닝 모델

- SVM : 구별하고자 하는 클래스의 마진을 최대화 시키는 모델. N차원을 N -1차원으로 나눌 수있는 초평면을 찾는 모델
- XGBoost : 여러 개의 의사결정트리를 조합해서 사용하는 앙상블 기법 중 하나. Boosting을 기반으로 하는 머신러닝 방법
- 로지스틱 회귀 :
- 선형 회귀 : 독립변수와 종속 변수 간의 관계를 예측할 때, 선형 관계를 통해 연속된 독립 변수를 통해 목표 변수를 예측하며 사용되는 지도 학습 기반 모델
- 의사결정트리 : 주어진 입력값을 의사결정규칙에 따라 출력값을 예측하는 트리형태의 모델
- 랜덤포레스트 트리 : 의사결정트리의 단점을 보완시킨 모델로, 깊이가 깊어질수록 오버피딩되는 문제점을 해결할 수 있음.
    - **Bagging**은 **B**ootstraping + **Agg**regat**ing**을 합친 말입니다
    - **부트스트랩(Bootstraping)**은 데이터를 셈플링 하는 방법
    - 부트스트렙을 통해서 만들어놓은 여러가지 나무들을 합치는 과정**(Aggregating)**
    - 
- KNN : 거리가까운 데이터로 유사성을 계산하여 분류하는 지도학습기반 모델
- K-Mean : 비지도학습 기반 기법으로 비슷한 데이터들끼리 군집화되어 군집의 중심을 계속 업데이트 시키는 모델

**랜덤 포레스트(Random Forest)와 그래디언 부스팅(Gradient Boosting)의 차이점은 무엇인가?**

랜덤 포레스트와 그래디언 부스팅은 모두 앙상블 기법을 사용하는 머신러닝 알고리즘이다.

랜덤 포레스트는 여러 개의 의사결정 트리를 만드록, 각 트리의 예측 결과를 집계하여 최종 결과를 얻는다.

이 트리들은 독립적으로 생성되며, 부스트트랩 샘플링과 특성 무작위를 선택을 사용하여 다양성을 부여한다.

그래디언트 부스팅은 순차적으로 개선된 여러 의사결정 트리를 만들어 학습한다.

각 트리는 이전 트리의 오차를 줄이는 방향으로 학습되며, 경사하강법을 사용하여 손실 함수를 최소화한다.

그래디언트 부스팅은 일반적으로 더 나은 성능을 제공하지만, 랜덤 포레스트보다 학습 시간이 오래 걸린다.

군집화는 비지도학습 기법으로, 데이터를 유사한 그룹으로 분류하는 과정이다. 주요 군집화 알고리즘은 다음과 같다.

- K-평균(K-means) 군집화 : K-means는 주어진 데이터를 K개의 클러스터로 묶는 알고리즘이다.
- 초기 중심점을 무작위로 선택한 후, 각 데이터 포인트를 가장 가까운 중심점에 할당하고, 중심점을 그룹 내 데이터 포인트들의 평균으로 업데이트한다.
- 이 과정을 중심점이 수렴할 때까지 반복을 한다. K-means는 속도가 빠르고 구현이 쉽지만, K값을 미리 정해야 하고 초기 중심점 선택에 민감하다.
- 계층적 군집화 : 계층적 군집화는 데이터 포인트를 계층 구조의 클러스터로 구성한다. 점진적으로 병합하거나 분할하는 방법에 따라 두 가지 유형으로 나뉜다.
- 병합 계층 군집화는 모든 데이터 포인트를 개별 클러스터로 시작하여 가장 유사한 클러스터를 병합하는 과정을 반복한다.
- 분할 계층 군집화는 전체 데이터 세트를 하나의 클러스터로 시작하여 클러스터를 재귀적으로 분할하는 방식이다.
- DBSCAN(Density-Based Spatial Clustering of Applications with Noise) : DBSCAN은 밀도 기반 군집화 알고리즘으로, 데이터 포인트의 밀도를 기반으로 클러스터를 형성하며, 동시에 노이즈 포인트를 구분한다.
- 이 알고리즘은 특정 밀도를 가진 영역에서 포인트를 찾아 클러스터를 확장하고, 밀도가 낮은 영역을 노이즈로 처리한다.
- DBSCAN은 클러스터의 개수를 미리 지정할 필요가 없으며, 임의의 모양의 클러스터를 찾을 수 있다.

**정규화(regularization)란 무엇이며, 왜 필요한다?**

정규화는 머신러닝 모델의 복잡성을 줄이고 과적합을 방지하기 위한 기법이다.

이는 모델의 가중치에 일정한 제약을 부과하여, 가중치가 너무 커지지 않도록 한다.

정규화를 사용하면 모델이 훈련 데이터에 너무 적합하지 않아 일반화 능력이 향상된다.

대표적인 정규화 방법으로는 L1 규제와 L2 규제가 있다.

**과적합(overfiting)과 과소적합(underfition)의 차이점은 무엇인가?**

과적합은 모델이 훈련 데이터에 지나치게 적합하여, 새로운 데이터에 대한 일반화 성능이 저하되는 현상입니다.

이는 모델이 훈련 데이터의 노이즈까지 학습하여 발생합니다. 반면 과소적합은 모델이 훈련 데이터를 충분히 학습하지 못해, 훈련 데이터와 새로운 데이터 모두에 대한 성능이 저하되는 현상이다.

이는 모델의 복잡성이 너무 낮거나 학습이 제대로 이루어지지 않을 때 발생한다.

**정확도(accuracy), 정밀도(precision), 재현율(reclaa)의 차이점은 무엇인가?**

- 정확도(accuracy)는 전체 예측 중 올바른 예측의 비율 (TP+TN)/(TP+TN+FP+FN)
- 정밀도(precision)는 양성으로 예측한 것 중 실제로 양성인 비율 TP/(TP+FP)
- 재현율(recall)은 실제 양성 중 양성으로 예측한 비율 TP/(TP+FN)

**ROC 곡선과 AUC의 개념을 설명하시오.**

ROC(Receiver Operating Characteristic) 곡선은 이진 분류 문제에서 모델으 성능을 평가하는 데 사용되는 그래프이다.

ROC 곡선은 False Positive Rate(FPR)을 x 축으로, True Positive Rate(TPR, 재현율)을 y축으로 놓고, 다양한 분류 임계에 대해 그린 곡선이다. 이 곡선은 모델의 성능이 얼마나 민감한지를 보여준다.

-AUC(Area Under the Curve)는 ROC 곡선 아래의 면적을 나타내며, 모델의 성능을 하나의 숫자로 표현하는 데 사용된다. AUC 값이 1에 가까울수록 모델의 성능이 좋다고 평가할 수 있으며, 0.5는 무작위 예측과 동일한 성능을 의미한다.

**하이퍼파라미터 최적화 방법들에 대해 설명하시오.**

하이퍼파라미터 최적화는 머신러닝 모델의 성능을 향상시키기 위해 모델의 하이퍼파라미터를 조정하는 과정이다. 주요 하이퍼파라미터 최적화 방법에는 다음과 같은 것들이 있다.

- 그리드 탐색(Grid Search) : 가능한 모든 하이퍼파라미터 조합을 탐색하여 최적의 조합을 찾는 방법이다. 계산 비용이 높을 수 있지만, 완전한 탐색을 수행한다.
- 랜덤 탐색(Random Search) : 하이퍼파라미터 공간에서 무작위로 조합을 선택하여 찾는 방법이다. 계산 비용이 낮고, 일정 시간 내에 근사적인 해를 찾을 수 있다.
- 베이지안 최적화(Bayesian Optimization) : 과거의 하이퍼파라미터 조합에 대한 결과를 활용하여 새로운 조합을 선택하는 확률 모델을 구축하는 방법이다. 보다 효율적인 탐색을 수행할 수 있다.

**그리드 탐색(Grid Search)과 랜덤 탐색(Random Search)의 차이점은 무엇인가?**

그리드 탐색은 하이퍼파라미터 공간을 균일하게 탐색하여 최적의 하이퍼파라미터 조합을 찾는 방법이다. 이 방법은 모든 가능한 조합을 시도하므로 계산 비용이 높을 수 있지만, 완전한 탐색을 수행한다. 그리드 탐색은 하이퍼파라미터의 가능한 값들을 미리 정의하고, 이들의 조합을 시스템적으로 탐색하며, 교차 검증을 사용하여 모델의 성능을 평가한다.

반면 랜덤 탐색은 하이퍼파라미터 공간에서 무작위로 조합을 선택하여 최적의 조합을 탖는 방법이다. 계산 비용이 낮고, 일정 시간 내에 근사적인 해를 찾을 수 있다. 랜덤 탐색은 하이퍼파라미터의 값들을 무작위로 샘플링하며, 그리드 탐색보다 더 넓은 하이퍼파라미터 공간을 탐색할 수 있다. 또한, 일부 하이퍼파라미터의 영향이 크지 않을 때, 랜덤 탐색이 효율적ㅇ니 해를 더 빠르게 찾을 수 있다.

**Precision(정밀도)**

**정밀도**란 모델이 True라고 분류한 것 중에서 실제 True인 것의 비율입니다. 즉, 아래와 같은 식으로 표현할 수 있습니다.

**Positive 정답률**, **PPV(Positive Predictive Value)**라고도 불립니다. 날씨 예측 모델이 맑다로 예측했는데, 실제 날씨가 맑았는지를 살펴보는 지표라고 할 수 있겠습니다.

**1.2  Recall(재현율)**

**재현율이란 실제 True인 것 중에서 모델이 True라고 예측한 것의 비율입니다.**
