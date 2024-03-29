너는 잊는 것이 병이라고 생각하느냐? 잊는 것은 병이 아니다. 너는 잊지 않기를 바라느냐? 잊지 않는 것이 병이 아닌 것은 아니다. 그렇다면 잊지 않는 것이 병이 되고, 잊는 것이 도리어 병이 아니라는 말은 무슨 근거로 할까? 잊어도 좋을 것을 잊지 못하는 데서 연유한다. 잊어도 좋을 것을 잊지 못하는 사람에게는 잊는 것이 병이라고 치자. 그렇다면 잊어서는 안 되는 것을 잊는 사람에게는 잊는 것이 병이 아니라고 말할 수 있다. 그 말이 옳을까?

2024학년도 대학수학능력시험 국어 영역 `유한준-잊음을 논함`을 참고하였습니다.
[GNE](https://github.com/heartleth/GNE) 로 실행할 수 있습니다.

# 자료구조
* 8개의 스택이 있습니다. 각각의 이름은 다음과 같습니다.

> 어버이에게는 효심을  
> 임금에게는 충성심을  
> 부모를 잃고서는 슬픔을  
> 제사를 지내면서 정성스러운 마음을  
> 물건을 주고받을 때 의로움을  
> 나아가고 물러갈 때 예의를  
> 낮은 지위에 있으면서 제 분수를  
> 이해의 갈림길에서 지켜야 할 도리를  

# 문법

모든 프로그램은 첫 줄에 `나는 이홍에게 이렇게 말했다.`를 쓰고 다음 줄부터 써야 합니다. 수능 국어 지문이 그렇게 편집되어 있기 때문입니다.

## 표현식
* 스택의 이름을 사용하여 스택의 top을 지칭할 수 있습니다.
  * `어버이에게는 효심을` > `어버이.top()`

### 숫자
* 순서대로 십진수로 0~9에 대응됩니다. 음수와 10이상의 수는 아래의 수를 사칙연산하여 표현합니다.

> 잊지 말아야 할 것을  
> 잊어도 좋을 것을  
> 눈은 아름다움을  
> 귀는 좋은 소리를  
> 입은 맛난 음식을  
> 사는 곳은 크고 화려한 집을  
> 천한 신분인데도 큰 세력을  
> 집이 가난하건만 재물을  
> 고귀한데도 교만한 짓을  
> 부유한데도 인색한 짓을  

### 사칙연산
* 합은 `잊으며, ` 로 연결합니다.
  * `부유한데도 인색한 짓을 잊으며, 잊어도 좋을 것을` > `9 + 1` > `10`
* 차는 `잊지 못하며, `로 연결합니다.
  * `잊지 말아야 할 것을 잊지 못하며, , 잊어도 좋을 것을` > `0 - 1` > `-1`
* 곱은 `잊고, 도리어 `로 연결합니다.
  * `눈은 아름다운 것을 잊고, 도리어 임금에게는 충성심을` > `2 * 임금.top()`
* 나눗셈은 `잊지 못하고, 도리어 `로 연결합니다.
  * `눈은 아름다운 것을 잊지 못하고, 도리어 임금에게는 충성심을` > `2 * 임금.top()`

## push
* `S 잊지 못하는 것은 E 잊는 데서 연유한다.`는 표현식 E의 값을 스택 S에 push한다는 뜻입니다.
* `S1 잊지 못하고, S2 잊는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다.`로 S1의 top을 S2에 push할 수 있습니다.

## pop
* 스택을 `잊는다`면 스택을 pop할 수 있습니다. 굉장히 직관적입니다.

    나아가고 물러갈 때 예의를 잊는다. > 나아가고물러갈때.pop()
    낮은 지위에 있으면서 제 분수를 잊는다. > 낮은지위.pop()

## swap
* 스택의 top끼리 swap하려면, 내적이 것과 외적인 것을 서로 바꾸는 능력이 있는 사람이 필요합니다.

    S1 잊지 못하고, S2 잊지 못하는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다. > swap(S1.top(), S2.top())

## while

* 그 말이 옳다면 (A=B인 것이 병이라고 했을 때 병이라면, 병이 아니라면) 두 문장 사이의 문장들을 반복합니다.

    그렇다면 A 잊고 B 잊는 것이 병이라고(병이 아니라고) 치자. > while (A == B) {
    그 말이 옳을까?                                        > }

* 예시: 10부터 1까지 출력
> 나는 이홍에게 이렇게 말했다.  
> 임금에게는 충성심을 잊지 못하는 것은 부유한데도 인색한 짓을 잊으며, 잊어도 좋을 것을 잊는 데서 연유한다. 그렇다면 임금에게는 충성심을 잊고 잊지 말아야 할 것을 잊는 것이 병이 아니라고 치자. 임금에게는 충성심을 잊지 못하고, 이해의 갈림길에서 지켜야 할 도리를 잊는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다. 임금에게는 충성심을 잊으면 하늘이 잊지 못해 벌을 내린다. 낮은 지위에 있으면서 분수를 잊으면 하늘이 잊어 벌을 내리지 않는다. 임금에게는 충성심을 잊지 못하는 것은 이해의 갈림길에서 지켜야 할 도리를 잊지 못하며, 잊어도 좋을 것을 잊는 데서 연유한다. 그 말이 옳을까?

## ~~입~~출력
### ~~입력~~
* 정수
* 아스키
### 출력
* 스택이 비어있다면 다음 줄로 개행합니다. 출력에는 pop이 뒤따릅니다.
* 정수 출력하기
  * 다음 문장은 어버이 스택의 top에 대응하는 수를 십진수로 출력하고 원소 1개를 pop합니다.
> 어버이에게는 효심을 잊으면 하늘이 잊지 못해 벌을 내린다.
* 유니코드 문자 출력하기
  * 다음 문장은 어버이 스택의 top에 대응하는 유니코드 문자를 출력하고 원소 1개를 pop합니다.
> 어버이에게는 효심을 잊으면 하늘이 잊어 벌을 내리지 않는다.

## 예시: Hello, world!

> 나는 이홍에게 이렇게 말했다.  
> 물건을 주고받을 때 의로움을 잊지 못하는 것은 입은 맛난 음식을 잊고, 도리어 집이 가난하건만 재물을 잊으며, 잊어도 좋을 것을 잊는 데서 연유한다. 임금에게는 충성심을 잊지 못하는 것은 고귀한데도 교만한 짓을 잊고, 도리어 부유한데도 인색한 짓을 잊는 데서 연유한다. 부모를 잃고서는 슬픔을 잊지 못하는 것은 물건을 주고받을 때 의로움을 잊으며, 임금에게는 충성심을 잊는 데서 연유한다. 부모를 잃고서는 슬픔을 잊지 못하고, 부모를 잃고서는 슬픔을 잊는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다. 임금에게는 충성심을 잊으면 하늘이 잊어 벌을 내리지 않는다. 부모를 잃고서는 슬픔을 잊으면 하늘이 잊어 벌을 내리지 않는다. 부모를 잃고서는 슬픔을 잊지 못하는 것은 부모를 잃고서는 슬픔을 잊으며, 집이 가난하건만 재물을 잊는 데서 연유한다. 부모를 잃고서는 슬픔을 잊지 못하고, 부모를 잃고서는 슬픔을 잊는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다. 부모를 잃고서는 슬픔을 잊지 못하고, 부모를 잃고서는 슬픔을 잊는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다. 부모를 잃고서는 슬픔을 잊으면 하늘이 잊어 벌을 내리지 않는다. 부모를 잃고서는 슬픔을 잊으면 하늘이 잊어 벌을 내리지 않는다. 부모를 잃고서는 슬픔을 잊지 못하는 것은 부모를 잃고서는 슬픔을 잊으며, 귀는 좋은 소리를 잊는 데서 연유한다. 부모를 잃고서는 슬픔을 잊지 못하고, 부모를 잃고서는 슬픔을 잊는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다. 부모를 잃고서는 슬픔을 잊으면 하늘이 잊어 벌을 내리지 않는다. 제사를 지내면서 정성스러운 마음을 잊지 못하는 것은 사는 곳은 크고 화려한 집을 잊고, 도리어 부유한데도 인색한 짓을 잊지 못하며, 잊어도 좋을 것을 잊는 데서 연유한다. 임금에게는 충성심을 잊지 못하는 것은 제사를 지내면서 정성스러운 마음을 잊고, 도리어 눈은 아름다움을 잊으며, 물건을 주고받을 때 의로움을 잊으며, 눈은 아름다움을 잊는 데서 연유한다. 물건을 주고받을 때 의로움을 잊지 못하는 것은 귀는 좋은 소리를 잊으며, 물건을 주고받을 때 의로움을 잊는 데서 연유한다. 제사를 지내면서 정성스러운 마음을 잊으면 하늘이 잊어 벌을 내리지 않는다. 물건을 주고받을 때 의로움을 잊지 못하고, 물건을 주고받을 때 의로움을 잊는 사람은 내적인 것과 외적인 것을 서로 바꿀 능력이 있다. 물건을 주고받을 때 의로움을 잊으면 하늘이 잊어 벌을 내리지 않는다. 임금에게는 충성심을 잊으면 하늘이 잊어 벌을 내리지 않는다. 부모를 잃고서는 슬픔을 잊지 못하는 것은 부모를 잃고서는 슬픔을 잊지 못하며, 귀는 좋은 소리를 잊는 데서 연유한다. 부모를 잃고서는 슬픔을 잊지 못하는 것은 부모를 잃고서는 슬픔을 잊으며, 천한 신분인데도 큰 세력을 잊는 데서 연유한다. 부모를 잃고서는 슬픔을 잊지 못하는 것은 부모를 잃고서는 슬픔을 잊지 못하며, 귀는 좋은 소리를 잊는 데서 연유한다. 부모를 잃고서는 슬픔을 잊으면 하늘이 잊어 벌을 내리지 않는다. 부모를 잃고서는 슬픔을 잊으면 하늘이 잊어 벌을 내리지 않는다. 부모를 잃고서는 슬픔을 잊으면 하늘이 잊어 벌을 내리지 않는다. 임금에게는 충성심을 잊지 못하는 것은 눈은 아름다움을 잊고, 도리어 사는 곳은 크고 화려한 집을 잊고, 도리어 눈은 아름다움을 잊고, 도리어 사는 곳은 크고 화려한 집을 잊는 데서 연유한다. 임금에게는 충성심을 잊으면 하늘이 잊어 벌을 내리지 않는다. 물건을 주고받을 때 의로움을 잊지 못하는 것은 물건을 주고받을 때 의로움을 잊으며, 잊어도 좋을 것을 잊는 데서 연유한다. 물건을 주고받을 때 의로움을 잊으면 하늘이 잊어 벌을 내리지 않는다. 낮은 지위에 있으면서 제 분수를 잊으면 하늘이 잊어 벌을 내리지 않는다.
