# CHAPTER 1. Elementary of mathematics


## Set Theory (집합론)

(익숙한 내용이라 생략)


## Measure Theory (측도론)

직관적인 개념으로서 측도(measure)란 일정 규칙에 따라 **주어진 집합에 숫자를 부여하는 함수**입니다.  
예를 들어, 아래와 같이 정의한 집합 $S$에 대한 셈측도(counting measure)는 측도입니다.

(정의 1.1) **셈측도(counting measure)**  
$ \mu = \left\{\begin{matrix}
n(S) (S\text{ is finite}) \\ \infty (S\text{ is infinite})
\end{matrix}\right.  $

### $\sigma$-field

측도의 수학적 정의에 $\sigma$-field라는 생소한 개념이 들어가기 때문에 먼저 살펴보아야 합니다.

**정의**

(정의 1.2) **sigma field**  
전체집합 $U$의 멱집합(power set) $2^U$의 원소를 아래 조건에 맞게 잘 골라낸 부분집합 $\mathcal{B}$를 $\sigma$-field라고 부릅니다.

1. 공집합을 반드시 포함한다. ($\phi \in \mathcal{B}$)
2. 차집합 연산에 대해 닫혀 있다. ($B \in \mathcal{B} \Rightarrow B^C \in \mathcal{B}$)
3. 셀 수 있는 합집합 연산에 대해 닫혀 있다. ($B_i \in \mathcal{B} \Rightarrow \bigcup_{i = 1}^{\infty}B_i \in \mathcal{B}$)

예를 들어, $U = \{1, 2, 3\}$에 대하여  
$A = \{\phi, \{1 \}, \{2, 3 \}, \{1, 2, 3 \}\}$는 $U$의 $\sigma$-field로서 자격이 있지만,  
$B = \{\phi, \{1 \}, \{2 \}, \{1, 2 \}, \{1, 2, 3 \}\}$는 그렇지 못합니다.

$\mathcal{B}$가 $U$로부터 만들어진 $\sigma$-field임을 표현하기 위해 수식으로 $\mathcal{B} = \sigma(U)$와 같이 표현합니다.

**성질**

주요 성질은 다음과 같습니다.

1. 전체집합 $U \in \mathcal{B}$ (정의의 1번과 2번 생각하면 당연)
2. $B_i \in \mathcal{B} \Rightarrow \bigcap_{i = 1}^{\infty}B_i \in \mathcal{B}$  
증명: 정의 2번에 따라 모든 $B_i$의 차집합 $B_i^C$가 $\mathcal{B}$에 포함되어 있습니다.   
정의 3번에 따라 이 차집합의 합집합($\bigcup_{i = 1}^{\infty}B_i^C$) 또한 $\mathcal{B}$에 포함되어 있습니다.  
드 모르간의 법칙에 따라 이 합집합을 $\bigcap_{i = 1}^{\infty}B_i$으로 나타낼 수 있습니다. [끝]
3. $U$의 멱집합 $2^U$은 $U$의 $\sigma$-field입니다.
4. $\sigma$-field는 유한(finite)하거나 셀 수 없이 무한하거나(uncountably infinite) 둘 중 하나입니다.  
직관: $U$가 유한집합이면 $2^U$ 또한 유한집합이기 때문에 $\sigma$-field는 유한합니다.  
$U$가 무한집합이면 $2^U$는 셀 수 없이 무한하기 때문에 $\sigma$-field는 셀 수 없이 무한합니다.  
어떤 경우에도 $\sigma$-field는 셀 수 있도록 무한하지 않습니다. [끝]
5. 두 $\sigma$-field $\mathcal{B}$, $\mathcal{C}$의 교집합은 $\sigma$-field이고, 합집합은 $\sigma$-field가 아닙니다.

### 측도(measure)

전체집합 $U$와 그로부터 구성한 $\sigma$-field를 묶어 measurable space가 형성됩니다.   
드디어 이 space에서의 측도를 정의할 준비가 되었습니다.

(정의 1.3) **측도(measure)**  
Measurable space $(U, \mathcal{B})$에 대해 다음과 같은 성질을 만족하도록 정의된 함수 $\mu : \mathcal{B} \rightarrow [0, \infty] $를 $(U, \mathcal{B})$에 대한 측도라고 합니다.

1. 공집합에 대한 함숫값은 0 : $\mu(\phi) = 0$
2. 셀 수 있는 서로소 집합에 대한 덧셈 : $\mu(\bigcup_{i = 1}^{\infty}B_i) = \sum_{i = 1}^{\infty}\mu(B_i)$

이제 (정의 1.1)의 셈측도가 측도로서의 자격이 있다는 걸 이해할 수 있습니다.  
개수는 항상 0개 이상이고, 공집합의 개수는 0이고, 정의 2번의 덧셈 연산도 문제 없이 이뤄짐을 직관적으로 확인할 수 있습니다.

우리에게 친숙한 측도로는 셈측도뿐만 아니라 **확률(probability) 또한 일종의 측도**입니다.  
$U$ 자리에 sample space $\Omega$를 넣고, $P(\Omega) = 1$이라는 normalization 조건만 추가해주면 우리에게 친숙한 확률의 정의가 됩니다!

(정의 1.4) **확률(probability)**  
Sample space $\Omega$와 그에 대한 $\sigma$-field $\mathcal{A}$로 이루어진 measurable space $(\Omega, \mathcal{A})$에 대하여 다음과 같은 성질을 만족하도록 정의된 함수 $P : \mathcal{A} \rightarrow [0, 1] $를 $(\Omega, \mathcal{A})$에 대한 확률이라고 합니다.

1. 공사건에 대한 함숫값은 0 : $P(\phi) = 0$
2. 셀 수 있는 서로소 사건에 대한 덧셈 : $P(\bigcup_{i = 1}^{\infty}A_i) = \sum_{i = 1}^{\infty}P(A_i)$
3. **(추가!)** 전사건에 대한 함숫값은 1 : $P(\Omega) = 1$

(정의 1.3)과 비교하면서 따져보면 3번 조건이 추가된 것 빼고는 별다를 게 없습니다.  
확률이 측도이기 때문에 측도론을 훑어본 것이죠!

measurable space $(U, \mathcal{B})$에 대해 특정 측도 $\mu$를 정의하고 나면  
$(U, \mathcal{B}, \mu)$로 구성된 measure space가 정의됩니다.