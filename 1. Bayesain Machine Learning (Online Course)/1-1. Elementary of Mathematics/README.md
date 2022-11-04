# CHAPTER 1. Elementary of mathematics


## Set Theory (집합론)

(익숙한 내용이라 생략)


## Measure Theory (측도론)

직관적인 개념으로서 측도(measure)란 일정 규칙에 따라 **주어진 집합에 숫자를 부여하는 함수**입니다.  
예를 들어, 아래와 같이 정의한 집합 $S$에 대한 셈측도(counting measure)는 측도입니다.

(정의 1.1) **셈측도(counting measure)**  
$ \mu = n(S) (S\text{ is finite}) \text{ or } \infty (S\text{ is infinite})   $

### $\sigma$-field

측도의 수학적 정의에 $\sigma$-field라는 생소한 개념이 들어가기 때문에 먼저 살펴보아야 합니다.

**정의**

(정의 1.2) **sigma field**  
전체집합 $U$의 멱집합(power set) $2^U$의 원소를 아래 조건에 맞게 잘 골라낸 부분집합 $\mathcal{B}$를 $\sigma$-field라고 부릅니다.

1. 공집합을 반드시 포함한다. ( $\phi \in \mathcal{B}$ )
2. 차집합 연산에 대해 닫혀 있다. ( $B \in \mathcal{B} \Rightarrow B^C \in \mathcal{B}$ )
3. 셀 수 있는 합집합 연산에 대해 닫혀 있다. ( $B_i \in \mathcal{B} \Rightarrow \bigcup_{i = 1}^{\infty}B_i \in \mathcal{B}$ )

예를 들어, $U = \{1, 2, 3\}$에 대하여  
$A = \{\phi, \{1 \}, \{2, 3 \}, \{1, 2, 3 \}\}$는 $U$의 $\sigma$-field로서 자격이 있지만,  
$B = \{\phi, \{1 \}, \{2 \}, \{1, 2 \}, \{1, 2, 3 \}\}$는 그렇지 못합니다.

$\mathcal{B}$가 $U$로부터 만들어진 $\sigma$-field임을 표현하기 위해 수식으로 $\mathcal{B} = \sigma(U)$와 같이 표현합니다.

**성질**

주요 성질은 다음과 같습니다.

1. 전체집합 $U \in \mathcal{B}$ (정의의 1번과 2번 생각하면 당연)
2. $B_i \in \mathcal{B} \Rightarrow \bigcap_{i = 1}^{\infty}B_i \in \mathcal{B}$  
증명: 정의 2번에 따라 모든 $B_i$의 차집합 $B_i^C$가 $\mathcal{B}$에 포함되어 있습니다.   
정의 3번에 따라 이 차집합의 합집합( $\bigcup_{i = 1}^{\infty}B_i^C$ ) 또한 $\mathcal{B}$에 포함되어 있습니다.  
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

**정의**

(정의 1.3) **측도(measure)**  
Measurable space $(U, \mathcal{B})$에 대해 다음과 같은 성질을 만족하도록 정의된 함수 $\mu : \mathcal{B} \rightarrow [0, \infty] $를 $(U, \mathcal{B})$에 대한 측도라고 합니다.

1. 공집합에 대한 함숫값은 0 : $\mu(\phi) = 0$
2. 셀 수 있는 서로소 집합에 대한 덧셈 : $\mu(\bigcup_{i = 1}^{\infty}B_i) = \sum_{i = 1}^{\infty}\mu(B_i)$

measurable space $(U, \mathcal{B})$에 대해 특정 측도 $\mu$를 정의하고 나면  
$(U, \mathcal{B}, \mu)$로 구성된 measure space가 정의됩니다.

$\mu(\Omega) < \infty$이면 측도 $\mu$는 유한 측도(finite measure)가 됩니다.

**예시**

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


## Probability (확률론), Random Variable (확률변수)

(익숙한 내용이라 생략)


## Random Process (확률과정)

확률과정은 무한개의 확률변수를 표현하기 위해 등장하는 개념입니다.  
확률과정의 정의를 알아보고 연관 개념들을 차례대로 살펴봅시다.

### 정의

(정의 1.5) **확률과정(random process)**  
확률측도 $P$가 정의된 공통의 measure space $(\Omega, \mathcal{A}, P)$에 대해 정의된 확률변수의 indexed family*를 뜻합니다.  
이때, 해당 족에 포함된 모든 확률변수는 공통의 measurable space $(S, \Sigma)$로의 사상(mapping)이어야 합니다.  
Indexing에 사용한 index set을 $T$**라고 하면 다음과 같이 나타낼 수 있습니다.    
$\lbrace X_t(w) : \Omega \rightarrow S | t \in T \rbrace$  
각 확률변수의 공역인 $S$는 state space라고 부릅니다.

*Indexed family란 index set의 원소를 index로 이용하여 번호를 붙인 원소들의 집합을 뜻합니다.  
**전통적으로 T에는 시간을 표현하는 실수 또는 자연수 집합을 사용하는 경우가 많지만, 시간 이외의 다른 뜻을 가진 다양한 index를 활용할 수도 있습니다.

> 🚧 **주의!** 확률과정에서의 sample space $\Omega$    
>
> 위 (정의 1.5)에서 sample space $\Omega$에 대해 오해하기 쉬운 부분이 있어서 예시를 통해 짚고 넘어가겠습니다.  
>   
> 앞/뒷면이 나올 확률이 1/2로 같은 동전을 무한 번 던지는 실험에 대해서 확률과정을 아래와 같이 정의합시다.  
> $\lbrace X_t(w) : \Omega \rightarrow \{0, 1\} = (\text{if } t\text{th coin head then 1, else 0}) | t \in \mathbb{N} \rbrace$  
>   
> 여기서 sample space $\Omega$를 구성하는 sample point $w$로 적합한 것은  
> ❌ 한 번의 동전 뒤집기에 대한 결과인 {0}이나 {1}이 아니라  
> ✔️ 전체 동전 뒤집기에 대한 결과인 {0, 1, 0, 0, 1, 1, ...}이나 {1, 0, 0, 0, 1, 1, ...}입니다.   

아래와 같은 유한차원 확률분포(Finite-dimensional probability distribution)를 이용하면 확률과정을 규정할 수 있습니다.  
$P((X_{t_1}, ..., X_{t_k}) \in B) \text{ for any } B, k$  
여기서 $B$는 state space $S$의 cartesian power $S^k = S \times S \times ... \times S$의 부분집합을 의미합니다.  
다만, [stack exchang 질의응답](https://math.stackexchange.com/questions/3144894/what-does-it-mean-the-finite-dimensional-distribution-determine-the-random-pro)을 살펴보면 같은 유한차원 확률분포를 가지는 서로 다른 확률과정도 존재하는 것으로 보이니 엄밀하지는 않은 것으로 보입니다.

### 확률과정을 보는 두 가지 관점: 확률변수의 집합, 함수공간으로의 사상

확률과정의 정의에 따라, 확률과정을 index set $T$의 원소 $t$와 sample space $\Omega$의 원소 $w$의 함수로 볼 수 있습니다. 즉,  
$X_t : T \times \Omega \rightarrow \mathbb{R}$

1. 여기에서 확률과정 $X_t(w)$에서 $t$를 고정하면 확률변수가 됩니다. 이 사실은 (정의 1.5)을 통해 이미 알아차렸을 것입니다.
2. 반대로 $w$를 고정하면 $t$에 대한 함수를 얻게 됩니다. 각각의 $t$에 대해 $T=t$일 때 확률변수 $X_t$가 sample point $w$를 어떤 숫자로 표현하는지 나타내는 함수가 만들어집니다.  
이러한 $t$에 대한 함수를 sample function 또는 realization이라고 부르며, $T$가 시간 인덱스 집합일 때는 특히 sample path라고 부릅니다.  

위 2번 항목에서 확률과정에 sample point $w$를 넣어주면 sample function : $T \rightarrow S$가 튀어나오는 것을 알 수 있습니다.  
즉, T(index space)에서 S(state space)로 가는 함수의 공간을 $S^T$라고 하면,  
확률과정 $\{X_t(w) : \Omega \rightarrow S | t \in T \}$을 $\Omega \rightarrow S^T$로의 함수(사상)로 해석할 수도 있습니다!

추가적으로, 확률과정은 다음과 같은 두 가지 기준에 따라 분류할 수 있습니다.

1. 인덱스 집합 $T$의 특성: discrete-time RP, continuous-time RP
2. 확률변수 $X_t$의 특성: discrete-valued RP, continuous-valued RP

### 예시: 브라운 운동(Brownian motion)을 표현한 위너 확률과정(Wiener Process)

위너 과정은 다음과 같은 성질을 가지는 확률과정 $W_t$을 뜻합니다.

1. $W_0 = 0$
2. 독립적 증분(independent increment): $W_{t+u} - W_t (u \ge 0)$가 $W_t$와 독립
3. 증분은 정규분포를 따른다: $W_{t+u} - W_t \sim N(0, u)$
4. sample path가 연속적이다

아래 그림은 1차원 상에서의 브라운 운동을 표현한 위너 확률과정의 sample path(또는 realization)입니다.  
이를 통해 다시 한 번 확률과정이 $t$에 대한 함수를 출력하는 함수로 해석될 수 있음을 확인할 수 있습니다.  
매번 시행을 하면 시행의 결과에 따른 새로운 함수가 나타나겠죠?

![Wiener Process Sample Path](https://upload.wikimedia.org/wikipedia/commons/3/3e/Wiener_process_zoom.png)  
(그림 1.1) 1차원 위너 확률과정의 sample path 예시 (출처: [위키피디아 "Wiener Process"](https://commons.wikimedia.org/wiki/File:Wiener_process_zoom.png#filelinks))

위너 확률과정은 continuous-time RP이며, 또한 continuous-valued RP라는 것을 알 수 있습니다.

### 확률과정의 모멘트(moment)

확률변수나 확률분포와 마찬가지로 확률과정에서도 모멘트가 정의됩니다.  
눈여겨볼 점은, 모두 시점 1개나 2개에 대한 함수라는 것입니다.

- mean function: $m_X(t)\equiv E(X_t) = \sum_{x}^{}xp_{x_{t}}(x) \text{ (discrete) or } \int xf_{x_{t}}(x)dx \text{ (continuous)}$  
$t  = t_0$일 때에 해당하는 확률변수 $X_{t_0}$를 가져와 해당 확률변수의 평균을 구한다고 생각하면 쉽습니다.
- **auto-correlation function(acf)**: $R_X(t, s) = E[X_tX_s]$  
확률변수에서 correlation 식과 같지만 같은 확률과정 속 서로 다른 두 시점의 확률변수를 가져온다는 점만 다릅니다.
- **auto-covariance function(acvf)**: $C_X(t, s) = E[(X_t - m_X(t))(X_s - m_X(s))]$  
마찬가지로 확률변수에서의 공분산 식과 같지만 같은 확률과정 속 서로 다른 두 시점의 확률변수를 가져온다는 점만 다릅니다.
- cross-covariance function(ccvf): $R_{XY}(t, s) = E[(X_t - m_X(t))(Y_s - m_Y(s))]$  
acvf와 식이 비슷하지만 이번엔 서로 다른 두 확률과정에서 각각 하나씩 확률변수를 가져왔다는 점이 다릅니다.  

### Stationarity

(정의 1.6) **(Strong) stationary random process**

어떤 확률과정 $\{X_t(w) : \Omega \rightarrow S | t \in T \}$가 모든 $\tau, k, t_1, ..., t_k$에 대해  
$P((X_{t_1 + \tau}, ..., X_{t_k + \tau}) \in B) = P((X_{t_1}, ..., X_{t_k}) \in B)$이면 이 확률과정은 stationary하다고 말합니다.

Stationary random process의 mean function, acvf, ccvf는 모두 stationary합니다. (생각해보면 당연합니다.)  
mean : $m_X(t + \tau) = m_X(t)$  
acf : $R_X(t + \tau, s + \tau) = R_X(t, s)$  
acvf : $C_X(t + \tau, s + \tau) = C_X(t, s)$  

mean function이 stationary하다는 것은 결국 mean function이 constant임을 뜻합니다. ($m_X(t) = m_X$)

또한, stationary 확률과정에서 acf와 acvf는 모두 '시간차($\tau$)`에 대한 함수로 만들 수 있습니다.  
acf : $R_X(t, s) = R_X(\tau = t - s)$  
acvf: $C_X(t, s) = C_X(\tau = t - s)$ 

Strong stationarity애서는 정의에서 위 성질이 도출되었다면,  
반대로 wide-sense stationarity룰 츙족하기 위해서는 위 성질을 충족하면 됩니다.

(정의 1.7) **Wide-sense stationary random process**  
어떤 확률과정 $\{X_t(w) : \Omega \rightarrow S | t \in T \}$가 모든 $t, s \in T, \tau$에 대해  
다음 조건을 만족하면 이 확률과정은 weak stationary하다고 말합니다.  
- mean : $m_X(t + \tau) = m_X(t)$   
- acvf : $R_X(t + \tau, s + \tau) = R_X(t, s)$

acf 조건이 빠진 이유는 mean 조건과 acvf 조건에서 acf 조건을 유도할 수 있기 때문입니다.  

뒤에서 살펴볼 gaussian process에서 이 wide-sense stationarity(wss) 개념을 활용할 예정입니다.


## 함수해석학 (Functional Analysis)

앞으로 계속 등장하게 될 함수해석학의 기본 개념과 정리들을 차례대로 살펴보겠습니다.

### 벡터공간, 거리공간, 노름공간, 내적공간

(정의 1.8) **벡터공간(Vector Space)**
다음 8가지 조건을 만족하는 (1) 두 원소 간 덧셈, (2) 체(field) $F$ 중 임의의 스칼라와의 곱셈 연산에 대해 닫혀 있는 집합 $V$를  
$F$에 대한 벡터공간이라고 합니다.
1. (덧셈 결합법칙) $u + (v + w) = (u + v) + w$
3. (덧셈 항등원) $\exist 0 \text{ s.t. for } \forall v \in V, v + 0 = v$
4. (덧셈 역원) $\exist -v \text{ for } \forall v \in V \text{ s.t. } v + (-v) = 0$
2. (덧셈 교환법칙) $u + v = v + u$
5. (스칼라곱의 분배법칙 1) $c(x + y) = cx + cy$
6. (스칼라곱의 분배법칙 2) $(c_1 + c_2)x = c_1x + c_2x$
5. $a(bv) = (ab)v$
6. $1v = v$

우리가 자주 접하는 유클리드 공간 $\mathbb{R}^N$이나 특정 크기의 행렬 공간 $\mathcal{M}_{m \times n}$, 공집합이 아닌 집합 $S$에서 실수체와 같은 체 $F$로 가는 함수의 공간 $\mathcal{F}(S, F)$이 모두 위 조건을 만족합니다.  
사실 이 내용은 선형대수학 기초 중 기초이므로 익숙할 것입니다.

(정의 1.9) **거리공간(Metric Space)**  
$F$에 대한 벡터공간 $M$에 아래 조건을 만족하는 함수(즉, 거리함수(distance function)) $d : M \times M \rightarrow \mathbb{R}$가 정의되어 있다면  
해당 벡터공간을 거리공간이라고 합니다.  
1. $d(x, x) = 0$
2. $x \neq y \Rightarrow d(x, y) > 0$
3. $d(x, y) = d(y, x)$
4. (삼각부등식) $d(x, z) \le d(x, y) + d(y, z)$

같은 벡터공간에 대해서도 다양한 거리함수를 채택할 수 있다는 이야기를 들어보셨을 겁니다.

(정의 1.10) **노름공간(Normed Vector Space)**  
$F$에 대한 벡터공간 $V$에 대해 거리함수의 조건에 아래 조건을 추가로 하나 더 만족하는 함수, 즉 노름(norm) $\lVert \centerdot \rVert$가 정의되어 있다면  
해당 벡터공간을 노름공간이라고 합니다.  
1. $\lVert \alpha x \rVert = \lvert \alpha \rvert \lVert x \rVert$

(정의 1.11) **내적공간(Inner Product Space)**  
$F$($\mathbb{R}$ 또는 $\mathbb{C}$ 중 하나)에 대한 벡터공간 $V$의 두 벡터를 받는 다음 조건을 만족하는 함수(즉, 내적) $\langle \centerdot, \centerdot \rang : V \times V \rightarrow F$가 정의되어 있다면  
해당 벡터공간을 내적공간이라고 합니다.  
1. (켤레대칭) $\lang x, y \rang = \overline{\lang y, x\rang}$
2. (선형성) $\lang ax + by, z\rang = a\lang x, z\rang + b\lang y, z\rang$
3. $\text{if } x \neq 0, \lang x, x\rang > 0$

내적이 정의되어 있으면 이를 이용하여 아래와 같이 필요한 5가지 조건을 모두 갖춘 노름을 만들 수 있습니다.  
$\lVert x \rVert = \sqrt{\lang x, x \rang}$  

따라서 내적공간은 자동으로 노름공간입니다.

### 힐베르트 공간 (Hilbert Space)

**정의**

(정의 1.13) **힐베르트 공간(Hilbert space)**  
내적공간 $V$가 완비성(completeness)을 갖추었다면 해당 공간은 힐베르트 공간입니다.

그렇다면 완비성이 무엇인지 알아야겠죠?

(정의 1.14) **완비성(completeness)**
어떤 집합 $V$로 만들 수 있는 모든 코시 수열이 해당 집합 $V$의 원소로 수렴하면, 집합 $V$는 완비성을 갖추었다고 말합니다.  
코시 수열(cauchy sequence)이란, 유한개의 원소를 제외한 나머지 사이의 거리가 (아무리 작은) 임의의 양수보다 작은 수열을 뜻합니다.

유리수의 집합 $\mathbb{Q}$는 완비성을 갖추었을까요?  
우리는 $\pi$가 무리수라는 것을 알고 있습니다.  
$\mathbb{Q}$로 아래와 같은 수열을 만들어볼까요?  
$a_n \equiv (\pi\text{의 소숫점 n번째 자리까지 나타낸 유한소수}) (n \in \mathbb{N})$  
그렇다면, 이 수열은 분명 $\mathbb{Q}$의 원소로 이루어진 수열(정확히는 코시 수열)인데,  
정작 그 수렴값인 $\pi$는 $\mathbb{Q}$에 없습니다.  
결국 $\mathbb{Q}$는 완비성을 갖추지 못한 것이죠.

대수학에서는 ("실수의 완비성 공리")공리를 써서 실수집합 $\mathbb{R}$은 완비성을 갖추었다고 '정해놓았다'고 합니다.

완비성은 '빈 구멍 없이 꽉 막힌' 이미지를 떠올리면 직관적으로 이해할 수 있습니다.  
수직선상에서 유리수의 집합은 중간중간 무리수로 구멍이 나 있지만,  
실수와 같은 경우엔 (공리상) 그럴 수 없죠.

내적공간 중 '빈 구멍 없이 꽉 막힌' 공간을 힐베르트 공간이라고 한다는 것만 기억해둡시다.  
대수학적으로 엄밀한 증명을 할 것이 아니기 때문에 힐베르트 공간이라는 말을 보면 '내적이 정의되어 있구나' 정도만 떠올려도 될 것 같습니다.

**예시**

앞으로 자주 보게 될 몇몇 힐베르트 공간을 간단히 살펴봅시다.

**$l^2$ 공간**

(정의 1.15) **$l^p$ 공간**  
다음을 만족하는 모든 수열의 집합을 $l^p$ 공간이라고 부른다. ($0 < p < \infty$)  
$\sum_{n} \lvert x_n \rvert^p < \infty$  

$l^p$ 공간은 노름이 정의되는 노름공간입니다.  
워낙 유명한 $l^p$ 노름이니, 아래 형태를 적어두겠습니다.  
$\lVert x \rVert _p = (\sum_{n} \lvert x_n \rvert^p)^{1 / p}$  

$p = 2$일 때, 즉 $l^2$ 공간은 아래와 같은 내적이 정의된 힐베르트 공간입니다.  
(사실 $p \neq 2$일 때에는 내적이 정의되지 않습니다. [귀류법을 이용한 증명](http://mathonline.wikidot.com/proof-that-p-when-p-2-is-an-inner-product-space)도 찾아볼 수 있습니다.)  
$\lang x, y \rang = \sum_{n} \overline{x_n}y_n$

$l^2$의 완비성 증명을 공부하지는 않겠습니다.

**$L^2$ 공간**

(정의 1.16) **$L^p$ 공간**  
다음을 만족하는 모든 함수 $f : S \rightarrow \mathbb{R} \text{ or } \mathbb{C}$의 집합을 $L^p$ 공간이라고 부른다. ($1 \le p < \infty$)  
$\int_{S} \lvert f \rvert^p d\mu < \infty$  
여기에서 $\mu$는 $f$의 정의역 $S$에 대해 정의된 측도입니다.

마찬가지로 이중 $L^2$ 공간만이 내적이 정의될 수 있는 힐베르트 공간입니다.  
내적은 아래와 같습니다.  
$\lang f, g \rang = \int_{S} f(x)\overline{g(x)}d\mu(x)$

추가적으로로 $p = \infty$일 때의 경우가 뒤에서 잠시 등장해서, 뜻만 간단히 살펴보고 넘어가겠습니다.  
(물론 $L^\infty$ 공간은 힐베르트 공간이 아닌 노름공간입니다.)

$p \rightarrow \infty$하면서 $L^p$ 노름은 아래와 같은 '본질적 상한(essential supremum)'의 형태를 띈다고 합니다.  
$\lVert f \rVert = \text{ess sup}_{x \in S} \lvert f(x) \rvert$  
본질적 상한 $\alpha$이란, $\lvert f(x^*) \rvert > \alpha$를 만족하는 $\alpha$의 집합의 측도가 0이 되는 값을 뜻합니다.  
그러니까 '거의(사실상) 상한'이라는 것이죠.

이러한 본질적 상한이 정의되는 모든 함수의 집합을 $L^\infty$ 공간이라고 한다고 합니다.  
뒤에 한 번 등장하니 이해만 해두도록 하죠.

### 커널 (Kernel)

**정의**

강의에서는 커널에 대해 다른 정의를 내렸지만, 정리본에서는 일반적으로 사용되는 커널의 정의부터 이야기해보도록 하겠습니다.

(정의 1.17) **커널(Kernel)**  
공집합이 아닌 어떤 집합 $\mathcal{X}$에 대한 함수 $k : \mathcal{X} \times \mathcal{X} \rightarrow \mathbb{R}$를 커널 또는 커널 함수라고 부른다.

간단하죠? 내적공간에서 내적이 커널의 대표적인 예시가 되겠죠? 이어서 개념을 하나 더 정의하겠습니다.

(정의 1.18) **그람 행렬(Gram matrix)**  
커널 $k : \mathcal{X} \times \mathcal{X} \rightarrow \mathbb{R}$과 $\mathcal{X}$에서 뽑은 $n$개의 원소 $\mathcal{C} = \lbrace x_1, x_2, ..., x_n \rbrace$에 대해  
$K_{ij} = k(x_i, x_j)$를 만족하는 $n \times n$의 정방행렬을 뜻합니다.

*선형대수학에서 그람 행렬은 사실 $k$가 내적일 때를 의미하지만, textbook의 정의를 따르기 위해 불가피하게 용어를 abuse하게 됩니다.

(정의 1.19) **적분변환 연산자(Integral Transform Operator)**  
커널 $k : \mathcal{X} \times \mathcal{X} \rightarrow \mathbb{R}$에 대해 함수 $f : \mathcal{X} \rightarrow \mathbb{R}$를 다음을 만족하는 함수 $T_kf : \mathcal{X} \rightarrow \mathbb{R}$로 변환해주는 연산자 $T_k$를 적분변환 연산자라고 부릅니다.
$$(T_kf)(x) : \mathcal{X} \rightarrow \mathbb{R} = \int_{\mathcal{X}}k(x, x')f(x')d\mu(x')$$

위에서 정의한 적분변환 연산자는 함수를 다른 함수로 바꿔주는 연산자(즉 함수)입니다.  
커널이 정의되면 해당 커널에 대한 적분변환 연산자도 자동으로 정의가 되는 것이죠.  
이 개념을 정의한 이유는 뒤에서 알게 될 것입니다.

**PSD(Positive SemiDefinite) 커널**

앞에서 살펴보았든 커널의 정의는 정말 넓습니다. 하지만 그 중 우리가 관심이 있는 커널은 바로 PSD 커널입니다.  
커널이 PSD라는 말의 뜻은 다음과 같습니다.

(정의 1.20) **PSD 커널**  
임의의 $\mathcal{C} = \lbrace x_1, x_2, ..., x_n \rbrace \subset \mathcal{X}$과 $c = (c_1, c_2, ..., c_n)' \in \mathbb{R}^n$에 대해 다음을 만족하는 대칭(symmetric) 커널 $k : \mathcal{X} \times \mathcal{X} \rightarrow \mathbb{R}$를 PSD(Positive Semidefinite) 커널이라고 합니다.  
$$ 
\sum_{i=1}^n \sum_{j=1}^n c_ic_jK(x_i, x_j) \ge 0 \\
$$

*여기서 대칭이란 $K(x_i, x_j) = K(x_j, x_i)$를 뜻합니다.

위 조건식을 자세히 보면 일종의 이차형식(quadratic form)으로 되어있는 것을 살펴볼 수 있습니다.  
$K$를 커널함수의 그람 행렬이라고 하면 $ \sum_{i=1}^n \sum_{j=1}^n c_ic_jK(x_i, x_j) = c^TKc $으로 표현할 수 있죠.  
따라서 아래 정리가 성립합니다.

(정리 1.1) **그람 행렬의 부호와 커널의 부호**  
커널 $k$가 PSD 커널이다. $\Leftrightarrow$ 임의의 $\mathcal{C} = \lbrace x_1, x_2, ..., x_n \rbrace \subset \mathcal{X}$에 대한 $k$의 그람 행렬 $K$가 PSD이다.

> ❓ **참고 : PSD 커널의 다른 정의(Mercer's condition)**  
> 강의에서는 PSD 커널이 만족해야 하는 조건을 실수 벡터가 아닌 $L^2$ 함수 $f$로 정의합니다.  
> $$\int k(x, x')f(x)f(x')d\mu(x)d\mu(x') \ge 0 \text{ for } \forall f \in L^2$$ 
> 이 조건을 만족하는 커널 $k$에 대해 "Mercer's condition을 충족했다"라고 표현합니다.  
> Mercer's condition과 (정의 1.19)의 조건이 동치임은 Mercer, Moore 등의 수학자가 밝혀놓았으니 받아들이기로 합니다.  

### 고유함수(eigenfunction)과 고윳값(eigenvalue), Mercer의 정리

**고유함수와 고윳값**

선형대수학에서 행렬이 곧 선형 사상(mapping)임을 배우고, 행렬로부터 고유벡터(eigenvector)와 고윳값(eigenvalue)를 구하는 연습을 해보셨을 것입니다.   
커널 $k$의 적분변환 연산자도 일종의 함수, 즉 사상이라고 했습니다. (정의 1.19)를 잘 살펴보면 선형 사상임을 알 수 있습니다.  
그래서 마찬가지로 적분변환 연산자에 대한 고유함수와 고윳값을 정의할 수 있습니다.

(정의 1.21) **고유함수, 고윳값**  
커널 $k : \mathcal{X} \times \mathcal{X} \rightarrow \mathbb{R}$와 $k$에서 도출한 적분변환 연산자 $T_k$와 어떤 함수 $\phi : \mathcal{X} \rightarrow \mathbb{R}$가 다음 조건을 만족시키면   
함수 $\phi$를 커널 $k$ 또는 연산자 $T_k$의 고유함수(eigenfunction), $\lambda$를 고윳값(eigenvalue)라고 부른다.
$$
T_k\phi = \lambda\phi, \text{ thus } \int_{\mathcal{X}}k(x, x')f(x')d\mu(x') = \lambda\phi(x) \text{ for } \forall x \in \mathcal{X}
$$

정의가 아주 익숙한 형태입니다. 행렬에서 고유벡터를 정의하는 식 $Ax = \lambda x$와 비슷하죠?

**Mercer의 정리**

선형대수학 공부할 때를 떠올려보면, 고유벡터와 고윳값을 열심히 찾은 이유는   
결국 행렬의 대각화 가부를 따지고 가능한 경우 행렬을 대각화하기 위함이었습니다. 기억나시나요?  
행렬이 대각화 가능하다면, 행렬 $A$의 고윳값 $\lambda _ i$와 고유벡터 $v_i$를 찾아 $A = P\Lambda P^t = \sum_{i}\lambda _i v_i v_i^T$와 같이 나타냈습니다.  
(즉, $Ax = \sum_{i}\lambda _i v_i \lang v_i, x \rang$)  


마찬가지로 적분변환 연산자 $T_k$를 고유함수와 고윳값을 이용해 분해해보고자 합니다.  
이때 꼭 알아야 할 정리가 Mercer의 정리입니다.  

Mercer's theorem은 
1. 연산자를 분해할 수 있는 충분조건을 제시하고
2. 이로써 분해된 연산자의 형태를 제시합니다.

(정리 1.2) **Mercer의 정리**  
유한 측도 $\mu$가 정의된 measurable space $(\mathcal{X}, \mu)$와 $\kappa(x) \equiv k(x, x) \in L^\infty$인 커널 $k : \mathcal{X} \rightarrow \mathbb{R}$에 대해   
조건 : $k$의 적분변환 연산자 $T_k : L^2 \rightarrow L^2$가 정의되고 $k$가 PSD 커널이면,  
결과 : 다음 1 ~ 3까지 성립한다.

1. (고유함수의 직교성) $T_k$의 고유함수로 된 $L^2$ 공간의 기저를 만들 수 있다.
2. (커널의 대각화가능성) $K(x, x') = \sum_{i} \lambda _i \phi _i(x)\phi _i(x')$로 나타낼 수 있으며, 이 급수는 (일정 조건 하에) 절대수렴한다.
3. (고윳값의 절대수렴) 고윳값 수열 $\lbrace \lambda _i \rbrace _{i = 1}^{\infty}$은 수렴한다.

여기 등장한 $L^2$, $L^\infty$ 공간은 증명의 technical한 이유로 있는 것이고,  
핵심만 다시 한 번 짚어보겠습니다.

> 핵심 : $k$가 PSD 커널이면 $k$를 $T_k$의 고윳값과 고유벡터로 나타낼 수 있다.

그런 의미에서 Mercer의 정리는 선형대수학에서의 고윳값분해(eigendecomposition)과 맞닿아있다고 할 수 있습니다.

다만, 의아할 수 있는 점으로는 왜 $T_k$의 고유함수를 구했는데 난데없이 $T_k$가 아닌 $k$가 분해되었냐는 점이 있겠네요.  
수학적으로 엄밀하지는 않지만, 직관적으로 그 이유를 살펴보겠습니다.

PSD 커널 $k$에 대한 $T_k$을 '대각화'해보는 것입니다.

$$
T_k(\cdot) = \sum_{i}\lambda _i \phi _ i \lang \phi _ i, \cdot \rang \\
(T_k(f)) = \sum_{i}\lambda _i \phi _ i \lang \phi _ i, f \rang \\
(T_k(f))(x) = \sum_{i}\lambda _i \lbrace\int_{\mathcal{X}}\phi _ i(x')f(x')d\mu(x')\rbrace \phi _ i(x) \\
(T_k(f))(x) =  \int_{\mathcal{X}} \lbrace \sum_{i} \lambda _i \phi _ i(x)\phi _ i(x') \rbrace f(x')d\mu(x')
$$

맨 마지막 줄을 살펴보면 $T_k$의 정의에 따라 중괄호 부분이 바로 커널 $k(x, x')이 들어갈 자리가 됨을 알 수 있습니다.  
$k(x, x') = \sum_{i} \lambda _i \phi _ i(x)\phi _ i(x')$  
이로써 Mercer의 정리 2번에 등장하는 꼴이 됩니다.  
이로써 $T_k$의 고유함수가 왜 $k$를 표현하는 데 사용되는지 '대충은' 알 수 있겠네요.

### 넓은 의미의 커널, 좁은 의미의 커널

Mercer의 정리를 살펴보았으므로 이제 드디어 강의에서 제시하는 (좁은 의미의) 커널에 대해 살펴볼 수 있습니다.

(정의 1.22) **(좁은 의미의) 커널**  
공집합이 아닌 어떤 집합 $\mathcal{X}$에 대한 어떤 함수 $k : \mathcal{X} \times \mathcal{X} \rightarrow \mathbb{R}$에 대해,  
다음을 만족하는 어떤 힐베르트 공간 $\mathcal{H}$에 대한 사상(함수) $\phi : \mathcal{X} \rightarrow \mathcal{H}$가 존재한다면  
f를 커널 혹은 커널 함수라고 부른다.  
$k(x, x') = \lang \phi(x), \phi(x') \rang$

찬찬히 살펴보면, 어떤 집합  $\mathcal{X}$로부터 두 개의 원소를 받아 실수를 돌려주는 함수가  
마치 두 원소를 어떤 힐베르트 공간으로 보내 내적한 결과로 해석될 수 있다면  
그 함수를 (좁은 의미의) 커널 함수라고 부르겠다는 뜻이라는 것을 알 수 있습니다.

(참고로, $\mathcal{X}$에는 공집합이 아니라는 조건 외에는 별다른 조건이 없다는 것을 확인하세요.)

**예시**

예시가 없으면 이해하기 힘든 내용이니 예시를 몇 개 들고 와 봅시다.

*예 1. 다항 커널*

(정의 1.18) **다항 커널(Polynomial kernel)**  
$K(x, x') = (x^Ty +\gamma)^n, x, y$

이 형태만 보아서는 이 함수가 커널의 자격을 갖추었는지 확인하기 어렵습니다.  
[일반적인 경우에 대한 증명](https://en.wikipedia.org/wiki/Polynomial_kernel#definition)이 궁금할 경우 링크를 참조하고,  
간단히 $\gamma = 0, n = 2$일 때를 살펴봅시다.

$$
k(x, y) = (x^Ty)^2 = (\sum_{i = 1}^n x_iy_i)^2 \\
= \sum_{i = 1}^n (x_i^2)(y_i^2) + 2\sum_{i = 1}^n\sum_{j = 1}^{i - 1}(x_iy_i)(x_jy_j) \\
= \sum_{i = 1}^n (x_i^2)(y_i^2) + \sum_{i = 1}^n\sum_{j = 1}^{i - 1}(\sqrt{2}x_ix_j)(\sqrt{2}y_iy_j) \\
\text{Thus, } \phi(x) = (x_i)_{i = 1}^{n} \odot (\sqrt{2}x_ix_j)_{i < j}^{n} = (x_1, x_2, ..., x_n, \sqrt{2}x_1x_2, \sqrt{2}x_1x_3, ..., \sqrt{2}x_{n - 1}x_n)
$$
여기서 $\odot$은 두 벡터를 이어붙여준다는 의미로 사용하였습니다.

즉, 연산 자체는 꽤 간단해보이는 다항 커널은 사실 $n$차원 벡터를 훨씬 더 높은 차원의 힐베르트 공간으로 옮겨 내적하는 것과 동일한 효과를 내고 있다는 것이죠.  
따라서 이 함수는 커널이라고 볼 수 있습니다.

*예 2 가우시안 커널 (또는 RBF 커널)*

(정의 1.19) **RBF 커널(Radial basis function kernel)**  
$K(x, x') = \exp(-{{\lVert x - x' \rVert}^2\over{2\sigma ^ 2}})$

이번에는 이 함수가 커널인지 포착하는 게 더 어렵습니다. $\sigma = 1$로 두고 한번 살펴보겠습니다.

$$
k(x, y) = \exp(-{{\lVert x - x' \rVert}^2\over{2}}) \\
\text{Since } {\lVert x - x' \rVert}^2 = \lang x - x', x - x'\rang = \lang x, x\rang + \lang x', x'\rang + 2\lang x, x'\rang = {\lVert x \rVert}^2 +{\lVert x' \rVert}^2 + 2 x^Tx', \\
k(x, y) = \exp(x^Tx')\exp(-{1\over2}{\lVert x \rVert}^2)\exp(-{1\over2}{\lVert x' \rVert}^2) \\
= [\sum_{j=0}^{\infty}{(x^Tx')^j \over j!}]\exp(-{1\over2}{\lVert x \rVert}^2)\exp(-{1\over2}{\lVert x' \rVert}^2) \text{ (Applied Taylor's Expansion)}\\
= [\sum_{j=0}^{\infty} {1 \over j!}\sum_{\Sigma n_i = j} {j \choose n_1, n_2, ..., n_k}\prod_{i = 1}^k x_ix'_i]\exp(-{1\over2}{\lVert x \rVert}^2)\exp(-{1\over2}{\lVert x' \rVert}^2) \text{ (Applied Multinomial Expansion)}\\
= \sum_{j=0}^{\infty}\sum_{\Sigma n_i = j}\exp(-{1\over2}{\lVert x \rVert}^2){x_1^{n_1}x_2^{n_2}...x_k^{n_k} \over \sqrt{n_1!n_2!...n_k!}}\exp(-{1\over2}{\lVert x' \rVert}^2){{x'}_1^{n_1}{x'}_2^{n_2}...{x'}_k^{n_k} \over \sqrt{n_1!n_2!...n_k!}} \\
\text{Thus, } \phi(x) = \exp(-{1\over2}{\lVert x \rVert}^2)[({x_1^{n_1}x_2^{n_2}...x_k^{n_k} \over \sqrt{n_1!n_2!...n_k!}})_{\Sigma n_i = 0} \odot ({x_1^{n_1}x_2^{n_2}...x_k^{n_k} \over \sqrt{n_1!n_2!...n_k!}})_{\Sigma n_i = 1} \odot ...]
$$

RBF 커널은 $k$차원(유한차원)의 벡터를 무한차원의 힐베르트 공간으로 보냅니다.  
$\phi$ 함수를 보면 벡터가 끊임없이 이어지는 것을 볼 수 있습니다.

**성질**

(정리 1.3) **커널의 합, 커널의 곱**  
두 커널함수 $f, g : \mathcal{X} \rightarrow \mathbb{R}$에 대하여 $f + g$와 $fg$는 모두 커널이다.  

직관: 덧셈의 경우는 직관적입니다. 애초에 내적의 합은 합의 내적으로 바꿀 수 있는 게 내적의 정의상 성질이니까요!  
곱셈의 경우는 더 복잡합니다. 내적의 곱은 곱의 내적으로 바꿀 수 없으니까요.  
두 커널함수의 공역이 되는 힐베르트 공간이 $\mathbb{R}^N$ 공간인 경우를 예시로 들어볼까요?  
(그렇다면 $\mathbb{R}^N$ 공간에서 정의된 내적인 $\lang x, y \rang = \sum_{i = 1}^N x_iy_i$을 쓰면 되겠죠?)  

$$
f(x, x')g(x, x) = \lang \phi^1(x) , \phi^1(x') \rang \lang \phi^2(x) , \phi^2(x') \rang \\
= (\sum_{i = 1}^N\phi^1_i(x)\phi^1_i(x'))(\sum_{j = 1}^N\phi^2_j(x)\phi^2_j(x')) \\
= \sum_{i, j}(\phi^1_i(x)\phi^2_j(x))(\phi^1_i(x')\phi^2_j(x')) \\
\text{Thus, } \phi(x) = (\phi^1_i(x)\phi^2_j(x))_{i, j}
$$

위와 같이 곱셈의 교환법칙을 이용하여 새로운 $\phi$ 함수를 구성해줄 수 있다는 느낌만 이해하면 될 것 같습니다.

(정리 1.4) **$l^2$ 수열로 만든 커널**  
$\forall x \in \mathcal{X}$에 대해 $\lbrace\phi_1(x), \phi_2(x), \phi_3(x), ...\rbrace \in l^2$이도록 정의된 $N (N \le \infty)$개의 $\phi_i : \mathcal{X} \rightarrow \mathbb{R}$이 있다.  
함수 $\phi : \mathcal{X} \rightarrow \mathbb{R}^N = (\phi_1(x), \phi_2(x), \phi_3(x), ...)'$로 정의하면,  
함수 $K(x, x') = \sum_{i = 1}^{N} \phi _i(x)\phi _i(x')$는 커널함수이다.

거창하게 적어두었지만 증명이 따로 필요없는 당연한 명제입니다.  
다만, 왜 굳이 $l^2$ 공간 내의 수열만을 활용해야 하는지에 대한 의문이 들 수 있습니다.  
만약 $l^2$ 공간 외의 수열을 활용한다면, $K(x, x) =  \sum_{i = 1}^{N} \lbrace \phi _i(x) \rbrace ^ 2 = \infty$임을 확인할 수 있습니다.  
이런 결과를 원치 않기 때문에 $l^2$ 공간의 수열로 제한해준 것입니다.

**좁은 의미의 커널과 PSD 커널의 관계**

이제 좁은 의미의 커널과 넓은 의미의 커널 사이 논리적 관계를 살펴보겠습니다.

(정리 1.5) **Mercer 따름정리**  
어떤 (넓은 의미의) 커널 $k$가 PSD 커널이면 커널 $k$는 좁은 의미의 커널이기도 하다. (즉, $\phi$ 함수가 존재한다.)  
역으로, 모든 (좁은 의미의) 커널은 PSD 커널이다.

증명:  
$\rightarrow$ 방향 증명은 Mercer의 정리 결과 2번으로 알 수 있습니다.  
$K(x, x') = \sum_{i} \lambda _i \phi _i(x)\phi _i(x')$이므로 $\phi(x) = (\sqrt{\lambda _i}\phi _i(x))_{i = 1}$로 정의하면 좁은 의미의 커널 정의를 충족할 수 있겠네요.  
$\leftarrow$은 그람 행렬과 (넓은 의미의) 커널 간 관계를 밝힌 (정리 1.1)을 이용할 것입니다.  
내적으로 된 커널의 그람 행렬 $G$는 항상 PSD 행렬입니다. 왜냐하면,  
$$
v^T G v = \sum_{i, j} v_i v_j \lang \phi(x_i), \phi(x_j) \rang = \sum_{i, j} \lang v_i\phi(x_i), v_j\phi(x_j)\rang = \lang \sum_{i} v_i\phi(x_i), \sum_{j} v_j\phi(x_j)\rang = \lVert \sum_{i} v_i\phi(x_i) \rVert \ge 0.
$$
(정리 1.1)에 따라 좁은 의미의 커널은 어떤 경우에도 PSD 그람 행렬을 갖기 때문에 PSD 커널입니다. [끝]

이로써 좁은 의미의 커널은 PSD 커널과 같은 말이 됐습니다.  
앞으로는 'PSD 커널'이라는 말을 쓰도록 하겠습니다.