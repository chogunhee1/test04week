# Mermaid 실습
- 순서도 실습
    - 첫번째 샘플
```mermaid
classDiagram
    direction LR
    class Person{
        <<abstract>>
        +name: str
        +phoneNumber: str
        +emailAddress: str
        +purchaseParkingPass()
    }

    class Student{
        +StudentNumber:int
        +averageMark:int
        +isEligibleToEnroll(str) bool
        +getSeminarsTaken() int
    }

    class Professor{
        -/salary:int
        #staffNumber:int
        -yearsOfService:int
        +numberOfClasses:int
    }

    class Address {
        +street: str
        +city: str
        +state: str
        +postalCode: int
        +country: str
        -validate() bool
        +outputAsLabel() str
    }

    Person <|-- Student
    Person <|-- Professor
    Student "0..*"<--"1..5" Professor : supervise
    Person "0..1"-->"1" Address : lives in

```





<hr>
<hr>
<hr>

```mermaid
sequenceDiagram
autonumber
participant U as User
participant C as Client
participant S as Server
participant DB as Database

    U ->> C : Fillusername
    U ->> C : Fill password
    C ->> U : Enable "Login"button
    U ->> C : Click "Loginbutton
    C ->>+ S : POST /login
    S ->>+ DB : SELECT FROM users
    Note over S,DB: See login.py for impl. details
    DB -->>- S : results
    S -->>- C : { authenticated: true }
    C ->> U : redirect /home
```

<hr>

```mermaid
sequenceDiagram
    actor A as 사용자
    participant B as 서버
    
    A ->> B: 서비스 상태 요청
    
    alt 가능
        B -> A: 서비스 가능 상태입니다.
    else 불가능
        B -> A: 현재 서비스 중단 상태입니다.
    else 점검중
        B -> A: 점검중... 기다려 주세요
    end
```

<hr>

```mermaid
sequenceDiagram
    autonumber
    actor A as 사용자
    participant B as 인증 시스템
    A ->>+ B: 아이디/비밀번호 입력
    A ->>+ B: catcha 입력
    B -->>- A: catcha 성공
    B -->>- A: 인증 완료
```

<hr>

```mermaid
flowchart TB %% 좌우 배치일 경우 `LR` 적용
    a([밥을 먹지 않았다])
    b{{String status = hunger <br> String = nothing}}
    c{배가 고픈가?}
    d{먹을 것이 있는가?}
    e[밥을 먹는다]
    f[밥을 먹었다]
    g([End])

    %% 연결선 작업
    a --> b --> c -->|YES| d -->|YES| e --> f --> g
    
    aa[배불러]
    c -->aa-->h
    h[안 먹는다]
    c -->|NO| h
    d --> |NO| h
    i[먹지 않는다]
    h --> i
    i --> g
```

<hr>

```mermaid
flowchart 
    id(((첫번째노드)))
```

```mermaid
flowchart BT
    A[설날 아침] ==>|세뱃돈| B(쇼핑 가기)
    B -.-> C{뭘 사야하나?}
    C ==>|선택1| D[노트북]
    C ==>|선택2| E[스마트폰]
    C ==>|선택3| F[자동차]
```


```Python
print('hello')
```

```Java
System.out.println("hello");
```
## 여기는 수업 끝
