# CHAPTER 1. Elementary of mathematics


## Set Theory (집합론)

(익숙한 내용이라 생략)


## Measure Theory (측도론)

직관적인 개념으로서 측도(measure)란 일정 규칙에 따라 **주어진 집합에 숫자를 부여하는 함수**입니다.  
예를 들어, 아래와 같이 정의한 집합 $S$에 대한 셈측도(counting measure)는 측도입니다.

(정의 1.1) **셈측도(counting measure)**  
$ \mu = \left\{\begin{matrix} n(S) (S\text{ is finite}) \\ \infty (S\text{ is infinite}) \end{matrix}\right.  $

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
$\{X_t(w) : \Omega \rightarrow S | t \in T \}$  
각 확률변수의 공역인 $S$는 state space라고 부릅니다.

*Indexed family란 index set의 원소를 index로 이용하여 번호를 붙인 원소들의 집합을 뜻합니다.  
**전통적으로 T에는 시간을 표현하는 실수 또는 자연수 집합을 사용하는 경우가 많지만, 시간 이외의 다른 뜻을 가진 다양한 index를 활용할 수도 있습니다.

> 🚧 주의!  
> 위 (정의 1.5)에서 sample space $\Omega$에 대해 오해하기 쉬운 부분이 있어서 예시를 통해 짚고 넘어가겠습니다.  
>   
> 앞/뒷면이 나올 확률이 1/2로 같은 동전을 무한 번 던지는 실험에 대해서 확률과정을 아래와 같이 정의합시다.  
> $\{X_t(w) : \Omega \rightarrow \{0, 1\} = (\text{if } t\text{th coin head then 1, else 0}) | t \in \mathbb{N} \}$  
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
$X_t : T \times \Omega \rightarrow \real$

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

- mean function: $m_X(t)\equiv E(X_t) = \left\{\begin{matrix}
\sum_{x}^{}xp_{x_{t}}(x) \text{ when discrete-valued} \\ \int xf_{x_{t}}(x)dx \text{ when continuous-valued}
\end{matrix}\right.$  
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