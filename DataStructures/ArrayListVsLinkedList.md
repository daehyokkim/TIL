# 자료구조

> **메모리를 효율적으로 사용하기 위한 필수구조**
>
> ****

저장공간(memory)과 연산(CRUD)으로 구성된 구조를 의미한다.

지원되는 연산에 따라 다양한 자료구조가 존재!!

- 대상 : 메모리!! ~~중요해~~

### 학습에 앞서 알아두면 좋은 정보

- CPU : 생각,계산,연산을 담당

- 메모리 :

  - 가격이비쌈,휘발성,스토리지보다 훨씬 속도가빠름
  - Rendom Access memory (**RAM**) 
    - 메모리에 저장된 **데이터 주소를 접근하는 시간이 동일하단 특성**

- 스토리지 : HDD,SSD등과같은 저장장치를 의미함

  - 가격저렴,용량이큼,비휘발성

- cpu가 바로 스토리지에게 데이터를 가져온다면 처리속도가 월등히 차이가 나서 처리시간이 지연된다.~~CPU가 고구마100개는 먹은 답답함..?~~

  이를 해경하기 위해 스토리지에 저장된 데이터는 메모리에게 전해지고 cpu는 메모리에 있는 데이터를 처리함 ~~편안ㅎㅎㅎ~~

![img](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/1335/2917.png)

## Array List vs Linked List

### 1. Array List

- List의 사이즈가 동적인 배열
- Array List는 object element만 담을 수 있음을 명심하자!!
- 제네릭 타입을 사용할 수 있음 (참고자료) [제네릭 타입이란?](https://github.com/daehyokkim/multicampus/blob/main/java/collection_scrum_0412.md)
- **메모리 사용방식**
  - 같은 엘리먼트(데이터)들이 메모리상에 **연속적으로 존재** 하는 특성을 가진
- 장점
  - 인덱스를 이용해 값을 가져오는게 효율적이다. :rabbit2::rabbit2:
    - 이유
      - 원하는 데이터의 인덱스만 알면 바로 접근하기가 쉽기 때문이다.
- 단점
  - 데이를 추가,삭제 시 시간이 많이 소요된다. :turtle::turtle:
    - 이유
      - 데이터를 추가 및 삭제시 뒤에있는 데이터의 인덱스가 이동하기 때문에 추가,삭제시 시간이 오래 걸린다.
  - **삽입,삭제가 빈번한 프로세스일 경우 좋지않음**

- ArrayList의 삽입,삭제 과정

  ![img](https://media.vlpt.us/images/adam2/post/448cdf66-1186-469d-bcb8-868c8897c49f/image.png)![img](https://media.vlpt.us/images/adam2/post/fff2cfde-fc6b-4423-bbe3-2e1109c09968/image.png)

- 참고자료

  - [ArrayList 강의](https://opentutorials.org/module/1335/8709)

  

### 2.Linked List

- 노드 간에 link를 통해 리스트로 구현한 객체

- 다음 노드의 위치 정보만 가지고있어 **(즉, 인덱스를 가지고 있지 않음...)** 데이터를 탐색시 **순차접근**만 가능한 것을 명심하자!!
- 메모리 사용방식
  - 각가의 엘리먼트(데이터)들이 따로 흩어져 메모리에 존재하지만 각각 **연결(link)**되어 존재한다.

- 기본 구조
  - HEAD : 첫번째 링크가 무엇인지 저장하는 공간(C언어에선 포인트(주소)라고도 함!!)
  - 한개의 노드는 Data filed와 Link Filed로 구성되어 있다
    - Data filed : 정보를 저장
    - Link Filed : 다음 노드 주소를 저장

![img](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/1335/2939.png)

- 장점
  - 데이터의 삽입,삭제에 효율적
  - 리스트 내에 자료이동이 필요하자 않음
  - 사용 후 기억 자오의 재사용이 가능
- 단점
  - 포인터 사용으로 인해 공간 낭비가 생길 수 있음
  - 구현이 복잡하다
  - 특정 자료의 탐색 시간이 길다..

- LinkedList 삽입,삭제 과정

  - head  : 가장 처음 노드를 가리키는 포인트

  - java언어에선 .next()라는 메서드를 통해 다음 노드에 접근이 가능함

    ~~추가적으로~~ C언어에선 구조체안에 다음 노드의 address(주소)를 저장하는 포인터 변수를 생성하여 다음 노드를 접근한다.

![img](https://media.vlpt.us/images/adam2/post/fe15b837-a8c7-4be2-ac26-bf7aabaa9873/image.png)

![img](https://media.vlpt.us/images/adam2/post/39e70de3-ff85-4076-b598-c7997d4b6406/image.png)

- 참고자료

  [LinkedList 강의](https://opentutorials.org/module/1335/8821)



#### 이미지 한줄평

![img](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/1335/2885.png)



~~참고자료의 강의 내용이 정말 좋으니 여러번 학습해보자~~

