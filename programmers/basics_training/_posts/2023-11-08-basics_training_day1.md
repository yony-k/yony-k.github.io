---
title: "Day 1 출력"
tag: basics_training
---

### 문자열 출력하기

![문자열 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/c6554fda-7498-477c-8ce8-a3802d129140)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        
        System.out.println(a);
    }
}
```

---

### a와 b 출력하기 

![a와 b 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/a37b0f17-65ef-4a2b-a806-735a24fc4173)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        
        System.out.printf("a = %d\nb = %d", a,b);
    }
}
```
---

### 문자열 반복해서 출력하기

![문자열 반복해서 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/b88f7e6b-ee3e-4984-81ef-9da866102a6b)


```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.next();
        int n = sc.nextInt();
        
        for(int i=0;i<n;i++) {
            System.out.print(str);
        }
    }
}
```
- for문을 사용하여 주어진 값인 n번만큼 출력되도록 작성했다.
- print를 사용한 이유는 문자열이 줄바꿈 없이 붙어서 출력되었기 때문이다.

---

### 대소문자 바꿔서 출력하기

![대소문자 바꿔서 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/e6a25d94-ec9b-4a16-870e-061ecc34a84d)


```java
//Character 메소드 사용

import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String a = sc.next();
        
        String s = "";
        
        for(int i=0;i<a.length();i++) {
        	char ch = a.charAt(i);
        	if(Character.isUpperCase(ch)) {
        		s += Character.toLowerCase(ch);
        	} else if(Character.isLowerCase(ch)){
        		s += Character.toUpperCase(ch);
        	} else {
        		System.out.println("대소문자만 입력 가능합니다.");
        		break;
        	}
        }
        
        System.out.println(s);
    }
}
```
```java
//대소문자의 아스키 코드값 활용

Scanner sc = new Scanner(System.in);
System.out.print("문자 입력: ");
String msg = sc.next();
String newmsg = "";

for(int i=0;i<msg.length();i++) {
    int ch = Character.codePointAt(msg, i);
    if(ch>=65&&ch<=90) {
        newmsg += (char)(ch+32);
    } else if(ch>=97&&ch<=122) {
        newmsg += (char)(ch-32);
    } else {
        System.out.println("입력 값 오류");
        break;
    }
    
    if(i==msg.length()-1) System.out.println(newmsg);
}
```

- 받아온 문자열을 하나하나 분리하여 대소문자 구분을 해주었다.
- Wrapper class 중에 하나인 Character 클래스에 대소문자 판별 메소드와 대문자, 소문자 변환 메소드가 있다.
- 메소드 검색 할 때 String 에도 대문자, 소문자 변환 메소드가 있어 헷갈렸다.

<br>

- **Character.isUpperCase()** : char 타입 문자가 대문자인지 판별해주는 메소드, boolean 리턴
- **Character.isLowerCase()** : char 타입 문자가 소문자인지 판별해주는 메소드, boolean 리턴
- **Character.toUpperCase()** : char 타입 문자를 대문자로 바꾸어주는 메소드, char 리턴
- **Character.toLowerCase()** : char 타입 문자를 소문자로 바꾸어주는 메소드, char 리턴


---

### 특수문자 출력하기

![특수문자 출력하기](https://github.com/yony-k/yony-k.github.io/assets/109204976/8bf0a57e-fd31-4158-af48-4ab6ae259a5f)


```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        
        System.out.println("!@#$%^&*(\\'\"<>?:;");
    }
}
```
- 자바에는 특별한 용도로 사용되는 기호가 있다. ex) "(큰따옴표),\\(역슬래시)
- 이런 문자를 그냥 출력하려면 본래의 용도대로 사용되어버려 오류가 난다.
- 이런 문자들 앞에는 \\(역슬래시)를 하나 더 붙여주면 된다.