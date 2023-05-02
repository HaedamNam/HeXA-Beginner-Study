# 환경설정과 `markdown`, 그리고 기초 컴퓨터 구조
## 개요
이 스터디에서는 컴퓨터공학과에서 사용할 영역에 대한 전반적이고 기초적인 지식을 다루고 있습니다. 오늘의 스터디를 통해 개발자들이 가장 선호하는 개발환경인 Visual Studio Code에 익숙해지고, `markdown`을 작성해 볼 예정입니다. 더불어, 간단하게 컴퓨터 시스템의 구조를 살펴볼 예정입니다.

## 환경설정
오늘의 활동을 시작하기 전에, 개인 머신에 아래와 같은 환경 설정을 해 오시는 것을 추천드립니다:

> - Visual Studio Code ([link](https://code.visualstudio.com/))
> - Visual Studio Code Extension: Markdown All in One
([link](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one))


오늘 다룰 `markdown`을 포함하여, 모든 프로그래밍 언어는 다양한 종류의 개발환경에서 작성할 수 있습니다. [Vim](https://www.vim.org/)이라던지, Notepad++ 등의 기본 텍스트 에디터에서부터, 
[Visual Studio](https://visualstudio.microsoft.com/ko/)나, [IntelliJ IDEA](https://www.jetbrains.com/ko-kr/idea/)등의 IDE(통합 개발 환경)까지요.   


하지만 여러분의 더 나은 경험과 [Stack Overflow Developer Servey 2022](https://survey.stackoverflow.co/2022/)의 선호도 조사를 참고하여, Visual Studio Code로 이번 세션을 진행하려고 합니다.
> ### 참고: Stack Overflow Developer Servey 2022 IDE 순위
> 1. **Visual Studio Code(74.48%)**
> 2. Visual Studio(32.15%)
> 3. IntelliJ(27.97%)
> 4. Notepad++(27.71%)
> 5. Vim(23.34%)   
> ...

---

## `markdown`
우선, 프로그래밍 언어로 어떤 것을 제작하고 수정하는 것에 익숙해지기 위해, 
[마크업 언어](https://en.wikipedia.org/wiki/Markup_language)인 마크다운을 통해 접근해보는 시간을 가져보도록 하겠습니다.
마크다운은 비록 프로그래밍 언어는 아니지만([튜링 불완전](https://en.wikipedia.org/wiki/Turing_completeness)), 간단한 문법과 가벼운 파일 크기 덕택에 
대부분의 프로젝트에서 README를 작성하는데 사용되고 있습니다. `markdown`에 처음인 사용자도 1시간이면 다 배울 수 있을정도로요!  

(참고: [18F의 README를 작성하는 가이드](https://github.com/18F/open-source-guide/blob/18f-pages/pages/making-readmes-readable.md))

이 문서 역시 간단한 텍스트 에디터와 `markdown` 문법만을 사용하여 작성되었습니다.

### 기본 `markdown 문법`
```markdown
<!--주석-->
# Heading 1
## Heading 2
### Heading 3

**bold**
__also bold__
*italic*
_also italic_
***bold and italic***
___also bold and italic___
~~canceled~~

1. ordered list
2. and so on
  1. with child

- unordered list
- and so on
  - with child

and arrows
&rarr; &larr;
```
는 아래와 같이 표현됩니다:
>
> <!--주석-->
> # Heading 1
> ## Heading 2
> ### Heading 3
>
> **bold**   
> __also bold__   
> *italic*   
> _also italic_   
> ***bold and italic***   
> ___also bold and italic___   
> ~~canceled~~   
>
> 1. ordered list
> 2. and so on
>   1. with child
>
> - unordered list
> - and so on
>   - with child
> 
> and arrows   
> &rarr; &larr;

주의해야 할 점은, 사이트 별 지원하는 세부 마크다운 문법이 다를 수 있으므로 이를 잘 확인하고 사용하는 것이 좋습니다.   
([GitHub 마크다운 가이드](https://docs.github.com/ko/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax))

---
## 기초 컴퓨터 구조
다음으로, 우리가 사용하는 컴퓨터가 어떻게 구성되어 있는지 간단하게 살펴보도록 하겠습니다.

### 스크래치에서 컴퓨터를
 컴퓨터를 구매하실 때, 혹은 컴퓨터의 성능에 대해 논할 때 컴퓨터를 구성하는 많은 부품들이 있다는 사실을 아실 수 있습니다. 그렇다면 컴퓨터 설계자의 입장으로 돌아가서, 어떻게 컴퓨터를 설계해야할지 생각해보도록 합시다.
우선 여러분은 아래의 명령을 해독하고, 실행하는 기계를 만들고 싶습니다:   
```C
1 + 1 = ? 
```
우선, 저 명령을 저장할 **메모리**와 실제 연산을 실행할 **연산기**가 필요합니다. 이 메모리를 레지스터(*Register-'저항'을 뜻하는 'resister'와는 다릅니다*)라고 칭하고, 실제 명령을 연산하는 장치의 이름을 산술논리장치(ALU, Arithmetic Logic Unit)이라 합니다. 이 둘을 제어하는 제어부(control unit)가 추가되면, 우리에게 익숙한 부품, **CPU**(Central Processing Unit)가 완성됩니다.   
```
+------+----+---+
|CONTOL|    | C |
+------+    | A |
+-----+-----+ C |
|     |     | H |
| Reg | ALU | E |
+-----+-----+---+
```
(대부분의 CPU에서는 아래 설명할 RAM과 레지스터 사이에 1-3단계의 캐시 메모리(Cache Memory(L1-L3))를 추가로 탑재하고 있습니다.)

 이제 이 컴퓨터가 연산할 데이터의 양을 늘리고 싶습니다. 레지스터의 수가 늘어나면 좋겠지만, 이 레지스터(또는 캐시 메모리)는 굉장히 비싼 부품이므로 우리는 조금은 더 값싼, 하지만 빠른 접근을 위해 임의 접근(Random Access)가 가능한 부품을 추가하였습니다. 이 부품의 이름은 **RAM**(Random Access Memory)고, 주기억장치(Main Memory)라고도 불립니다.

RAM으로 추가 메모리를 확보하였지만, 아직 저희는 용량이 부족합니다.
> 2023년 현재 RAM 1GB: 약 5000원   
> Call of Duty: Modern Warfare(2019)의 용량: 약 133GB  
> **저장 비용: ???**

또한 RAM은 전원이 꺼졌을 경우 휘발하는(Volatile) 특성이 있으므로 저희는 용량 대비 가격이 저렴하고 비휘발성 메모리를 추가하게 됩니다. 이를 **보조 기억 장치**(Secondary Memory)라고 부르며, 보통 자기 디스크(HDD)나 SSD 등을 사용합니다.

마지막으로, 이 장치들을 연결하고 관리하는 회로 및 부품으로 구성된 기판(**메인보드***Main board*)과 전원 장치, 그리고 그래픽을 담당하는 유닛(**GPU**)를 추가하면 컴퓨터가 완성됩니다.

### 그리고 컴퓨터에서 운영체제까지
자, 이제 물리적인 컴퓨터가 준비되었습니다. 하지만 우리는 또 한가지 문제에 직면하고 있습니다. 우리의 컴퓨터는 디지털 세계, 즉 0과 1로(Binary) 이루어진 세상인데, 이 세상에서 우리가 무언가를 하기에는 너무나도 힘들고 어렵습니다. 우리는 이러한 물리적인 세상 위에 *인류가 조금 더 이해하기 쉽고 사용하기 간편한 세상*을 구축하고 싶습니다.([폰 노이만](https://ko.wikipedia.org/wiki/%EC%A1%B4_%ED%8F%B0_%EB%85%B8%EC%9D%B4%EB%A7%8C) 아저씨는 빼구요!)   
그래서 우리는 각각의 하드웨어 부품들을 통제하는 프로그램을 제작하기로 결심했습니다.
- 우선, 가장 중요한 CPU에서 어떤 작업을 실행할지 통제하고, (스케쥴링)
- 주기억장치의 어느 부분에 어떤 내용이 할당되고, 언제 어떻게 변경할지 관리하며, (메모리 관리)
- 보조기억장치의 저장 및 로드를 관리하며,
- 기억장치간 데이터 통신 및 외부 데이터 통신(마우스, 키보드, 모니터, 네트워크 등등)을 관장하며(드라이버),
- 에러 관리 및 보안 유지 등 시스템 향상성을 유지하려고 합니다.

이를 통해 아래와 같은 구조(커널*Kernel*)가 완성되었습니다:
```
+------------------+
|      Kernel      |
| +--------------+ |
| |    Driver    | |
+-+--------------+-+
|     HARDWARE     |
+------------------+

```
위의 구조를 조금 더 쉽고 안전하게 사용하기 위해 특정 기능별 함수를 추가하였고, 이를 시스템 콜(System Call)이라고 정의하였습니다. 그리고 우리가 친숙하게 사용할 수 있도록 유저 인터페이스(UI)도 추가하였구요.
```
                              User
+------------------+ ------------------------
|  User Interface  |
+------------------+
|    System Call   |
+------------------+   Operating System(OS)
|      Kernel      |
| +--------------+ |
| |    Driver    | |
+-+--------------+-+ ------------------------
|     HARDWARE     |
+------------------+

```
이렇게 하드웨어를 쉽고 안전하고, 효율적으로 제어하기 위해서 여러 계층으로 이루어진 프로그램이 완성되었습니다. 우리는 이를 컴퓨터를 운영하는 프로그램이라는 뜻으로, '**운영 체제(Operating System)**'이라고 부르기로 하였습니다. 우리가 사용하는 프로그램 등은 이 OS 위에서 작동하게 됩니다.


### 계층 구조
 컴퓨터 시스템은 위에서 설명하다시피, 대개 계층 구조를 채택하고 이를 구현하는 방식으로 이루어져 있습니다.
 **왜 시스템을 디자인 할 때 계층 구조를 주로 사용할까요?**
 
 바로 위에 언급된 구조를 참고해 보겠습니다. 유저 영역에서 무언가 작업을 하고자 할 경우 아래와 같은 단계를 거쳐서 이루어집니다:
 ```
+------------------+    +------------------+    +------------------+    +------------------+   
|  User Interface  | => |    System Call   | => |      Kernel      | => |      Driver      | => (Wait...)
+------------------+    +------------------+    +------------------+    +------------------+
+------------------+(Result)+------------------+    +------------------+    +------------------+
|     HARDWARE     |   =>   |      Driver      | => |      Kernel      | => |    System Call   | =>
+------------------+        +------------------+    +------------------+    +------------------+
+------------------+
|  User Interface  |
+------------------+
 ```
 보시다시피, 원하는 결과를 얻기 위해 굉장히 긴 과정을 거치는 것을 확인할 수 있습니다. 하지만, 다시 거슬러 올라가서 운영체제를 디자인한 이유를 다시 살펴봅시다.
 > 우리의 컴퓨터는 디지털 세계, 즉 0과 1로(Binary) 이루어진 세상인데, 이 세상에서 우리가 무언가를 하기에는 너무나도 힘들고 어렵습니다.
 
 계층 구조를 사용할 경우 우리는 하드웨어가 어떻게 명령을 받아들이고 해독하는지, 드라이버는 어떻게 명령을 내리고 대기하는지 **알 필요가 없습니다**. 단지, 각 계층의 프로그램은 자신과 이웃한 계층(위 혹은 아래)와 어떻게 소통하는지만 알면 원하는 작업을 실행할 수 있게 됩니다. 이를 통해 컴퓨터 시스템을 효율적이고, 체계적이며(각자 고유 프로토콜 vs. 일관화된 계층 호출), 보안성(위 혹은 아래로 침범할 수 없음) 등이 있는 시스템을 구축할 수 있게 됩니다.
 
 
 또다른 를 위해 가장 대표적인 계층 구조 두가지를 가져와 보았습니다.

#### OSI-7계층
```
1. Application Layer   |\
2. Presentation Layer  | |=> Upper Layers
3. Sesson Layer        |/
4. Transport Layer     |\
5. Network Layer       | |=> Transport Service
6. Data Link Layer     | |
7. Physical Layer      |/
```

#### 메모리 계층(Memory Hierachy)
```
                +----------------+
L0:             |    Register    |
              +--------------------+
L1:           |      L1 cache      | (SRAM)
            +------------------------+
L2:         |        L2 cache        | (SRAM)
          +----------------------------+
L3:       |          L3 cache          | (SRAM)
        +--------------------------------+
L4:     |           Main Memory          | (DRAM)
      +------------------------------------+
L5:   |       Local secondary Storage      | (Local Disks(HDD, SSD...))
    +----------------------------------------+
L6: |        Remote Secondary Storage        | (Distributed File Systems, Web servers...)
    +----------------------------------------+
```
