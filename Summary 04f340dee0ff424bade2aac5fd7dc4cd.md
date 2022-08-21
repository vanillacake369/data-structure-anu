# Summary

# 1장 : 자료구조 개요

---

## 문제 해결 과정

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled.png)

## 문자열 표현

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%201.png)

## 순서도

- if 문의 형식과 제어흐름
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F933bf7de-e27a-467f-91f8-cb89a0b71e11%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F933bf7de-e27a-467f-91f8-cb89a0b71e11%2Fimage.png)
    
- 다단계 조건문중첩 if문의 형식과 제어 흐름
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2Fec7a7456-f1f3-4c7f-a30f-d12ded5da3ca%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2Fec7a7456-f1f3-4c7f-a30f-d12ded5da3ca%2Fimage.png)
    
- 중첩 if문의 사용 예) 평균 점수에 따른 등급 계산하기
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F671e86a5-6a52-4a3a-a089-16737e644607%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F671e86a5-6a52-4a3a-a089-16737e644607%2Fimage.png)
    
- case 문여러 조건식 중에서 해당 조건을 찾아서 그에 대한 명령문을 수행
    - 중첩 if문으로 표현 가능
    - 형식과 제어흐름
        
        ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F8f8623d9-d35a-4cd3-8fd1-5263cb3d2132%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F8f8623d9-d35a-4cd3-8fd1-5263cb3d2132%2Fimage.png)
        
- case 문 예) 평균 점수에 따른 등급 계산하기
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2Ff68038ef-ea17-4f86-a99e-d150430fd746%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2Ff68038ef-ea17-4f86-a99e-d150430fd746%2Fimage.png)
    

### 반복문

- 일정한 명령을 반복 수행하는 루프(loop) 형태의 제어구조
- for 문형식과 제어흐름
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F1758d99a-b63d-492e-80fa-dc2bc142068a%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F1758d99a-b63d-492e-80fa-dc2bc142068a%2Fimage.png)
    
- while-do 문형식과 제어흐름
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F38304517-70a2-4526-875e-4015713622b5%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F38304517-70a2-4526-875e-4015713622b5%2Fimage.png)
    
- do-while문형식과 제어흐름
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F6cc6ab34-0f97-4744-bd9e-c057aaea883b%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2F6cc6ab34-0f97-4744-bd9e-c057aaea883b%2Fimage.png)
    

### 함수문

- 처리작업 별로 모듈화하여 만든 부 프로그램
- 형식과 예
    
    ![https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2Fbf0bb186-0ec8-4bae-866b-6ef8752d8a78%2Fimage.png](https://velog.velcdn.com/images%2Fsanizzang00%2Fpost%2Fbf0bb186-0ec8-4bae-866b-6ef8752d8a78%2Fimage.png)
    

---

# 2장 : 재귀호출

---

## 팩토리얼

```cpp
long int fact(int n){
		if(n <= 1)
				return (1);
		else
				return (n*fact(n-1));
}
```

## 하노이탑

```cpp
#include <stdio.h>
void hanoi(int n, int start, int work, int target);
int main()
{
    hanoi(3, 'A', 'B', 'C');
    getchar();
}
void hanoi(int n, int start, int work, int target)
{
		// base
    if (n == 1)
    {
        printf("%c에서 %d를(을) %c로 옮김\n", start, n, target);
    }
    else
    {
        //맨 위부터 맨 아래 원판 전까지의 원판(1~n-1)을 start->target->work
        hanoi(n - 1, start, target, work);
        //맨 아래 원판인 n을 옮김
        printf("%c에서 원반 %d를(을) %c로 옮김\n", start, n, target);
        // work에 있는 맨 위부터 맨 아래 원판 전까지의 원판(1~n-1)을 work -> start -> target
        hanoi(n - 1, work, start, target);
    }
}
```

---

# 3장 : 순차자료구조

## 순차자료구조  VS 연결자료구조

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%202.png)

## row major VS column major VS page major

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%203.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%204.png)

## Polynomial :: addPoly()

### Pseudo-Code

```cpp
addPoly(A,B){
	C <- zeroP();
	while(not isZeroP(A) and not isZeroP(B)){
		case{
			maxExp(A) < maxExp(B):
				C <- addTerm(C,coef(B,maxExp(B)),maxExp(B));
				B <- delTerm(B,maxExp(B));
			maxExp(A) == maxExp(B):
				sum <- coef(A,maxExp(A)) + coef(B,maxExp(B));
				if(sum != 0)
					C <- addTerm(C,sum,maxExp(A));
				A <- delTerm(A,maxExp(A));
				B <- delTerm(B,maxExp(B));
			maxExp(A) > maxExp(B):			
				C <- addTerm(C,coef(A,maxExp(A)),maxExp(A));
				A <- delTerm(A,maxExp(A));
		}
	}
	
	if(not isZeroP(A)) A 나머지항 C에 복사
	else if(not isZeroP(B)) B 나머지항 C에 복사
	
	return C;
}
```

### C

```cpp
#include <stdio.h>
#define MAX_DEGREE 50
#define MAX(a,b) ((a>b)?a:b)

typedef struct{
	int degree;
	float coef[MAX_DEGREE];
}polynomial;

polynomial addPoly(polynomial A,polynomial B){
	//make result poly
	polynomial C;
	C.degree = MAX(A.degree,B.degree);
	//while A,B is not empty, compare maxExp of A,B
	int A_index,B_index,C_index=0;
	int A_degree=A.degree;
	int B_degree=B.degree;
	int C_degree=C.degree;
	while(A_degree>=A_index && B_degree>=B_index){
		if(A_degree > B_degree){
			C.coef[C_index++] = A.coef[A_index++];
			A_degree--;
		}
		else if(A_degree == B_degree){
			C.coef[C_index++] = A.coef[A_index++] + B.coef[B_index++];
			A_degree--;
			B_degree--;
		}
		else{
			C.coef[C_index++] = B.coef[B_index++];
			B-degree--;
		}
	}
	//if one of them is null, add all of filled poly to reult poly
	if(A_degree>=A_index){
		while(A_degree>=A_index){
			C.coef[C_index++] = A.coef[A_index++];
			A_degree--;
		}
	}else if(B_degree>=B_index){
		while(B_degree>=B_index){
			C.coef[C_index++] = B.coef[B_index++];
			B-degree--;
		}
	}
	//return result poly
	return C;
}
```

## Sparse Matrix Transpose

```cpp
#include <stdio.h>

typedef struct{
	int row;
	int col;
	int value;
}term;

void smTranspose(term a[],term b[]){
	int r,c,v,p;
	r = a[0].row;
	c = a[0].col;
	v = a[0].value;
	b[0].col = r;
	b[0].row = c;
	b[0].value = v;
	
	p=1;
	if(v>0){
		for(int i=0;i<c;i++){
			for(int j=1;j<=v;j++){
				if(a[j].col == i){
					b[p].row = a[j].col;
					b[p].col = a[j].row;
					b[p].value = a[j].value;
					p++;
				}//end if
			}//end for(j)
		}//end for(i)
	}//end if(v)
}
```

---

# 4장 : 연결자료구조

### insertFirst

```cpp
void insertFirst(List* h,data x){
	// create new node
	Node* new = createNode();
	new->data = x;
	// insert first
	new->link = h;
	h = new;
}
```

### insertMiddle

```cpp
void insertMiddle(List* h,Node* pre,data x){
	// create new node
	Node* new = createNode();
	new->data = x;
	// if empty, insert first, make new point null
	if(h == null){
		h = new;
		new->link = null;
	}
	else{
		new->link = pre->link;
		pre->link = new;
	}
}
```

### insertLast

```cpp
void insertLast(List* h,data x){
	// create new node
	Node* new = createNode();
	new->data = x;
	// if empty, make new node point null, insert first
	// if filled, track down to last, insert last
	if(h == null){
		new->link = h;
		return;
	}else{
		Node* temp = h;
		while(temp->link != null){
			temp = temp->link;
		}
		temp->link = new;
	}
}
```

### deleteNode

```cpp
void deletNode(List* h,Node* pre){
	// if empty, error
	/* if filled, 
		 check pre->link is last node and then, 
		 point pre to pre.link.link, 
		 remove pre */
	if(h == null) error;
	else{
		Node* old = pre;
		if(old == null) then return;
		pre->link = old->link;
		free(pre);
	}
}
```

### searchNode

```cpp
Node* searchNode(List* h,data x){
	if(h == null)
		return;
	else{
		Node* temp = h;
		while(temp->link != null){
			if(temp->data == x)
				break;
			else
				temp = temp->link;
		}
		return temp;
	}
}
```

## 원형 연결리스트

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%205.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%206.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%207.png)

## 이중연결리스트

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%208.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%209.png)

## 다항식

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2010.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2011.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2012.png)

# 5장 : 스택

---

LIFO Last-In-First-Out 후입선출 구조

마지막에 삽입(Last-In)한 원소는 맨 위에 쌓여 있다가 가장 먼저 삭제(First-Out)됨

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2013.png)

## ADT

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2014.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2015.png)

## push(S,x) ALG

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2016.png)

## pop(S) ALG

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2017.png)

## 단순 연결리스트를 이용한 스택 구현

순차 자료구조인 1차원 배열을 이용하여 구현
스택의 크기 : 배열의 크기
스택에 저장된 원소의 순서 : 배열 원소의 인덱스
인덱스 0번 : 스택의 첫번째 원소
인덱스 n-1번 : 스택의 n번째 원소
변수 top : 스택에 저장된 마지막 원소에 대한 인덱스 저장
공백 상태 : top = -1 (초기값)
포화 상태 : top = n-1

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2018.png)

### 과정

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2019.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2020.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2021.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2022.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2023.png)

### 20~26행 : 연결 스택에서 삽입 연산을 수행하는 과정

22행 : 원소 item을 저장할 노드에 대한 메모리 할당, 포인터 temp 설정
23행 : 삽입할 노드의 데이터 필드에 원소 item을 저장
24행 : 삽입할 노드의 링크 필드에 포인터 top의 값 저장하면, 새로 삽입한 노드가 현재 스택의 마지막 노드(현재 top이 가리키는 노드)로 연결
25행 : 포인터 temp의 값(삽입 노드의 주소)을 포인터 top에 설정, 새로 삽입한 노드가 스택의 top 노드가 되도록 조정

### 28~43행 : 연결 스택에서 삭제하는 연산을 수행하는 과정

31행 : 포인터 temp를 top 노드에 설정하여 삭제할 노드를 가리킴
38행 : 스택의 마지막 노드의 데이터 필드값을 변수 item에 저장
39행 : 포인터 top의 위치를 현재 마지막 노드의 아래 노드로 이동
40행 : 포인터 temp가 가리키는 노드를 메모리 해제
41행 : 변수 item의 값, 즉 스택의 top이었던 노드의 데이터를 반환

### 60~63행 : 연결 스택에 노드가 있는 동안, top 노드부터 링크 필드를 따라
아래 노드로 이동하면서 데이터 필드값을 출력.

top 노드부터 출력하므로
출력 화면에서 왼쪽이 스택의 마지막 원소인 top이 됨

## 역순 문자열 만들기

① 문자열을 순서대로 스택에 삽입

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2024.png)

② 스택에서 삭제하여 문자열을 만들기

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2025.png)

## 시스템 스택

프로그램에서의 호출과 복귀에 따른 수행 순서를 관리

- 가장 마지막에 호출된 함수가 가장 먼저 실행을 완료하고 복귀하는 후입선출 구조이므로, 후입선출 구조의 스택을 이용하여 수행순서 관리
- 함수 호출이 발생하면 호출한 함수 수행에 필요한 지역변수, 매개변수 및 수행 후 복귀할 주소 등의 정보를 스택 프레임(stack frame)에 저장하여 시스템 스택에 삽입
- 함수의 실행이 끝나면 시스템 스택의 top 원소(스택 프레임)를 삭제(pop)하면서 프레임에 저장되어있던 복귀주소를 확인하고 복귀
- 함수 호출과 복귀에 따라 이 과정을 반복하여 전체 프로그램 수행이 종료되면 시스템 스택은 공백스택이 됨

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2026.png)

①main( )함수 실행 시작 : 시작하면 main( )함수가 호출되어 실행, main( ) 함수 시작과 관련된 정보를 스택 프레임에 저장, 시스템 스택에 삽입

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2027.png)

② F_1( ) 함수 호출 : main() 함수 실행 중 F_1() 함수 호출을 만나면 함수 호출과 복귀에 필요한 정보를 스택 프레임에 저장, 시스템 스택에 삽입, 호출된 함수인 F_1() 함수로 이동. 이때 스택 프레임에는 호출된 함수의 수행이 끝나고 main() 함수로 복귀할 주소 a를 저장

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2028.png)

③ 호출된 함수 F_1() 함수 실행
④ F_2( ) 함수 호출 : F_1() 함수 실행 중에 F_2() 함수 호출을 만나면 다시 함수 호출과 복귀에 필요한 정보를 스택 프레임에 저장하여 시스템 스택에 삽입하고, 호출된 함수인 F_2() 함수를 실행. 스택 프레임에는 F_1() 함수로 복귀할 주소 b를 저장

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2029.png)

⑤ 호출된 함수 F_2() 함수 실행
⑥ F_2( ) 함수 실행 종료, F_1( ) 함수로 복귀 : F_2( ) 함수 실행이 끝나면 F_2( ) 함수를 호출했던 이전 위치로 복귀하여 이전 함수 F_1( )의 작업을 계속해야 함. 시스템 스택의 top에 있는 스택 프레임을 pop하여 정보를 확인하고 복귀 및 작업 전환 실행함

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2030.png)

⑦ F_1( ) 함수로 복귀하여 F_1( ) 함수의 나머지 부분 실행
⑧ F_1( ) 함수 실행 종료, main( ) 함수로 복귀 : 스택의 top에 있는 스택 프레임을 pop하여 정보를 확인하고 복귀 및 작업 전환을 실행

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2031.png)

⑨ main( ) 함수 실행 완료(전체 프로그램 실행 완료) : 정상적인 함수 호출과 복귀가 모두 완료되었으므로 시스템 스택은 공백이 됨

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2032.png)

---

## 수식 괄호 쌍 검사

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2033.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2034.png)

---

## 수식 표기법

- 전위표기법(prefix notation)
연산자를 피연산자를 앞에 표기하는 방법
예) +AB
- 중위표기법(infix notation)
연산자를 피연산자의 가운데 표기하는 방법
예) A+B
- 후위표기법(postfix notation)
연산자를 피연산자 뒤에 표기하는 방법
예) AB+

### 후위표기법

변환

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2035.png)

연산

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2036.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2037.png)

---

# 6장 : 큐(Queue)

- 스택과 비슷한 삽입과 삭제의 위치가 제한되어있는 유한 순서 리스트
- 큐는 뒤에서는 삽입만 하고, 앞에서는 삭제만 할 수 있는 구조
- 삽입한 순서대로 원소가 나열되어 가장 먼저 삽입(First-In)한 원소는
맨 앞에 있다가 가장 먼저 삭제(First-Out)됨
☞ 선입선출 구조 (FIFO, First-In-First-Out)

## 스택과 큐의 연산 비교

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2038.png)

## 추상자료형

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2039.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2040.png)

## 순차큐

1차원 배열을 이용한 큐

- 큐의 크기 = 배열의 크기
- 변수 front : 저장된 첫 번째 원소의 인덱스 저장
변수 rear : 저장된 마지막 원소의 인덱스 저장

상태 표현

- 초기 상태 : front = rear = -1
- 공백 상태 : front = rear
- 포화 상태 : rear = n-1  (n : 배열의 크기, n-1 : 배열의 마지막 인덱스

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2041.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2042.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2043.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2044.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2045.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2046.png)

## 순차 큐의 잘못된 포화상태 인식

---

큐에서 삽입과 삭제를 반복하면서 그림(a)와 같은 상태일 경우, 앞부분에 빈자리가 있지만 rear=n-1 상태이므로 포화상태로 인식하고 더 이상의 삽입을 수행하지 않는다.

## 순차 큐의 잘못된 포화상태 인식의 해결 방법-1

---

저장된 원소들을 배열의 앞부분으로 이동시키기
순차자료에서의 이동 작업은 연산이 복잡하여 효율성이 떨어짐

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2047.png)

## 순차 큐의 잘못된 포화상태 인식의 해결 방법-2

---

1차원 배열을 사용하면서 논리적으로 배열의 처음과 끝이 연결되어 있다고 가정하고 사용 ⇒ 원형 큐
원형 큐의 논리적 구조

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2048.png)

## 원형 큐

---

### 원형 큐의 구조

---

- 초기 공백 상태 : front = rear = 0
- front와 rear의 위치가 배열의 마지막 인덱스 n-1에서 논리적인 다음 자리인 인덱스 0번으로 이동하기 위해서 나머지연산자 mod를 사용
3  ÷  4 = 0 …3  (몫=0, 나머지=3)
3 mod 4 = 3

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2049.png)

사용조건) 공백 상태와 포화 상태 구분을 쉽게 하기 위해서 front가 있는 자리는 사용하지 않고 항상 빈자리로 둠

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2050.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2051.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2052.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2053.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2054.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2055.png)

## 연결 큐

---

단순 연결 리스트를 이용한 큐

- 큐의 원소 : 단순 연결 리스트의 노드
- 큐의 원소의 순서 : 노드의 링크 포인터로 연결
- 변수 front : 첫 번째 노드를 가리키는 포인터 변수
- 변수 rear : 마지막 노드를 가리키는 포인터 변수

상태 표현

- 초기 상태와 공백 상태 : front = rear = null

공백 연결 큐 생성 알고리즘
초기화 : front = rear = null

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2056.png)

연결 큐의 공백 상태 검사 알고리즘
공백 상태 : front = rear = null

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2057.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2058.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2059.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2060.png)

## 데크(Deque)

---

큐 두 개 중 하나를 좌우로 뒤집어서 붙인 구조, 큐의 양쪽 끝에서 삽입 연산과 삭제 연산을 수행할 수 있도록 확장한 자료구조

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2061.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2062.png)

## 큐의 응용

---

프린터 버퍼 큐(Printer Buffer Queue)

- CPU에서 프린터로 보낸 데이터 순서대로(선입선출) 프린터에서 출력하기 위해서 선입선출 구조의 큐 사용

스케줄링 큐(Scheduling Queue)

- CPU 사용을 요청한 프로세서들의 순서를 스케줄링 하기 위해서 큐를 사용

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2063.png)

시뮬레이션에서의 큐잉 시스템

- 시뮬레이션을 위한 수학적 모델링에서 대기행렬과 대기시간 등을 모델링 하기 위해서 큐잉 이론(Queue theory) 사용

# 7장 : 트리

---

## 트리란

---

- 원소들 간에 1:n 관계를 가지는 비선형 자료구조
- 원소들 간에 계층관계를 가지는 계층형 자료구조(Hierarchical Data Structure)
- 상위 원소에서 하위 원소로 내려가면서 확장되는 트리(나무)모양의 구조

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2064.png)

## 용어

---

- 노드(node) – 트리의 원소
    - 트리 A의 노드 - A,B,C,D,E,F,G,H,I,J,K,L
- 루트 노드(root node) – 트리의 시작 노드(레벨Level 0)
    - 트리 A의 루트노드 - A
- 간선(edge) – 노드를 연결하는 선. 부모Parent 노드와 자식Child 노드를 연결
- 형제 노드(sibling node) – 같은 부모 노드의 자식 노드들
    - B,C,D는 형제 노드
- 조상 노드(Ancestor) – 간선을 따라 루트 노드까지 경로에 있는 모든 노드들
    - K의 조상 노드 : F, B, A
- 서브 트리(subtree) – 부노 노드와 연결된 간선을 끊었을 때 생성되는 트리
    - 각 노드는 자식 노드의 개수 만큼 서브 트리를 가짐
- 자손 노드 – 서브 트리에 있는 하위 레벨의 노드들
    - B의 자손 노드 – E,F,K,L
- 차수(degree)
    - 노드의 차수 : 노드에 연결된 자식 노드의 수.
        - A의 차수=3, B의 차수=2, C의 차수=1
    - 트리의 차수 : 트리에 있는 노드의 차수 중에서 가장 큰 값
        - 트리 A의 차수=3
    - 단말 노드(리프 노드) : 차수가 0인 노드. 자식 노드가 없는 노드
- 높이
    - 노드의 높이 : 루트에서 노드에 이르는 간선의 수. 노드의 레벨
        - B의 높이=1,  F의 높이=2
    - 트리의 높이 : 트리에 있는 노드의 높이 중에서 가장 큰 값. 최대 레벨
        - 트리 A의 높이=3
- 포리스트forest : 서브트리의 집합
    - 트리 A에서 노드 A를 제거하면, A의 자식 노드 B, C, D에 대한 서브 트리가 생기고, 이들의 집합은 포리스트가 됨

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2065.png)

## 이진트리란

---

- 이진트리(Binary Tree)
- 트리의 모든 노드의 차수를 2 이하로 제한하여 전체 트리의 차수가 2 이하가 되도록 정의
- 이진 트리의 모든 노드는 왼쪽 자식 노드와 오른쪽 자식 노드만 가짐
    - 부모 노드와 자식 노드 수와의 관계  ☞  1:2
    - 공백 노드도 자식 노드로 취급
    - 0 ≤ 노드의 차수 ≤ 2

## 일반 트리를 이진트리로 변환 과정

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2066.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2067.png)

## 이진트리 ADT

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2068.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2069.png)

## 이진트리 특성

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2070.png)

## 이진트리 종류

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2071.png)

### 포화 이진 트리 Full Binary Tree

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2072.png)

### 완전 이진 트리

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2073.png)

### 편향 이진 트리

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2074.png)

## 순차 자료구조를 이용한 구현

---

- 1차원 배열의 순차 자료구조 사용
    - 높이가 h인 포화 이진 트리의 노드번호를 배열의 인덱스로 사용
    - 인덱스 0번 : 실제로 사용하지 않고 비워둠.
    - 인덱스 1번 : 루트 저장

### 완전 이진트리 1차원 배열 표현

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2075.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2076.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2077.png)

### 편향 이진트리 1차원 배열 표현

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2078.png)

## 연결 자료구조를 이용한 구현

---

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2079.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2080.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2081.png)

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2082.png)

## 이진 트리 순회

---

- 모든 원소를 빠트리거나 중복하지 않고 처리하는 연산
- 이진 트리가 순환적으로 정의되어 구성되어있으므로, 순회작업도 서브트리에 대해서 순환적으로 반복하여 완성한다.
- 왼쪽 서브트리에 대한 순회를 오른쪽 서브트리 보다 먼저 수행한다.
- 순회의 종류
    - 전위 순회
    - 중위 순회
    - 후위 순회

### 전위 순회

---

- D → L → R 순서로, 현재 노드를 방문하여 처리하는 작업 D를 가장 먼저 수행

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2083.png)

- 수식 A*B-C/D를 이진 트리로 구성
    - 수식에 대한 이진 트리를 전위 순회하면, 전위 표기식을 구할 수 있음

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2084.png)

### 중위 순회

---

- L → D → R 순서로, 현재 노드를 방문하는 작업 D를 작업 L과 작업 R의 중간에 수행

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2085.png)

- 수식 A*B-C/D를 이진 트리로 구성
    - 수식 이진 트리를 중위 순회하면, 수식에 대한 중위 표기식을 구할 수 있음

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2086.png)

### 후위 순회

---

- L-R-D 순서로 현재 노드를 방문하는 D 작업을 가장 나중에 수행

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2087.png)

- 수식 A*B-C/D를 이진 트리로 구성
    - 수식 이진 트리를 후위 순회하면, 수식에 대한 후위 표기식을 구할 수 있음

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2088.png)

**이진 트리 순회하기 프로그램 : 교재 335p**

- 수식 (A*B-C/D)에 대한 이진 트리를 연결 자료구조 방식으로 표현
- makeRootNode( )함수를 이용해 전위 순회, 중위 순회, 후위 순회를 수행한 경로를 출력하여 확인하는 프로그램

> 또 안 나올거라고 하다가 큰 코 다치지 말고, 한 번이라도 보자. 어디서 어떻게 나올지 모른다… ~~물론 ppt에서 대부분 내겠지만…~~
> 

### 이진 트리 순회의 응용 프로그램

---

- 컴퓨터의 폴더 구조가 이진 트리 구조인 경우 각 폴더를 순회하면서 용량을 계산하면 내 컴퓨터의 전체 용량이 계산 가능함.
    - 폴더 전체 용량은 폴더에 저장된 파일 용량과 하위 폴더의 용량을 합한 값.
    - 상위 폴더 용량을 계산하려면 먼저 하위 폴더 용량을 계산해야 하므로 후위순회를 사용

**이진 트리의 후위 순회를 이용해 폴더 용량 계산 프로그램 : 교재 340p**

## 스레드 이진 트리

---

- 재귀호출 없이 순회할 수 있도록 수정한 이진 트리
    - 재귀호출 방식은 알고리즘이나 함수 구현은 간단하지만, 수행 성능 측면에
    서는 시스템 스택을 사용하면서 호출과 복귀를 관리해야 하고 이진 트리의
    하위 레벨로 내려갈수록 재귀호출 깊이가 깊어지므로 비효율적임.
- 스레드(Thread)
    - 스레드 이진 트리에서 자식 노드가 없는 경우 링크 필드를 널 포인터 대신 순회
    순서상의 다른 노드를 가리키도록 설정. 이런 링크 필드를 스레드라 함

### 스레드 이진 트리노드

---

- 이진 트리 노드 구조에 isThread 필드를 추가하여 정의
- isThread 필드는 링크 필드가 자식 노드에 대한 포인터인지 아니면 자식 노드 대신 스레드가 저장되어 있는지 구별하기 위한 태그 필드

![Untitled](Summary%2004f340dee0ff424bade2aac5fd7dc4cd/Untitled%2089.png)

# Reference

---

[https://velog.io/@sanizzang00/자료구조-알고리즘의-표현-방법](https://velog.io/@sanizzang00/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%EC%9D%98-%ED%91%9C%ED%98%84-%EB%B0%A9%EB%B2%95)