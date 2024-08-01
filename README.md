# Logical Inference and Knowledge Representation (論理推論と知識表現)
The notes below are a compilation of self-study based on the course materials that were provided, and may contain incorrect information that due to misunderstandings.

## Logical Inference
주어진 정보나 전제로 새로운 정보를 도출하는 과정

- 연역적 추론(Deductive Inference)
    - 일반적인 원칙이나 법칙을 바탕으로 결론을 도출. 전제가 참이라면 결론도 참이다.
    - (modus ponens, 긍정 논법, 함의 소거) $P \to Q | Q \to P .$ 그러므로 Q는 P이다.
    - (modus tollens, 부정 논법) $P \to Q | Q \to \neg P .$ 그러므로 Q는 P가 아니다.

- 귀납적 추론(Inductive Inference)
    - 관찰된 구체적 사례들로부터 일반적인 원리를 도출. 전제가 참인 것은 결론이 참일 확률이 높을 뿐 반드시 참일 필요는 없음.

- 비유적 추론 (Abductive Inference)
    - 증거를 바탕으로 현상에 대한 합리적 가설을 제시.

### 주요 개념
1. Premise
2. Conclusion
3. Logical Validity
4. Truth and Falsity

## Logical Foundation
### Logic symbols
- $\lnot$ \_ 또는 $\sim$ \_ : 부정(Negation), NOT
- \_ $\land$ \_ : 논리곱(Conjunction), AND
- \_ $\lor$ \_ : 논리합(Disjunction), OR
- \_ $\oplus$ \_ : 배타적 논리합(Exclusive OR, Either .. or ..), XOR
- $\to$ : 함축(Implication), 조건(Conditional), IMPLY
- $\leftrightarrow$ : 상호조건(Biconditional), IFF(if and only if)
- $\forall$ : For All
- $\exists$ : There exists
- $\exists !$ : There exists exactly one

### Propositional Logic (명제 논리)
- Propositional(命題): 참 또는 거짓인 문장.
    - $P \vee Q$: P 또는 Q
    - $P \wedge Q$: P 와 Q
    - $\neg P$: P 가 아님
    - 카르노 맵으로 표현 가능.
- Logical Implicaiton (논리적 함의)
    - 다음과 같이 표현된다.
    - $\frac{P \quad P \rightarrow Q}{Q}$ (Modus pones)
    - $P \rightarrow Q \equiv \neg P \wedge Q$ 
        - means $(P$ implies(함의) $Q)$ equivalence $($ not $P$ or $Q)$
        - 여기서 $P$는 가설(Hypothesis) 또는 전제(Premise)이며, $Q$는 결론(Conclusion) 또는 결과(Consequence)이다.
        - 이 때 $P$와 $Q$ 사이의 인과관계(Causality)는 불요하다. $P \to Q$ 가 갖는 의미는 둘의 진리값에만 의존한다. 즉, 아래의 명제도 참이 된다.
            - 니가 교수면 나는 총장이다.
            - 내가 로또가 되면 니가 올림픽에서 금메달을 딴다.
- Logical Connectives
    - $P \leftrightarrow Q \equiv (P \rightarrow Q) \wedge (Q \rightarrow P)$: P와 Q는 서로 동치다. 
    - Logical and/or: $P \land Q \rightarrow P, P \rightarrow P \lor Q .$
    - Commutative(교환법칙): $P \lor Q \leftrightarrow Q \lor P, P \land Q \leftrightarrow Q \land P .$
    - Associative(결합법칙): $(P \lor Q) \lor R \leftrightarrow P \lor (Q \lor R), (P \land Q) \land R \leftrightarrow P \land (Q \land R) .$
    - Contraposition(반대조건): $(P \to Q) \leftrightarrow (\lnot Q \to \lnot P) .$
    - Double negation(이중부정): $\lnot \lnot P \leftrightarrow P .$
    - de Morgan's law:
        - $\lnot (P \lor Q) \leftrightarrow \lnot P \land \lnot Q .$
        - $\lnot (P \land Q) \leftrightarrow \lnot P \lor \lnot Q .$
    - Distributive law(분배법칙):
        - $P \lor (P \land Q) \leftrightarrow (P \lor Q) \land (P \lor Q) .$
        - $P \land (P \lor Q) \leftrightarrow (P \land Q) \lor (P \land Q) .$

#### Examples
1. 다음 문장은 명제인가?
    - 바둑이는 개다.
        - True. 명제이다.
    - 바둑이와 철수는 동물이다.
        - True. 명제이다.
    - 바둑이는 100살까지 산다.
        - False. 명제가 아니다.
    - 명제는 참 또는 거짓으로 평가될 수 있는 문장을 의미한다. "바둑이는 100살까지 산다" 라는 문장은 예측 또는 가정에 가까우므로, 현 시점에서 이를 참 또는 거짓으로 평가할 수는 없다.
2. 다음 문장을 논리식(論理式, Logical formulas)으로 표현하라.
    - 날이 맑고(P) 내가 돈이 있다면(Q) 나는 여행을 간다(R).
        - $P \land Q \to R .$
    - 날이 맑거나(P) 흐리면(S) 나는 우산을 쓰지 않는다(T: 우산을 쓴다).
        - $P \lor S \to \neg T .$
3. 다음 논리식을 해석하라.
    - P: 1분은 60초 이다.
    - Q: 1시간은 100분 이다.
    - R: 1시간은 3600초 이다.
    1. $Q \to P$
        - True
        - 함의에 인과관계는 불필요하기에 P의 진리값에 의해 전체 명제의 진리값이 결정된다. 즉, P의 "1분은 60초이다" 가 참이기 때문에 전체 명제의 진리값도 참이 된다.
        - 전제가 거짓이라면 결과에 상관없이 전체 명제는 참이 된다.
        - 전제가 참일 때 결과가 참이라면 전체 명제는 참이고, 결과가 거짓이라면 전체 명제는 거짓이다.
    2. $P \to Q \lor R$
        - True
        - 전제 $P$가 참인 상태에서, 결과 $Q$가 거짓이고 $R$이 참이므로, $Q$와 $R$의 논리합에 의해 참이 된다.
    3. $\neg P \land (Q \to R)$
        - False
        - $P$가 참이므로 $\lnot P$는 거짓이다.
        - $(Q \to R)$에서 $Q$가 거짓, $R$이 참이므로 이는 참이다.
        - 전체 명제는 $\lnot P$가 거짓이고 $(Q \to R)$가 참이므로, False 와 True의 논리곱에 의해 False가 된다.

4. 다음 논리식에 대한 진리표(真理値表, Truth table)를 작성하라.
    - $(\neg P \lor Q) \to R$

| $P$   | $Q$   | $R$   | $\lnot P$  | $\lnot P \lor Q$ | $\lnot P \lor Q \to R$ |
|-----|-----|-----|-----|--------|--------------|
| T   | T   | T   | F   | T      | T            |
| T   | T   | F   | F   | T      | F            |
| T   | F   | T   | F   | F      | T            |
| T   | F   | F   | F   | F      | T            |
| F   | T   | T   | T   | T      | T            |
| F   | T   | F   | T   | T      | F            |
| F   | F   | T   | T   | T      | T            |
| F   | F   | F   | T   | T      | F            |


### First-order Logic (1차 논리, 술어 논리)
- 상수(Constant term): $a, b, c, ...$
- 변수(Variable term)" $x, y, z, ...$
- 술어(Predicate): $p, q, r, ...$
- 리터럴(Literal): $p(a), \lnot q(b), p(x), q(y), ...$
    - $x$는 인간($p$): $p(x)$
    - $x$는 한국인($q$): $q(x)$
    - $x$가 한국인이면 $x$는 인간이다: $\forall x$ $[q(x) \to p(x)]$
- Quantifier(限量子, 한정사)
    - 변수의 범위를 지정한다.
    - $\forall$ (For all), $\exists$ (There exists)
        - 모든 인간은 죽는다:
            - $\forall x$ $[$ human($x$) $\to$ mortal($x$) $] .$
        - 어떤 새는 날지 않는다:
            - $\exists y$ $[$ bird($y$) $\land$ $\lnot$ fly($y$) $] .$
        - 모든 남성은 여성을 사랑한다:
            - $\forall x$ $[$ man($x$) $\to$ $\exists y$ $[$ woman($y$) $\land$ love($x, y$) $]$  $] .$
            - $\exists y$  $[$ woman($y$) $\land$ $\forall x$ $[$ man($x$) $\to$ love($x, y$) $]$  $] .$
            - 메모: 수강자가 모든 명제에 동의하지만은 않는다.
    - 변수 바인딩, 스코프와 자유변수
        - $\forall$ $[$ farmer($x$) $\land$ $\exists y$ $[$ donkey($y$) $\land$ own($x, y$) $]$ $\to$ beat($x, y$) $] .$
            - 메모: 왜 때리는지??
        - $\forall x [p(x)] \leftrightarrow \forall y [p(y)] .$
        - $\exists x [p(x)] \leftrightarrow \exists y [p(y)] .$
        - $\lnot \forall x [p(x)] \leftrightarrow \exists y [\lnot p(y)] .$
        - $\lnot \exists x [p(x)] \leftrightarrow \forall y [\lnot p(y)] .$
        - 예:
            - 모든 $x$는 동물(animal)이다.
                - $\forall x$ animal($x$) .
            - 어떤 $x$는 날 수 있다(fly).
                - $\exists x$ fly($x$) .
            - 모든 $x$들이 새(bird)라면, $x$는 날 수 있다.
                - $\forall x$ $($ bird($x$) $\to$ fly($x$) $)$
            - 어떤 $x$들이 펭귄(penguin)이라면, $x$는 수영할 수 있다(swim).
                - $\exists x$ $($ penguin($x$) $\land$ swim($x$) $)$
            - 모든 고양이들이(cat) 포획된 것은 아니다(captured).
                - $\lnot \forall x$ $($ cat($x$) $\to$ captured($x$) $)$
            - 어떤 고양이는 포획되었고 어떤 고양이는 포획되지 않았다.
                - $\exists x$ $($ cat($x$) $\land$ captured($x$) $)$ $\land$  $\exists y$ $($ cat($y$) $\land$ $\lnot$ captured($y$) $)$
            - 모든 날개(wing) 없는 포유류들(mammal)은 날 수 없다.
                - $\forall x$ $($ mammal($x$) $\land$ $\lnot$ wing($x$) $\to$ $\lnot$ fly($x$) $)$
            - 지느러미(fin)있는 어떤 포유류들은 수영할 수 있다.
                - $\exists x$ $($ mammal($x$) $\land$ fin($x$) $\to$ swim($x$) $)$
                - 지느러미 있는 어떤 포유류가 수영할 수 있다.
                    - $\exists x$ $($ mammal($x$) $\land$ fin($x$) $\land$ swim($x$) $)$

### Analytic Tableau
