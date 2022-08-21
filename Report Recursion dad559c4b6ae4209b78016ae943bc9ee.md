# Report : Recursion

> 대부분의 소스코드들은 Loop로 짜여지지만, 우리는 프로그래머로서 논리를 갖춰 이산적으로 접근해야만 한다. 허나, 소스코드들과 달리 대부분의 문제들은 수열의 형태 즉 Recursion의 형태로 해결되는 경우가 많다. 따라서 우리는 Recursion에 대해 면밀히 살펴보아야할 필요성이 있다.
> 

## Types of Recursion

- Tail Recursion
- Head Recursion
- Tree Recursion
- Indirect Recursion
- Nested Recursion

## Tail Recursion

소스코드의 꼬리, 즉 맨 마지막에서 순환호출을 하는 형태.

Calling Time이 아닌 Returning Time에서만 연산되어진다.

(이게 무슨 말이냐하면...)

쉽게 설명하자면 

Calling Time은 말 그대로 호출될 때 연산되어지느냐를 의미하고

Returning Time은 반환되어질 때 연산되어지느냐를 의미한다.

아래와 같은 코드가 있다고 쳐보자.

```c
fun(n)
{
	if(n>0){
		....
		fun(n-1)+n;
	}
}
```

여기서 +n은 call time, 즉 다음 함수를 호출할 때에 연산되어지지 않는다.

되려,  recursive call이 한 꺼풀씩 벗겨지며 반환되어질 때 +n연산을 수행한다.

즉 +n은 즉 fun(n-1)이 반환되어질 때 수행되어지는 것이다. 

Tail Recursion은 또 하나의 장점이 있는데, 그것은 바로 loop의 형태로 변환되기 쉽다는 것이다.

아래의 //1번 코드와 //2번 코드를 비교해보아라.

구조가 닮아있다는 것을 알 수 있을 것이다.

```c
//#1 Loop
void fun(int n){
	while(n>0){
		printf("%d",n);
		n--;
	}
}
//#2 Recursion
void fun(int n){
	if(n>0){
		printf("%d",n);
		fun(n-1);
	}
}
```

Time Complexity

#Loop - O(n)

#Recursion - O(n)

반면 Recursion은 스택구조를 활용하므로

Space Complexity

#Loop - O(1)

#Recursion - O(n)

## Head Recursion

No statements or operation before the recursive call.

```c
void fun(int n){
	if(n>0){
		fun(n-1);
		...
	}
}
```

Head Recursion의 특징::

It means the function doesn’t have to process or perform any operation at the time of calling

It has to do everything only at the time of returning

아래 예시를 들여다보자

```c
void fun(int n){
	if(n>0)
	{
		fun(n-1);
		printf("%d",n);
	}
}
//fun(3) 수행 시,
//console:: 123
```

Printing will be done at returning time so the function doesn’t do anything at the calling time.

반면, Head Recursion은 수행부가 호출부 아래에 있게 되어 있어 Loop형태로 변환하기 복잡하다는 단점이 있다.

```c
//#1 Loop
void fun(int n){
	while(n>0){
		n--;
		printf("%d",n);
	}
}
//#2 Recursion
void fun(int n){
	if(n>0)
	{
		fun(n-1);
		printf("%d",n);
	}
}
```

## Linear Recursion & Tree Recursion

```c
//Linear
fun(n)
{
	if(n>0){
		...
		fun(n-1);
		...
	}
}
//Tree
fun(n)
{
	if(n>0){
		...
		fun(n-1);
		...
		...
		fun(n-1);
		...
	}
}
```

In linear recursion, you can see that the function is calling itself only one time

In Tree recursion, you can see that the function is calling itself more than one time.

Tree Recursion에서는 이전 순환호출이 다 반환되어 수행이 완전히 끝나야 다음 순환호출 수행으로 넘어간다. 

(하나하나 넘겨짚으며 이해하고 싶다면 Section5.55 Tree Recursion 1:50~10:30 참고하여라)

가장 쉬운 예로서 아래와 같이 Recursion in Tree Traversal이 있다.

[https://stackoverflow.com/questions/41335033/recursion-in-tree-traversal](https://stackoverflow.com/questions/41335033/recursion-in-tree-traversal)

```
if(n!=null){
     treeTraversal(n.left);
     System.out.println(n.val);
     treeTraversal(n.right);
 }
```

Let's say I have a tree which is something like:

```
    4
   / \
  2   5
 / \
1   3

```

Your code will first put the recurse through the left children 4 -> 2 -> 1. Since 1 does not have a left child (it is null), it will print 1 and then pop the stack. Next up in the recursion is 2. It will print 2 then traverse the right child of 2 i.e 3. It will print 3, then pop the stack. Then it will print 4, then 4's right child 5. The sequence of prints will be 1, 2, 3, 4, 5. [Here](https://visualgo.net/bst) is a good animation too.

이 강의에서의 쓴 예제는 다음과 같다

![화면 캡처 2022-01-10 191220.png](Report%20Recursion%20dad559c4b6ae4209b78016ae943bc9ee/%ED%99%94%EB%A9%B4_%EC%BA%A1%EC%B2%98_2022-01-10_191220.png)

위 코드를 분석하게 되면 4 layer,4 level이 생성된다.

따라서 n=3의 입력으로서 1+2+4+8=15개의 fun()을 수행한다. 이는 다음 수식을 통해 일반화 할 수 있다.

$$
2^0+2^1+.... 2^n= 2^n-1
$$

따라서 Time Complexity는 O(2^n)이다.

Space Complexity는 트리를 생성해내며 만들어낸 스택구조만큼 차지하게 된다. 이는 하드웨어적으로 스택이 허용하는만큼이지만, 수치적으로는 Tree의 높이만큼 필요하게 된다.

따라서 Space Complexity는 O(n)이다.

## Indirect Recursion 간접순환(?)

A() calls B()

B() calls C()

C() calls A()

```c
//pseudo
void A(){
	if(...){
		..B()
	}
}
void B(){
	if(...){
		..C()
	}
}
void C(){
	if(...){
		..A()
	}
}
```

조건 하에 동작한다는 것에 Note해야한다.

조건에 실패하게 되면 하나의 함수가 무너지고 무너지게 되는 경우 초기 call한 부분으로 반환되어지게 될 것이다.

**Sizing Down**(n/2혹은n- -)과 **조건**(n>value) 에 의해 의존성을 부숴 최상위스택으로부터 하나씩 반환해나가는 구조라고 생각하면 된다.

아래 코드를 살펴보자.

```c
void funA(int n){
	if(n>0){
		printf("%d",n);
		funB(n-1);
	}
}
void funB(int n){
	if(n>1){
		printf("%d",n);
		funA(n/2);
	}
}
```

## Nested Recursion

```c
//psuedo code
int fun(int n){
	if(...){
		...
		fun(fun(n-1));
	}
}
```

fun(n-1)이 순환호출의 parameter로 쓰이는 구조임을 note하여라

즉 함수의 **순환호출부의 파라미터로서 자기 자신이 쓰이는 구조**인데

특이한 점은 fun(n-1)이나 fun(n+1)과 같이 **함수 자기자신에게 up sizing 혹은 down sizing변수를 던진다**는 것이다.

또한 순환호출구조인 fun(fun(n-1))에서 **fun(n-1)의 반환값이 존재하지 않는다면 recursive call은 동작하지 않을 뿐더러 함수 자체에 error가 발생**하게 된다.

정리하자면 다음과 같다.

recursive call의 구현::

```c
fun(fun(n-1))
```

sizing의 구현::

```c
fun(n-1)
```

탈출부 구현::

```c
if(...){...fun(fun(n-1));}
```

실제 코드 예시는 아래와 같다.

```c
int fun(int n){
	if(n>100)
		return n-10;
	else
		return fun(fun(n+11));
}
```

main()에서 fun(95)를 호출하게 된다면

아래와 같이 동작할 것이다.

fun(95) calls fun(fun(95+11))

fun(95+11) returns 95+11-10=96

fun(96) calls fun(fun(96+11))

fun(96+11) returns 96+11-10=97

...

fun(100) calls fun(fun(100+11))

fun(100+11) returns 101

fun(101) returns 91 //여기서 recursive call을 멈추게 된다.

91 goes to starting point where is fun(95)

so fun(95) = 91

## Example #1 : Sum of Natural Numbers

Remember whenever you define any recurrence relation or recursive function, then you must two types of statements

1. What is the **Formula** for the large value
2. What is the **Answer** for the small value

1+2+...+n

sum(n)=1+2+...+(n-1) + n

sum(n)=sum(n-1) + n

sum(n) ::

→ 0 <n=0>

→ sum(n-1) + n <n>0>

```c
#include <stdio.h>

int sum(int num){
	if(num>0){
		return sum(num-1)+num;
	}
	else{
		return 0;
	}
}

int main(){
	int result = sum(100);
	printf("%d",result);
	return 0;
}
```

단순히 내 사족이지만 순환호출 뿐만이 아니라 어떤 문제를 해결하려 할 때이든 Formula와 Answer을 위와 같이 수식으로 접근하는 게 중요한 것 같다 

강의에서는 위 수식으로부터 순환호출을 구현하는 게 더 직관적이다라는 것을 강조한다. loop로 구현하는 것보다 직관적이기도하지만 space complexity에서 효율이 떨어진다라고 설명한다.

개인적으로 효율이 떨어지더라도 수식을 그대로 표현하고 명령하기에는 순환호출만한 게 없다 생각한다.

오류 찾기에도 편하고 표현하고자 하는 것이 무엇인지 인식하기에도 좋지 않은가.

## Example #2 : Factorial

fact(n) = 1*2*3..*(n-1)  * n

fact(n) = fact(n-1) * n

fact(n) ::

→ 1 <n=0>

→ fact(n-1)*n <n>0>

```c
int fact(int n){
	if(n==0)
		return 1;
	else
		return fact(n-1)*n;
}
```

## Example#3 : Power m의n승

m^n

=m*m*m..*m  //multiplied for n times

pow(m,n) = { m*m*m...*m for (n-1) times } * m

pow(m,n) =- pow(m,n-1)*m

pow(m,n)::

→ 1 <m=0>

→ pow(m,n-1)*m  < m>0 >

pow(m,n)을 그냥 구현할 수도 있지만 연산과정을 더욱 짧게 할 수도 있다.

지수가 짝수냐 홀수이냐에 따라 pow(m,n)에 m*m,n/2 혹은 m*m,(n-1)/2을 넘겨주어 m^2을 통해 연산해나가는 것이다.

귀찮지만 그냥 구현하는 버전과 지수를 짝수/홀수로 구분한느 버전 둘 다 아래 코드로 적어놓겠다.

```c
//#og
int pow(int m,int n){
	if(n==0)
		return 1;
	return pow(m,n-1)*m;
}

//#float==even||odd
int pow(int m,int n){
	if(n==0)
		return 1;
	if(n%2==0) //even number
		return pow(m*m,n/2);
	else //odd number
		return m*pow(m*m,(n-1)/2);
}
```

## Example#3 : Taylor Series for e^x

수식 자체가 굉장히 복잡하다.

구글링하여보자

[https://www.youtube.com/watch?v=3d6DsjIBzJ4](https://www.youtube.com/watch?v=3d6DsjIBzJ4)

![https://www.gstatic.com/education/formulas2/397133473/en/taylor_series.svg](https://www.gstatic.com/education/formulas2/397133473/en/taylor_series.svg)

영상을 보면 어떠한 함수를 수식화하기 위해 도함수의 개념을 통해 각 x^n의 계수를 구하는 과정을 taylor series라고 할 수 있는 것 같다. (있는 것 같다라 했다... 그렇다고 안 했다. ㅇㅅㅇ)

도함수의 개념을 통해 접근하게 되면 factorial이 빠질 수 없기 때문에 저러한 식이 나오게 된다. (자세한 건 영상을 다시 보아라. 상당히 재미있다)

자. 그렇다면 위 수식을 어떻게 프로그래밍하느냐?

앞 서 했던 예제들과 같이 예시를 들며 해석해보도록 해보자.

이 수식을 다룬 영상의 제작자 3Blue1Brown은 영상 초기에 다음과 같은 말을 적어놓았는데 인상깊어 적어본다.

> “To many, mathematics is a collection of theorems. For me, mathematics is a collection of examples; a theorem is a statement about a collection of examples and the purpose of proving theorems is to classify and explain the examples...”
> 

— John B. Conway

이를 명심하며 분석해보도록 하자.

e^x를 taylor series의 함수라고 가정한다면 다음과 같이 나열할 수 있다.

e(x,0) =1

e(x,1) = 1 + x/1

e(x,2) = 1 + x/1 + x^2/2

e(x,3) = 1 + x/1 + x^2/2 + x^3/3

e(x,4) = 1 + x/1 + x^2/2 + x^3/3 + x^4/4

...

앞 선 예제들처럼 패턴이 보이지 않는가?

p를 power,f를 factorial이라고 할 때 

e(x,0) =1

e(x,1) = 1 + x/1

=1 + p/f (p=p*x,f=f*1) //p=x^0,f=0!

e(x,2)=1+x/1+x^2/2

=1 + p/f (p=p*x,f=f*1)

...

위 수식을 코드로 옮기면 다음과 같다.

```c
int e(int x,int n){
	static int p=1,f=1;
	int r;
	if(n==0){
		return 1;
	}
	else{
		r=e(x,n-1);
		p=p*x;
		f=f*n;
		return r+p/f;
	}
}
```

슬슬 지겨워지려고 한다.

내가 수식을 배우는 것인지 Recursion에 대한 개념을 배우고 가는 것인지 모르겠다.

일단은 강의를 들어보도록 한다.

(여기서부터 일일이 정리하지 않겠다는 소리이다...ㅎ)