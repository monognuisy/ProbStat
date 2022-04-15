---
marp: true
inlineSVG: true
theme: gaia
_class: lead
paginate: true
---

<style>
  @import url('https://cdn.jsdelivr.net/gh/orioncactus/pretendard/dist/web/static/pretendard.css');

  section {
    background-color: #fff;
    font-family: Pretendard;
    letter-spacing: 0em;
    color: #333;
  }

  p, li {
    font-size: 0.8em;
  }

  figcaption {
    font-size: 0.6em;
  }

  .katex {
    font-size: 1.1em;
  }

  code {
    background-color: #eee;
    color: #444;
    border-radius: 0.5em;
  }

  img[alt$=">"] {
    float: right;
  }

  img[alt$="<"] {
    float: left;
  }
</style>

# 확률과 통계 HW 3

##### Relations between Poisson & Exponential Dist.

<br/>

2021031685 유성민

---

## Poisson Modeling

##### Designing Poisson Distribution

$X$를 성공확률 $p$인 Bernoulli 시행에서의 성공 횟수라고 하면, $X \sim \mathrm{B}(n,p)$이다.

여기서 $n = 1000$, $p = 0.005$로 설정하면 $X$의 기댓값 $\lambda$는 다음과 같다.

$$
  \lambda = np = 5
$$

포아송 분포는 이항 분포에서 $n \to \infty$일 때 얻을 수 있으므로, $X$는 평균이 $\lambda$인 포아송 분포를 따를 것이라고 기대할 수 있다.

---

## Poisson Modeling

##### Implementation through Python

- $p = 0.005$인 베르누이 시행을 위하여 $[1, 200]$ 구간의 random한 정수를 `randint()`함수를 이용하여 uniformly 생성하고, 그 정수가 10일 때만 `True`를 반환하게 한다.
- $k$번 성공할 횟수를 저장하는 길이 $n = 1000$의 list인 `PoissonRVList`를 만든다.

###### Trial

1. $n = 1000$번의 베르누이 시행을 통해, 성공(`return True`)한 횟수($k$)를 센다.
2. `PoissonRVList[k]`에 1을 더한다.
3. 이를 $m = 1000$번 반복하여 충분히 list에 정보를 기록한다.

---

## Poisson Modeling

##### Simulation Result

`PoissonRVList`에서 성공 횟수가 30 이하인 경우만 히스토그램으로 나타내면 다음과 같다.

<div style="display:flex; justify-content: center; margin: 0">
<figure style="display:flex; flex-direction: column; align-items: center;">
<img src="./image/PoissonSimulation.svg" width="500">
<figcaption>Fig 1. Histogram of Simulation</figcaption>
</figure>
<figure style="display:flex; flex-direction: column; align-items: center;">
<img src="./image/PoissonSimulationPlot.svg" width="500">
<figcaption>Fig 2. Normalized Histogram & Plot</figcaption>
</figure>
</div>

---

## Poisson Modeling

##### Simulation Result (Cont.)

