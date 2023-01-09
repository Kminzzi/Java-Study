
# Chapter05. 배열
###   :memo: 작성 날짜 : 2023-01-09
###  :tada: 작성자 : KMinzzi   
<br/>


## 1. 배열 (array)
### 1.1 배열(array)이란?

- 같은 타입의 여러 변수를 하나의 묶음으로 다루는 것
</br>

### 1.2 배열의 선언과 생성
|선언방법|선언 예|
|:-:|:-:|
타입 [] 변수이름;|int[] score; String[] name;
|타입 변수이름[]; |int score[]; String name[];

#### 배열의 생성

배열의 선언은 생성된 배열을 다루기 위한 참조변수를 위한 공간이 만들어지는 것이고, 배열을 생성해야만 비로소 값을 저장할 수 있는 공간이 만들어진다.
```
타입[] 변수이름;				// 배열을 선언(배열을 다루기 위한 참조변수 선언)
변수이름 = new 타입[길이];	// 배열을 생성(실제 저장공간을 생성)
```

```
int[] score;				// int타입의 배열을 다루기 위한 참조변수 score선언
score = new int[5];			// int타입의 값 5개를 저장할 수 있는 배열
```

```
타입[] 변수이름 = new 타입[길이];	// 배열의 선언과 생성을 동시에.
int[] score = new int[5];		// 길이가 5인 int배열
```

</br>

### 1.3 배열의 길이와 인덱스
  - 배열의 요소(element) : 생성된 배열의 각 저장공간
  - 인덱스(index) : 배열의 요소마다 붙여진 일련번호
  - 인덱스의 범위는 0부터 '배열길이-1'까지
  
  ```
class ArrayEx1{  
	public static void main(String[] args) throws IOException {  
		int score[] = new int[5];  
		int k=1;  
		score[0] = 50;  
		score[1] = 60;  
		score[k+1] = 70;  
		score[3] = 80;  
		score[4] = 90;  
  
	  int tmp = score[k+2] + score[4];  
  
	  for(int i=0; i<5; i++) {  
            System.out.printf("score[%d] : %d%n", i, score[i]);  
	  }  
  
      System.out.printf("tmp:%d%n", tmp);  
	  System.out.printf("score[%d]:%d%n", 7, score[7]);  
	  // index의 범위를 벗어난 값
  }
  ```
```
score[0] : 50
score[1] : 60
score[2] : 70
score[3] : 80
score[4] : 90
tmp:170
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 7 out of bounds for length 5
	at Main.main(Main.java:22)
``` 

#### 배열의 길이

- 배열의 길이 : 배열의 요소의 개수, 즉 값을 저장할 수 있는 공간의 개수

```
int[] arr = new int[0]; 	// 길이가 0인 배열도 생성이 가능하다.
```

* 배열의 길이는 int범위의 양의 정수(0도 포함)이어야 한다.

#### 배열이름.length
```
int[] score = new int[5];

for(int i=0; i<score.length; i++) {
	System.out.println(score[i]);
	}
```
배열의 길이를 직접 입력하는 것보다 '배열이름.length'를 사용하는 것이 좋다. 배열의 길이가 변경될 때마다 조건식도 변경하지 않아도 된다.


#### 배열의 길이 변경하기
1) 더 큰 배열을 새로 생성한다.
2) 기존 배열의 내용을 새로운 배열에 복사한다.

이러한 과정을 통해 배열의 길이를 변경할 수 있다.
하지만 꽤나 비용이 많이 들기 때문에, **처음부터 배열의 길이를 넉넉하게 잡아 새로 배열을 생성해야 하는 상황이 가능한 적게 발생**하도록 해야 한다. 

그렇다고 배열의 길이를 크게 잡으면 메모리를 낭비하게 되므로 기존의 2배 정도의 길이로 생성하는 것이 좋다.

</br>

### 1.4 배열의 초기화
배열은 생성과 동시에 자동적으로 자신의 타입에 해당하는 기본값으로 초기화되므로 따로 초기화를 해주지 않아도 된다.

하지만 원하는 값을 저장하려면 요소마다 값을 지정해야한다.

```
int[] score = new int[5];
score[0] = 50;
score[1] = 60;
score[2] = 70;
score[3] = 80;
score[4] = 90;
```
배열의 크기가 큰 경우에는 for문을 이용한다.
```
int[] score = new int[5]

for(int i=0; i<score.length; i++) {
	score[i] = i*10 + 50;
}
```

다음과 같이 생성과 초기화를 동시에 할 수도 있다.
```
int[] score = new int[] { 50, 60, 70, 80, 90 };
```
이 경우 []안의 배열의 길이는 적지 않는다. {}에 적힌 개수에 의해 배열의 길이가 자동적으로 결정되기 때문이다.

#### 배열의 출력
Arrays.toString(배열이름) 메서드를 사용하면 더 간단하다.
```
int[] iArr = {100, 95, 80, 70, 60};
System.out.println(Arrays.toString(iArr));
```
  


