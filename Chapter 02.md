## 2장 - 의미 있는 이름

### 목차
- [들어가면서](#1)
- [의도를 분명히 밝혀라](#2)
- [그릇된 정보를 피하라](#3)
- [의미 있게 구분하라](#4)
- [발음하기 쉬운 이름을 사용하라](#5)
- [검색하기 쉬운 이름을 사용하라](#6)
- [인코딩을 피하라](#7)
- [자신의 기억력을 자랑하지 마라](#8)
- [클래스와 메서드의 이름](#9)
- [기발한 이름은 피하라](#10)
- [한 개념에 한 단어를 사용하라](#11)
- [말장난을 하지 마라](#12)
- [해법 영역에서 가져온 이름을 사용하라](#13)
- [의미 있는 맥락을 추가하라](#14)
- [불필요한 맥락을 없애라](#15)
- [마치면서](#16)

---

<a name="1"></a>
### 들어가면서
- 소프트웨어에서 이름은 어디나 쓰인다.
- 이름을 지을 때 지키면 좋을 간단한 규칙들을 소개한다.

<a name="2"></a>
### 의도를 분명히 밝혀라
- 변수, 함수, 클래스 이름은 존재 이유, 수행 기능, 사용 방법에 대해 답할 수 있어야 한다.
- 따로 주석이 필요하다면 의도를 분명히 드러내지 못했다는 말이다.
```java
// 의도가 드러나지 않는 이름(주석 필요)
int d;	// 경과 시간(단위: 날짜)

// 의도가 드러나는 이름들
int elapsedTimeInDays;
int daysSinceCreation;
int daysSinceModification;
int fileAgeInDays;
```

<a name="3"></a>
### 그릇된 정보를 피하라
- 나름대로 널리 쓰이는 의미가 있는 단어를 다른 의미로 사용하면 안 된다.
	- hp, aix, sco, List 등
- 서로 흡사한 이름을 사용하지 않도록 주의한다.
- 유사한 개념은 유사한 표기법을 사용한다.

<a name="4"></a>
### 의미 있게 구분하라
- 동일한 범위 안의 다른 두 개념을 사용하기 위해 한쪽이름의 철자를 살짝 바꿨다가 컴파일이 불가능한 상황에 빠질 수 있다.
- 연속된 숫자를 붙여 사용하면 저자 의도가 전혀 드러나지 않는다.
- 불용어(noise word)를 추가하는 방식은 아무런 정보도 제공하지 못한다.
	- 변수 이름에 variable, 표 이름에 table, 클래스 이름에 Object 등의 단어는 단연코 금물이다.

<a name="5"></a>
### 발음하기 쉬운 이름을 사용하라
- 말을 처리하려고 발달한 두뇌를 활용하지 않는다면 안타까운 손해다.
```java
// 발음하기 어려운 단어들을 사용한 예시
class DtaRcrd102 {
	private Date genymdhms;
	private Date modymdhms;
	private final String pszqint = "102";
	/* ... */
};

// 발음하기 쉬운 단어로 바꾼 예시
class Customer {
	private Date generationTimestamp;
	private Date modificationTimestamp;
	private final String recordId = "102";
	/* ... */
};
```

<a name="6"></a>
### 검색하기 쉬운 이름을 사용하라
- 문자 하나를 사용하는 이름과 상수는 텍스트 코드에서 쉽게 눈에 띄지 않고, 검색하기 어렵다.
- 간단한 메서드에서 로컬 변수만 한 문자를 사용한다.
- **이름 길이는 범위 크기에 비례해야 한다.**

<a name="7"></a>
### 인코딩을 피하라
- 굳이 부담을 더하지 않아도 이름에 인코딩할 정보는 많다.
- 문제 해결에 집중하는 개발자에게 인코딩은 불필요한 정신적 부담이다.

<a name="8"></a>
### 자신의 기억력을 자랑하지 마라
- 전문가 프로그래머는 **명료함이 최고**라는 사실을 이해하며, 자신의 능력을 좋은 방향으로 사용해 남들이 이해하는 코드를 내놓는다.

<a name="9"></a>
### 클래스와 메서드의 이름
- 클래스, 객체 이름은 Customer, WikiPage, Account, AddressParser와 같은 명사나 명사구가 적합하다.
- 메서드 이름은 postPayment, deletePage, save와 같은 동사나 동사구가 적합하다.
	- 접근자, 변경자, 조건자는 javabean 표준에 따라 값 앞에 각각 get, set, is를 붙인다.
	- 생성자를 중복정의할 때는 정적 팩토리 메서드를 사용하고, 메서드는 인수를 설명하는 이름을 사용한다.
```java
// 좋지 않은 예
Complex fulcrumPoint = Complex.FromRealNumber(23.0);

// 바람직한 예
Complex fulcrumPoint = new Complex(23.0);
```

<a name="10"></a>
### 기발한 이름은 피하라
- 재미난 이름보다 명료한 이름을 선택하라.
- 특정 문화에서만 사용하는 농담은 피하는 편이 좋다.

<a name="11"></a>
### 한 개념에 한 단어를 사용하라
- 추상적인 개념 하나에 단어 하나를 선택해 이를 고수한다.
- 일관성 있는 어휘는 코드를 사용할 프로그래머가 반갑게 여길 선물이다.

<a name="12"></a>
### 말장난을 하지 마라
- 한 단어를 두 가지 목적으로 사용하지 마라.
- 집중적인 탐구가 필요한 코드가 아니라 대충 훑어봐도 이해할 코드 작성이 목표다.

<a name="13"></a>
### 해법 영역에서 가져온 이름을 사용하라
- 코드를 읽을 사람도 프로그래머이므로 전산 용어, 알고리즘 이름, 패턴 이름, 수학 용어 등을 사용해도 괜찮다.
- 기술 개념에는 기술 이름이 가장 적합한 선택이다.
- 적절한 '프로그래머 용어'가 없거나, 문제 영역 개념과 관련이 깊은 코드라면 문제 영역에서 이름을 가져온다.

<a name="14"></a>
### 의미 있는 맥락을 추가하라
- 같은 목적으로 사용하는 변수들을 한 클래스에 넣어 함수를 쪼개면 알고리즘이 좀 더 명확해진다.
<details>
	<summary>맥락이 불분명한 변수</summary>
	
```java
private void printGuessStatistics(char candidate, int count) {
	String number;
	String verb;
	String pluralModifier;
	if (count == 0) {
		number = "no";
		verb = "are";
		pluralModifier = "s";
	} else if (count == 1) {
		number = "1";
		verb = "is";
		pluralModifier = "";
	} else {
		number = Integer.toString(count);
		verb = "are";
		pluralModifier = "s";
	}
	String guessMessage = String.format(
		"There %s %s %s%s", verb, number, candidate, pluralModifier
	);
	print(guessMessage);
}
```
</details>
<details>
	<summary>맥락이 분명한 변수</summary>
	
```java
private void GuessStatisticsMessage{
	private String number;
	private String verb;
	private String pluralModifier;
	
	public String make(char candidate, int count) {
		createPluralDependentMessageParts(count);
		return String.format(
			"There %s %s %s%S",
			verb, number, candidate, pluralModifier);
	}
	
	private void createPluralDependentMessageParts(int count) {
		if (count == 0) {
			thereAreNoLetters();
		} else if (count == 1) {
			thereIsOneLetter();
		} else {
			thereAreManyLetters(count);
		}
	}
	
	private void thereAreManyLetters(int count) {
		number = Integer.toString(count);
		verb = "are";
		pluralModifier = "s";
	}
	
	private void thereIsOneLetter() {
		number = "1";
		verb = "is";
		pluralModifier = "";
	}
	
	private void thereAreNoLetters(int count) {
		number = "no";
		verb = "are";
		pluralModifier = "s";
	}
}
```
</details>

<a name="15"></a>
### 불필요한 맥락을 없애라
- 일반적으로는 짧은 이름이 긴 이름보다 좋다. 단, 의미가 분명한 경우에 한해서다.

<a name="16"></a>
### 마치면서
- 좋은 이름을 선택하려면 **설명 능력이 뛰어나**야 하고 **문화적인 배경이 같아야** 한다.
- 좋은 이름을 선택하는 능력은 기술, 비즈니스, 관리 문제가 아니라 **교육 문제**다.
- 이 장에서 소개한 규칙 몇 개를 적용해 코드를 손본다면 단기적인 효과는 물론 장기적인 이익도 보장한다.
