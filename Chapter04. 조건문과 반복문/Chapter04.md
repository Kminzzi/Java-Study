# Chapter04. 조건문과 반복문
###   :memo: 작성 날짜 : 2022-12-14 ~
###  :tada: 작성자 : KMinzzi   
<br/>


## 1. 조건문 - if, switch

- 제어문(control statement) : 프로그램의 흐름을 바꾸는 역할을 하는 문장들로 조건문과 반복문이 있다.
- 조건문 : 조건에 따라 다른 문장이 수행한다.
- 반복문 : 특정 문장들을 반복해서 수행한다.

<br/>

### 1.1 if문
#### 만일 (if) 조건식이 참(true)이면 괄호 {}안의 문장들을 수행하라.
```
if(조건식) {
		// 조건식이 참이 ㄹ때 수행될 문장
}
```

```
if(score > 60) {
	System.out.println("합격입니다.");
}
```

</br>

### 1.2 if-else문
#### else는 그 밖의 다른으로 해석하면 된다. 즉, 조건식의 결과가 참이 아닐 때, else블럭의 문장을 수행하라는 뜻이다.

```
if(조건식) {
	// 조건식이 참(0이 아닌 값)일 때 수행될 문장
} else {
	// 조건식이 거짓(0)일 때 수행될 문장들
}
```
```
if(input==0) {
	System.out.println("0입니다.");
} else {
	System.out.println("0이 아닙니다.");
}
```
</br>

###  1.3 if-else if문
 #### 경우의 수가 셋 이상인 경우에 사용한다.
```
if (조건식1) {
	// 조건식1이 참일 때 수행될 문장
} else if (조건식2) {
	// 조건식2가 참일 때 수행될 문장
} else if (조건식3) {
	// 조건식 3이 참일 때 수행될 문장
} else {
	// 위의 어느 조건식도 만족하지 않을 때 수행될 문장
}
```
```
if (socre>=90) {
	grade = 'A';
} else if (80<=score && score < 90) {
	grade = 'B';
} else if (70 <=score && score < 80) {
	grade = 'C';
} else {
	grade = 'D';
}
```
</br>

### 1.4 중첩 if문
```
if (조건식1) {
	if (조건식2) {
		// 조건식1과 조건식2가 모두 true일 때 수행될 문장들
	} else {
		// 조건식 1이 true이고, 조건식2가 false일 때 수행되는 문장들
	}
} else {
	// 조건식1이 false일 때 수행되는 문장들 
}
```
</br>

### 1.5 switch 문
#### 하나의 조건식으로 많은 경우의 수를 처리할 수 있다.
```
switch(조건식) {
	case 값1 :
		// 조건식의 결과가 값1과 같을 경우 수행
		break;
	case 값2 :
		// 조건식의 결과가 값2와 같을 경우 수행
		break;
	default :
		//일치하는 case문이 없을 때 수행
}
```
switch문에서 break문은 각 case문의 영역을 구분하는 역할을 하는데, 만일 break문을 생략하면 case문 사이의 구분이 없어지므로 다른 break문을 만나거나 블럭 끝을 만날 때까지 나오는 모든 문장을 수행한다. 때문에 break를 잊지 말도록 주의해야 한다.

```
switch (level) {
	case 3:
		grantDelete();
	case 2:
		grantWrite();
	case 1:
		grantRead();
}
```
다음 코드는 고의적으로 break문을 생략하는 경우이다.

</br>

## 2.2 반복문 - for, while, do-while

### 2.1 반복문

- 반복문 : 어떤 작업이 반복적으로 수행되도록 할 때 사용
- for문, while문, do-while문이 있다.
</br>

### 2.1 for문
```
for (초기화;조건식;증감식) {
	// 조건식이 참일 때 수행
}
```

```
for(int i=1; i<=10; i++) { }
```
세가지 요소는 필요하지 않으면 생략할 수 있으며, 모두 생략도 가능하다.
```
for(;;) { }
```
조건식이 생략된 경우, 참으로 간주되어 무한 반복문이 되며, if문을 넣어서 특정 조건을 만족하면 for문을 나오게 해야 한다.
 
#### 향상된 for문
```
for  (타입 변수명 : 배열 또는 컬렉션) {
	// 반복할 문장
}
```
타입은 배열 또는 컬렉션의 요소의 타입이어야 한다. 배열 또는 컬렉션에 저장된 값이 매 반복마다 하나씩 순서대로 읽혀서 변수에 저장된다. 그리고 반복문의 괄호 {}내에서는 이 변수를 사용해서 코드를 작성한다.

```
class FlowEx22 {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};
        int sum = 0;
        for (int i = 0; i < arr.length; i++) {
            System.out.printf("%d", arr[i]);
        }
        System.out.println();
        
        for(int tmp : arr) {
            System.out.printf("%d", tmp);
            sum += tmp;
        }
        System.out.println();
        System.out.println("sum="+sum);
    }
}
```
```
10 20 30 40 50
10 20 30 40 50
sum=150
```
 
 </br>
 
### 2.2 while문

조건식이 참인 동안 블럭 내의 문장을 반복한다.

```
while(조건식) {
	// 조건식의 연산결과가 참인 동안 수행
}
```
</br>

### 2.3 do-while문
기본적인 구조는 while문과 같으나 조건식과 블럭 {}의 순서를 바꿔놓은 것이다. while문과 반대로 블럭{}을 먼저 수행한 후에 조건식을 평가한다.
```
do {
	//조건식의 연산결과가 참일 때 수행
} while (조건식);
```
```
import java.util.*;

class FlowEx28 {
    public static void main(String[] args) {
        int input = 0;
        int answer = 0;
        
        answer = (int)(Math.random()*100) + 1;
        Scanner scanner = new Scanner(System.in);
        
        do {
            System.out.print("1과 100 사이의 정수를 입력하세요. > ");

            String tmp = scanner.nextLine();
            input = Integer.parseInt(tmp);

            if (input > answer) {
                System.out.println("더 작은 수로 다시 시도해보세요. ");
            } else if (input < answer) {
                System.out.println("더 큰 수로 다시 시도해보세요. ");
            }
        } while(input != answer);
        
        System.out.println("정답입니다.");
    }
}
```

</br>

### 2.4 break문
break문은 자신이 포함된 가장 가까운 반복문을 벗어난다.

</br>

### 2.5 continue문
반복문 내에서만 사용될 수 있으며, 반복이 진행되는 도중에 continue문을 만나면 반복문의 끝으로 이동하여 다음 반복으로 넘어간다.

continue문은 반복문 전체를 벗어나지 않고 다음 반복을 계속 수행한다는 점에서 break문과 다르다.
```
import java.util.*;

class FlowEx32 {
    public static void main(String[] args) {
        int menu = 0;
        int num = 0;
        
        Scanner scanner = new Scanner(System.in);
        
        while(true) {
            System.out.println("(1) square");
            System.out.println("(2) square root");
            System.out.println("(4) log");
            System.out.println("원하는 메뉴(1~3)를 선택하세요. (종료:0) >");
            
            String tmp = scanner.nextLine();
            menu = Integer.parseInt(tmp);
            
            if(menu == 0) {
                System.out.println("프로그램을 종료합니다. ");
                break;
            } else if (!(1 <= menu && menu <=3)) {
                System.out.println("메뉴를 잘못 선택하셨습니다. (종료는 0)");
                continue;
            }
            
            System.out.println("선택하신 메뉴는 " + menu + "번입니다.");
        }
    }
}
```

</br>

### 2.6 이름이 붙은 반복문
여러 개의 반복문이 중첩된 경우에는 break문으로 중첩 반복문을 완전히 벗어나


<br/>
