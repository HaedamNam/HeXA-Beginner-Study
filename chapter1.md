# 환경설정과 `markdown`, 그리고 기초 컴퓨터 구조
## 개요
이 스터디에서는 컴퓨터공학과에서 사용할 영역에 대한 전반적이고 기초적인 지식을 다룰 예정입니다. 이 스터디를 통해, 여러분은 

## 환경설정

### 컴퓨터 공학
컴퓨터 공학에서 여러분은 

## `markdown`
우선, 프로그래밍 언어로 어떤 것을 제작하고 수정하는 것에 익숙해지기 위해, 
[마크업 언어](https://en.wikipedia.org/wiki/Markup_language)인 마크다운을 통해 접근해보는 시간을 가져보도록 하겠습니다.
마크다운은 비록 프로그래밍 언어는 아니지만([튜링 불완전](https://en.wikipedia.org/wiki/Turing_completeness)), 간단한 문법과 가벼운 파일 크기 덕택에 
대부분의 프로젝트에서 README를 작성하는데 사용되고 있습니다. `markdown`에 처음인 사용자도 1시간이면 다 배울 수 있을정도로요!  

>(참고: [18F의 README를 작성하는 가이드](https://github.com/18F/open-source-guide/blob/18f-pages/pages/making-readmes-readable.md))

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


## 기초 컴퓨터 구조
다음으로, 우리가 사용하는 컴퓨터가 어떻게 구성되어 있는지 간단하게 살펴보도록 하겠습니다.

### 스크래치에서 컴퓨터까지


### 계층 구조
 컴퓨터 시스템은 대개 계층 구조를 

#### OSI-7계층

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
