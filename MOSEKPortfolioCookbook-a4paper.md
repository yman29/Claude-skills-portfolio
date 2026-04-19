

MOSEK Portfolio Optimization
## Cookbook
## Release 1.6.0
MOSEK ApS
## 05 November 2025

## Contents
## 1  Preface1
1.1  Purpose  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .1
1.2  Content  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .1
1.3  Online resources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .2
2  Markowitz portfolio optimization3
2.1  The mean–variance model  . . . . . . . . . . . . . . . . . . . . . . . . . .3
2.2  Constraints, modifications  . . . . . . . . . . . . . . . . . . . . . . . . . .6
2.3  Conic formulation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .8
2.4  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .9
3  Input data preparation15
3.1  Scenarios . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   15
3.2  Modeling the distribution of returns . . . . . . . . . . . . . . . . . . . . .   17
3.3  Extensions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   19
3.4  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   23
4  Dealing with estimation error26
4.1  Estimation of mean . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   26
4.2  Estimation of the covariance matrix . . . . . . . . . . . . . . . . . . . . .   29
4.3  Using constraints . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   31
4.4  Improve the optimization . . . . . . . . . . . . . . . . . . . . . . . . . . .   32
4.5  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   34
5  Factor models37
5.1  Definition  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   37
5.2  Classes of factor models  . . . . . . . . . . . . . . . . . . . . . . . . . . .   38
5.3  Portfolio optimization with factor model  . . . . . . . . . . . . . . . . . .   41
5.4  Shrinkage as factor model  . . . . . . . . . . . . . . . . . . . . . . . . . .   42
5.5  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   43
6  Transaction costs49
6.1  Variable transaction costs  . . . . . . . . . . . . . . . . . . . . . . . . . .   50
6.2  Fixed transaction costs . . . . . . . . . . . . . . . . . . . . . . . . . . . .   50
6.3  Market impact costs  . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   51
6.4  Cardinality constraints . . . . . . . . . . . . . . . . . . . . . . . . . . . .   52
6.5  Buy-in threshold  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   53
6.6  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   54
i

7  Benchmark relative portfolio optimization61
7.1  Active return  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   61
7.2  Factor model on active returns . . . . . . . . . . . . . . . . . . . . . . . .   62
7.3  Optimization  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   62
7.4  Extensions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   63
7.5  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   64
8  Other risk measures68
8.1  Deviation measures . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   69
8.2  Tail risk measures . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   72
8.3  Expected utility maximization . . . . . . . . . . . . . . . . . . . . . . . .   76
8.4  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   79
9  Risk budgeting83
9.1  Risk contribution . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   83
9.2  Risk budgeting portfolio  . . . . . . . . . . . . . . . . . . . . . . . . . . .   83
9.3  Risk budgeting with variance  . . . . . . . . . . . . . . . . . . . . . . . .   84
9.4  Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   86
10 Robust optimization90
10.1 Types of uncertainty  . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   90
10.2 Uncertainty in security returns . . . . . . . . . . . . . . . . . . . . . . . .   91
10.3 Uncertainty in the factor model . . . . . . . . . . . . . . . . . . . . . . .   91
10.4 Parameters  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   94
10.5 Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   96
11 Multi-period portfolio optimization99
11.1 Single-period model . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  100
11.2 Multi-period model . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  101
11.3 Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  103
12 Regression and regularization106
12.1 Linear regression  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  106
12.2 Regularization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  108
12.3 Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  110
## 13 Appendix114
13.1 Conic optimization refresher . . . . . . . . . . . . . . . . . . . . . . . . .  114
13.2 Mixed-integer models . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  120
13.3 Quadratic cones and riskless solution . . . . . . . . . . . . . . . . . . . .  122
13.4 Monte Carlo Optimization Selection (MCOS)  . . . . . . . . . . . . . . .  123
14 Notation and definitions125
14.1 Financial notations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  125
14.2 Mathematical notations  . . . . . . . . . . . . . . . . . . . . . . . . . . .  126
14.3 Abbreviations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  127
ii

## Bibliography128
MOSEK Portfolio Optimization Cookbook, Release 1.6.0, November 2025
©Copyright 2025 MOSEK ApS
iii

## Chapter 1
## Preface
## 1.1 Purpose
This book provides an introduction to the topic of portfolio optimization and discusses
several branches of practical interest from this broad subject.
We intended it to be a practical guide, a cookbook, that not only serves as a reference
but also supports the reader with practical implementation. We do not assume that the
reader is acquainted with portfolio optimization, thus the book can be used as a starting
point, while for the experienced reader it can serve as a review.
First we familiarize the reader with the basic concepts and the most relevant ap-
proaches in portfolio optimization, then we also present computational examples with
code to illustrate these concepts and to provide a basis for implementing more complex
and more specific cases. We aim to keep the discussion concise and self-contained, cov-
ering only the main ideas and tools, the most important pitfalls, both from theoretical
and from technical perspective. The reader is directed towards further reading in each
subject through references.
## 1.2 Content
Each of the chapters is organized around a specific subject:
•Sec. 2 is a general introduction, and is recommended to be read first to familiarize
with the problem formulation and notations used throughout this book. Here we
also present a code example showing how to useMOSEKto model the problem
and how to solve it.
•Sec. 3 summarizes concepts and pitfalls related to the preparation of raw data.
Here we discuss how to arrive at security returns data suitable for optimization,
starting from raw data that is commonly available on the internet. This chapter is
recommended as a second read.
•Each of the subsequent chapters are focusing on a specific topic: mitigating estima-
tion error, using factor models, modeling transaction costs, optimizing relative to
a benchmark, optimizing different risk measures, risk budgeting, robust optimiza-
tion, and finally the multiperiod portfolio optimization problem. These chapters
are independent and thus can be read in any order.
## 1

•The book assumes basic familiarity with conic optimization. Sec. 13.1 can be used
as a quick refresher in this topic. It shows how to convert traditional quadratic
optimization (QO) and quadratically constrained quadratic optimization (QCQO)
problems into equivalent quadratic conic optimization models, and what are the
advantages of this conversion. Then it briefly introduces other types of cones as
well.
1.3 Online resources
The code examples appearing in this cookbook are written using theMOSEKFusion
API for Python, and focus on the modeling part, omitting error handling, status checks,
logging and other technical facilities. The full technical documentation, as well as manuals
forMOSEKAPIs in other programming languages can be found at:
https://www.mosek.com/documentation
The notebooks with full executable code examples are available at GitHub:
https://github.com/MOSEK/PortfolioOptimization
VisitMOSEKat:
https://www.mosek.com
The cookbook, code examples, manuals for other APIs and other portfolio optimization
resources can be found at the webpage of this publication:
https://www.mosek.com/content/portfolio-optimization
## 2

## Chapter 2
Markowitz portfolio optimization
In this section we introduce the Markowitz model in portfolio optimization, and discuss
its different formulations and the most important input parameters.
2.1 The mean–variance model
Consider an investor who wishes to allocate capital among푁securities at time푡=  0
and hold them over a single period of time until푡=ℎ. We denote푝
## 0,푖
the (known) price
of security푖at the beginning of the investment period and푃
## ℎ,푖
the (random) price of
security푖at the end of the investment period푡=ℎ. Therate of returnof security푖over
periodℎis then modeled by the random variable푅
## 푖
## =푃
## ℎ,푖
## /푝
## 0,푖
−1, and its expected
value is denoted by휇
## 푖
## =E(푅
## 푖
). The risk-averse investor seeks to maximize the return
of the investment, while trying to keep the investmentrisk, i. e., the uncertainty of the
future security returns푅
## 푖
on an acceptable low level.
The part of investment risk called specific risk (the risk associated with each individual
security) can be reduced (for a fixed expected rate of return) through diversification,
which means the selection of multiple unrelated securities into a portfolio.
## 1
## Modern
Portfolio Theory formalized this process by using variance as a measure of portfolio risk,
and constructing a optimization problem.
Thus we make the investment decision at time푡= 0by specifying the푁-dimensional
decision vectorxcalledportfolio, where푥
## 푖
is the fraction of funds invested into security
푖. We can then express the random portfolio return as푅
x
## =
## ∑︀
## 푖
## 푥
## 푖
## 푅
## 푖
## =x
## T
푅, where푅
is the vector of security returns. The optimalxis given based on the following inputs of
the portfolio optimization problem:
•The expected portfolio return
## 휇
x
## =E(푅
x
## ) =x
## T
## E(푅) =x
## T
## 휇.
•The portfolio variance
## 휎
## 2
x
## = Var(푅
x
## ) =
## ∑︁
## 푖
## Cov(푅
## 푖
## ,푅
## 푗
## )푥
## 푖
## 푥
## 푗
## =x
## T
## Σx.
## 1
The other component of risk called systematic risk can only be reduced by decreasing the expected
return.
## 3

Here휇is the vector of expected returns,Σis the covariance matrix of returns, sum-
marizing the risks associated with the securities.  Note that the covariance matrix is
symmetric positive semidefinite by definition, and if we assume that none of the securi-
ties is redundant
## 2
, then it is positive definite. This can also be seen if we consider that
the portfolio variance must always be a positive number. After the above parameters the
problem is also referred to as mean–variance optimization (MVO). The choice of variance
as the risk measure results that MVO is aquadratic optimization(QO) problem.
## 3
Using these input parameters, the MVO problem seeks to select a portfolio of securities
xin such a way that it finds the optimal tradeoff between expected portfolio return and
portfolio risk. In other words it seeks to maximize the return while limiting the level of
risk, or it wants to minimize the risk while demanding at least a given level of return.
Thus portfolio optimization can be seen as a bi-criteria optimization problem.
2.1.1 Solution of the mean–variance model
To be able to solve the portfolio optimization problem, we have to assume that the investor
knows the value of the expected return vector휇and covariance matrixΣ. In practice it
is only possible to have estimates, which we will denote by휇andΣrespectively. (Details
on the properties of these estimates and ways to improve them will be the topic of Sec.
## 4.)
In the simplest form of the MVO problem only risky securities are considered. Also the
portfolio is fully invested with no initial holdings, implying the linear equality constraint
## ∑︀
## 푖
## 푥
## 푖
## =1
## T
x= 1, where1denotes a vector of ones.
We can formulate this portfolio optimization problem in three equivalent ways:
- Minimize the portfolio risk, with the constraint expressing a lower bound on the
portfolio return:
minimizex
## T
## Σx
subject to휇
## T
x≥푟
min
## ,
## 1
## T
x=   1.
## (2.1)
## Here푟
min
is the target expected return, which the investor wishes to reach. In this
problem the objective function is convex quadratic, all the constraints are linear,
thus it is a quadratic optimization (QO) problem. While QO problems are easy
to solve, this formulation is not ideal in practice because investors might prefer
specifying an upper bound on the portfolio risk instead of specifying a lower bound
on the expected portfolio return.
- Maximize the expected portfolio return, with the constraint expressing an upper
bound on the portfolio risk:
maximize휇
## T
x
subject tox
## T
## Σx≤훾
## 2
## ,
## 1
## T
x=   1.
## (2.2)
## 2
A security is redundant within the universe of securities in consideration, if there is areplicating
portfolio, i. e., a combination of other securities in the universe, that has the same properties. It means
that we can drop the redundant security from the universe without loss of opportunities for diversification.
Keeping it in the portfolio could cause the covariance matrixΣto be singular.
## 3
This was a reasonable choice from both the financial and the mathematical point of view, because
modern portfolio theory and the theory of quadratic optimization started to develop about the same
time in history, in the 1950s. However, the way we model risk can be different. See later in Sec. 8.
## 4

In this formulation it is possible to explicitly constrain the risk measure (the vari-
ance), which makes it more practical.  We can also add constraints on multiple
types of risk measures more easily. However, the problem in this form is not a QO
because of the quadratic constraint. We can reformulate it as a conic problem; see
## Sec. 2.3.
- Maximize the utility function of the investor:
maximize휇
## T
x−
## 훿
## 2
x
## T
## Σx
subject to1
## T
x=   1.
## (2.3)
In this case we construct the (concave) quadratic utility function휇
## T
x−
## 훿
## 2
x
## T
## Σxto
represent the risk-averse investor’s preferred tradeoff between portfolio return and
portfolio risk. This preference can be adjusted using therisk-aversion coefficient
훿. However this parameter might not have intuitive investment meaning for the
investor.
We get a variant of this optimization problem by using the standard deviation
instead of the variance:
maximize휇
## T
x−
## ̃
## 훿
## √
x
## T
## Σx
subject to1
## T
x=   1.
## (2.4)
This form is favorable because then the standard deviation penalty term will be of
the same scale as portfolio return.
Moreover, if we assume portfolio return to be normally distributed, then
## ̃
훿has a
more tangible meaning; it is the z-score
## 4
of portfolio return. Also, the objective
function will be the(1−훼)-quantile of portfolio return, which is the opposite of the
훼confidence levelvalue-at-risk(VaR). The number훼comes fromΦ(−
## ̃
## 훿) = 1−훼,
whereΦis the cumulative distribution function of the normal distribution.
We can see that for
## ̃
훿= 0we maximize expected portfolio return. Then by increas-
ing
## ̃
훿we put more and more weight on tail risk, i. e., we maximize a lower and lower
quantile of portfolio return. This makes selection of
## ̃
훿more intuitive in practice.
Note that computing quantiles is more complicated for other distributions, because
in general they are not determined by only mean and standard deviation.
These two problems will result in the same set of optimal solutions as the other two
formulations. They also allow an easy computation of the entire efficient frontier.
Maximizing problem (2.3) is again a QO, but problem (2.4) is not because of the
square root. This latter problem can be solved using conic reformulation, as we will
see in Sec. 2.3.
The optimal portfolioxcomputed by the Markowitz model isefficientin the sense
that there is no other portfolio giving a strictly higher return for the same amount of
risk or a strictly lower risk for the same amount of return. In other words an efficient
portfolio is Pareto optimal. The collection of such points form theefficient frontierin
mean return–variance space.
The above introduced simple formulations are trivial to solve. Through the method
of Lagrangian multipliers we can get analytical formulas, which involve휇andΣ
## −1
as
## 4
The z-score is the distance from the mean measured in units of standard deviation.
## 5

parameters. Thus the solution is simply to invert the covariance matrix (see e. g. in
[CJPT18]). This makes them useful as a demonstration example, but they have only
limited investment value.
2.2 Constraints, modifications
In investment practice additional constraints are essential, and it is common to add linear
equalities and inequalities, convex inequalities, and/or extra objective function terms to
the model, which represent various restrictions on the optimal security weights.
Constraints can reflect investment strategy or market outlook information, they can be
useful for imposing quality controls on the portfolio management process, or for control-
ling portfolio structure and avoiding inadvertent risk exposures. In these more realistic
use cases however, only numerical optimization algorithms are suitable for finding the
solution.
In the following, we discuss some of the constraints commonly added to portfolio
optimization problems.
2.2.1 Budget constraint
In general we can assume that we havex
## 0
fraction of initial holdings, and푥
f
## 0
fraction of
(risk-free) initial wealth to invest into risky securities. Then1
## T
x
## 0
## +푥
f
## 0
= 1is an initial
condition, meaning that both the risky and the risk-free securities take up some fraction
of the initial portfolio. After portfolio optimization, the portfolio composition changes,
but no cash is added to or taken out from the portfolio. Thus the condition
## 1
## T
x+푥
f
## = 1
## (2.5)
has to hold. For the differences
## ̃
x=x−x
## 0
and ̃푥
f
## =푥
f
## −푥
f
## 0
it follows that1
## T
## ̃
x+  ̃푥
f
## = 0
has to hold.
If we do not want to keep any wealth in the risk-free security, then in addition푥
f
must
be zero.
2.2.2 Diversification constraints
These constraints can help limit portfolio risk by limiting the exposure to individual
positions or industries, sectors.
For a single position, they can be given in the form
## 푙
## 푖
## ≤푥
## 푖
## ≤푢
## 푖
## .
For a group of securities such as an industry or sector, represented by the setℐthey will
be
## 푙
## 푖
## ≤
## ∑︁
## 푖∈ℐ
## 푥
## 푖
## ≤푢
## 푖
## .
We can also create a constraint that limits the total fraction of the푚largest investments
to at most푝. Based on Sec. 13.1.1 this is represented by the following set of constraints:
## 푚푡+1
## 푇
u≤푝,u+푡≥x,u≥0,
whereuand푡are new variables.
## 6

2.2.3 Leverage constraints
Componentwise short sale limit
The simplest form of leverage constraint is when we do not allow any short selling. This
is the long-only constraint stated as
x≥0.
We can allow some amount of short selling푠
## 푖
on security푖by stating
## 푥
## 푖
## ≥−푠
## 푖
## .
Total short sale limit
We can also bound the total short selling by the constraint
## ∑︁
## 푖
max(−푥
## 푖
## ,0)≤푆.
We can rewrite this as a set of linear constraints by modeling the maximum function
based on Sec. 13.1.1 using an auxiliary vectort
## −
## :
## 1
## T
t
## −
## ≤푆,t
## −
## ≥−x,t
## −
## ≥0.
Collateralization requirement
An interesting variant of this constraint is thecollateralization requirement, which limits
the total of short positions to a fraction of the total of long positions. We can model it
by introducing new variablesx
## +
andx
## −
for the long and short part ofx, based on Sec.
13.1.1. Then the collateralization requirement will be:
## ∑︁
## 푖
## 푥
## −
## 푖
## ≤푐
## ∑︁
## 푖
## 푥
## +
## 푖
## .
Leverage strategy
A leverage strategy is to do short selling, then use the proceeds to buy other securities.
We can express such a strategy in general using two constraints:
## •1
## T
x= 1,
## •
## ∑︀
## 푖
## |푥
## 푖
|≤푐or equivalently‖x‖
## 1
## ≤푐,
where푐= 1yields the long-only constraint and푐= 1.6means the 130/30 strategy.
The 1-norm constraint is nonlinear, but can be modeled as a linear constraint based on
## Sec. 13.1.1:−z≤x≤z,1
## T
z=푐.
## 7

2.2.4 Turnover constraints
The turnover constraint limits the total change in the portfolio positions, which can help
limiting e. g. taxes and cost of transactions.
## Supposex
## 0
is the initial holdings vector. Then we can write the turnover constraint
as
## ‖x−x
## 0
## ‖
## 1
## ≤푐.
This nonlinear expression can be modeled as linear constraint using Sec. 13.1.1.
2.2.5 Practical considerations
We can of course add many other constraints that might be imposed by regulations or
arise from specific investor preferences. As long as all of these are linear or conic, the
problem will not become significantly harder to solve. (See Sec. 13.1 for a summary on
conic constraints.)
However, we must not add too many constraints. Overconstraining a portfolio can
lead to infeasibility of the optimization problem, or even if there exists a solution, out-
of-sample performance of it could be poor.
Throughout this book the general notationx∈ℱwill indicate any further constraints
added to the problem, that are not relevant to the given example. Then we can write the
general MVO problem in the form
maximize휇
## T
x
subject tox
## T
## Σx≤훾
## 2
## ,
x∈ ℱ.
## (2.6)
2.3 Conic formulation
We have seen that some of the portfolio optimization problems in Sec. 2.1.1 are quadratic
optimization problems. Solving QO problems in their original form is popular and con-
sidered easy, because this model was studied starting from early in history (in the 1950s),
allowing it to become a well known and mature approach. However, more recent results
show us that conic optimization models can improve on QO models both in the theoretical
and in the practical sense. More on this in Sec. 13.1.2.
In this section we will show to convert problems (2.1)-(2.4) into conic form. Assuming
that the covariance matrix estimateΣis positive definite, it is possible to decompose it
asΣ=GG
## T
, whereG∈R
## 푁×푘
. We can do this for example by Cholesky decomposition,
see Sec. 13.1.1 for a list of other possibilities. An interesting approach in financial ap-
plications is thefactor model, which can have the advantage of having a direct financial
interpretation (see in Sec. 5).
Even if there are no redundant securities,Σcan be positive semidefinite if the number
of samples is lower than the number of securities. In this case the Cholesky decomposition
might not be computable.
## 5
We can then apply regularization techniques (e. g. shrinkage,
see in Sec. 4.2.1) to ensure positive definiteness. Otherwise if suitable linear returns data
## 5
The Cholesky decomposition is possible for positive semidefinite matrices, but software implemen-
tations might need positive definiteness depending on the algorithm used (e. g. Python numpy).
## 8

(see in Sec. 3) is available, then a centered and normalized data matrix can also serve as
matrixG.
Using the decomposition we can write the portfolio variance asx
## T
## Σx=x
## T
## GG
## T
x=
## ‖G
## T
x‖
## 2
## 2
. This leads to two different conic forms (see also in Sec. 13.1.1).
- Modeling with rotated quadratic cone:
We can directly model the squared norm constraint‖G
## T
x‖
## 2
## 2
## ≤훾
## 2
using the rotated
quadratic cone as(훾
## 2
## ,
## 1
## 2
## ,G
## T
x)∈ 풬
## 푘+2
r
. This will give us the conic equivalent of e.
g. problem (2.3):
maximize휇
## T
x
subject to(훾
## 2
## ,
## 1
## 2
## ,G
## T
x)∈ 풬
## 푘+2
r
## ,
## 1
## T
x=   1.
## (2.7)
- Modeling with quadratic cone:
We can also consider the equivalent norm constraint‖G
## T
x‖
## 2
≤훾instead of the
squared norm, and model it using the quadratic cone as(훾,G
## T
x)∈ 풬
## 푘+1
## . The
conic equivalent of problem (2.3) will then look like
maximize휇
## T
x
subject to(훾,G
## T
x)∈ 풬
## 푘+1
## ,
## 1
## T
x=   1.
## (2.8)
This way we can also model problem (2.4). We introduce the variable푠to represent
the upper bound of the portfolio standard deviation, and model the constraint
## ‖G
## T
x‖
## 2
≤푠using the quadratic cone as
maximize휇
## T
x−
## ̃
## 훿푠
subject to(푠,G
## T
x)∈ 풬
## 푘+1
## ,
## 1
## T
x=   1.
## (2.9)
While modeling problem (2.3) using the rotated quadratic cone might seem more
natural, it can also be reasonable to model it using the quadratic cone for the
benefits of the smaller scale and intuitive interpretation of
## ̃
훿. This is the same as
modeling of problem (2.4), which shows that conic optimization can also provide
efficient solution to problems that are inefficient to solve in their original form.
In general, transforming the optimization problem into the conic form has multiple
practical advantages. Solving the problem in this format will result in a more robust and
usually faster and more reliable solution process. Check Sec. 13.1.2 for details.
## 2.4 Example
We have seen how to transform a portfolio optimization problem into conic form. Now
we will present a detailed example inMOSEKFusion.  Assume that the input data
estimates휇andΣare given.  The latter is also positive definite.  For methods and
examples on how to obtain these see Sec. 3.
Suppose we would like to create a long only portfolio of eight stocks. Assume that we
receive the following variables:
## 9

# Expected returns and covariance matrix
m = np.array(
## [0.0720, 0.1552, 0.1754, 0.0898, 0.4290, 0.3929, 0.3217, 0.1838]
## )
S = np.array([
## [0.0946, 0.0374, 0.0349, 0.0348, 0.0542, 0.0368, 0.0321, 0.0327],
## [0.0374, 0.0775, 0.0387, 0.0367, 0.0382, 0.0363, 0.0356, 0.0342],
## [0.0349, 0.0387, 0.0624, 0.0336, 0.0395, 0.0369, 0.0338, 0.0243],
## [0.0348, 0.0367, 0.0336, 0.0682, 0.0402, 0.0335, 0.0436, 0.0371],
## [0.0542, 0.0382, 0.0395, 0.0402, 0.1724, 0.0789, 0.0700, 0.0501],
## [0.0368, 0.0363, 0.0369, 0.0335, 0.0789, 0.0909, 0.0536, 0.0449],
## [0.0321, 0.0356, 0.0338, 0.0436, 0.0700, 0.0536, 0.0965, 0.0442],
## [0.0327, 0.0342, 0.0243, 0.0371, 0.0501, 0.0449, 0.0442, 0.0816]
## ])
The similar magnitude and positivity of all the covariances suggests that the selected
securities are closely related. In Sec. 3.4.2 we will see that they are indeed from the same
market and that the data was collected from a highly bullish time period, resulting in the
large expected returns. Later in Sec. 5.5.1 we will analyze this covariance matrix more
thoroughly.
2.4.1 Maximizing return
We will solve problem (2.2) with an additional constraint to prevent short selling. We
specify a risk level of훾
## 2
=  0.05and assume that there are no transaction costs. The
optimization problem will then be
maximize휇
## T
x
subject tox
## T
## Σx≤훾
## 2
## ,
## 1
## T
x=   1,
x≥0.
## (2.10)
Recall that by the Cholesky decomposition we haveΣ=GG
## T
. Then we can model the
quadratic termx
## T
## Σx≤훾
## 2
using the rotated quadratic cone as(훾
## 2
## ,
## 1
## 2
## ,G
## T
x)∈풬
## 푁+2
r
, and
arrive at
maximize휇
## T
x
subject to
## (︀
## 훾
## 2
## ,
## 1
## 2
## ,G
## T
x
## )︀
## ∈ 풬
## 푁+2
r
## ,
## 1
## T
x=   1,
x≥0.
## (2.11)
In the code,Gwill be an input parameter, so we compute it first. We use the Python
packagenumpyfor this purpose, abbreviated here asnp.
N = m.shape[0]# Number of securities
gamma2 = 0.05# Risk limit
# Cholesky factor of S to use in conic risk constraint
G = np.linalg.cholesky(S)
Next we define the Fusion model for problem (2.11):
## 10

with Model("MarkowitzReturn") as M:
# Decision variable (fraction of holdings in each security)
# The variable x is the fraction of holdings in each security.
# x must be positive, this imposes the no short-selling constraint.
x = M.variable("x", N, Domain.greaterThan(0.0))
# Budget constraint
## M.constraint('budget', Expr.sum(x) == 1)
## # Objective
M.objective('obj', ObjectiveSense.Maximize, x.T @ m)
# Imposes a bound on the risk
M.constraint('risk', Expr.vstack(gamma2, 0.5, G.T @ x),
Domain.inRotatedQCone())
# Solve optimization
## M.solve()
returns = M.primalObjValue()
portfolio = x.level()
The resulting portfolio return is휇
## T
x= 0.2767and the portfolio composition isx=
## [0,0.0913,0.2691,0,0.0253,0.3216,0.1765,0.1162].
2.4.2 Efficient frontier
In this section we compute the full efficient frontier using the same input variables. This
is the easiest to do based on the formulation (2.3) by varying the delta parameter. We
also prevent short selling in this case and assume no transaction costs. The optimization
problem becomes
maximize휇
## T
x−
## ̃
## 훿
## √
x
## T
## Σx
subject to1
## T
x=   1,
x≥0.
## (2.12)
With the help of Cholesky decomposition, we can model the quadratic term
## √
x
## T
## Σx=
## √
x
## T
## GG
## T
x=‖G
## T
x‖
## 2
in the objective as a conic constraint.  Let us introduce the
variable푠and apply that‖G
## T
x‖
## 2
≤푠is equivalent to the quadratic cone membership
## (푠,G
## T
x)∈풬
## 푁+1
. Then the problem will take the form
maximize휇
## T
x−
## ̃
## 훿푠
subject to1
## T
x=   1,
x≥0,
## (푠,G
## T
x)∈ 풬
## 푁+1
## .
## (2.13)
First we compute the input variableG:
N = m.shape[0]# Number of securities
(continues on next page)
## 11

(continued from previous page)
# Cholesky factor of S to use in conic risk constraint
G = np.linalg.cholesky(S)
Next we define the Fusion model for problem (2.13):
with Model("MarkowitzFrontier") as M:
## # Variables
# The variable x is the fraction of holdings in each security.
# x must be positive, this imposes the no short-selling constraint.
x = M.variable("x", N, Domain.greaterThan(0.0))
# The variable s models the portfolio variance term in the objective.
s = M.variable("s", 1, Domain.unbounded())
# Budget constraint
## M.constraint('budget', Expr.sum(x) == 1)
# Objective (quadratic utility version)
delta = M.parameter()
M.objective('obj', ObjectiveSense.Maximize,
x.T @ m - delta * s)
# Conic constraint for the portfolio variance
M.constraint('risk', Expr.vstack(s, G.T @ x), Domain.inQCone())
Here we use a feature in Fusion that allows us to define model parameters. The line
delta = M.parameter()in the code does this.  Defining a parameter is ideal for the
computation of the efficient frontier, because it allows us to reuse an already existing
optimization model, by only changing its parameter value.
To do so, we define the range of values for the risk aversion parameter훿to be20
numbers between10
## −1
and10
## 1.5
## :
deltas = np.logspace(start=-1, stop=1.5, num=20)[::-1]
Then we will solve the optimization model repeatedly in a loop, setting a new value
for the parameter훿in each iteration, without having to redefine the whole model each
time.
columns = ["delta", "obj", "return", "risk"] + df_prices.columns.tolist()
df_result = pd.DataFrame(columns=columns)
for d in deltas:
# Update parameter
delta.setValue(d)
# Solve optimization
## M.solve()
# Save results
portfolio_return = m @ x.level()
portfolio_risk = s.level()[0]
(continues on next page)
## 12

(continued from previous page)
row = pd.Series([d, M.primalObjValue(), portfolio_return,
portfolio_risk] + list(x.level()), index=columns)
df_result = df_result.append(row, ignore_index=True)
Then we can plot the results. See the risk-return plane on Fig. 2.1. We generate it
by the following code:
# Efficient frontier
df_result.plot(x="risk", y="return", style="-o",
xlabel="portfolio risk (std. dev.)",
ylabel="portfolio return", grid=True)
We can observe the portfolio composition for different risk-aversion levels on Fig. 2.2,
generated by
# Portfolio composition
my_cmap = LinearSegmentedColormap.from_list("non-extreme gray",
["#111111", "#eeeeee"], N=256, gamma=1.0)
df_result.set_index('risk').iloc[:, 3:].plot.area(colormap=my_cmap,
xlabel='portfolio risk (std. dev.)', ylabel="x")
Fig. 2.1: The efficient frontier.
## 13

Fig. 2.2: Portfolio compositionxwith varying level if risk-aversion훿.
## 14

## Chapter 3
Input data preparation
In Sec. 2.1.1 we mentioned that the expected return vector휇and the covariance matrixΣ
of the securities needs to be estimated. In this chapter we will discuss this topic through
a more general approach.
Portfolio optimization problems are inherently stochastic because they contain uncer-
tain forward-looking quantities, most often the return of securities푅. In the case of the
basic mean–variance optimization problems (2.1)-(2.3) the simple form of the objective
and constraint functions make it possible to isolate uncertainty from the decision vari-
ables and wrap it into the parameters. This allows us to separate stochastic optimization
into parameter estimation and deterministic optimization steps.
In many cases, for instance those involving different risk measures, however, it is
not possible to estimate the optimization inputs as a separate step.  These objectives
or constraints can be a non-trivial function of portfolio returns, and thus we have to
explicitly model the randomness. See examples in Sec. 8. Therefore more generally our
goal is to estimate thedistribution of returnsover the investment time period.  The
simplest way to do that is by using the concept ofscenario.
## 3.1 Scenarios
A scenario is a possible realizationz
## 푘
of the푁dimensional random vector푍of a quantity
corresponding to a given time period [MWOS15]. Thus we can also see a set of scenarios
as a discretization of the distribution of푍.
We denote the number of scenarios by푇. The probability of scenarioz
## 푘
occurring will
be푝
## 푘
, with
## ∑︀
## 푇
## 푘=1
## 푝
## 푘
= 1. In practice when the scenarios come from historical data or are
obtained via computer simulation, all scenarios are assumed to have the same probability
## 1/푇.
We commonly work with scenarios of the security returns푅. Scenario푘of security
returns will ber
## 푘
. Assuming that푝
## 푘
= 1/푇, we can arrange the scenarios as columns of
the푁×푇matrixR.
Models involving certain risk measures can most easily be solved as convex opti-
mization problems using scenarios (see Sec. 8). This approach is calledsample average
approximationin stochastic optimization.
## 15

3.1.1 Scenario generation
Both the quality and the quantity of scenarios is important to get reliable optimal portfo-
lios. Scenarios must be representative and also there must be enough of them to accurately
model a random variable. Too few scenarios could lead to approximation errors, while
too many scenarios could result in excessive computational cost. Next we discuss some
common ways of generating scenarios.
3.1.2 Historical data
If we can assume that past realizations of a random quantity represents possible future
outcomes, we can simply use historical data to create scenarios. Observations are then
collected from a predetermined time window, with a given frequency. Each scenario would
correspond to a vector of simultaneous observations for all푁securities.
Using historical data is a simple non-parametric approach, but it could be inaccurate
or insufficient in some cases:
•The underlying assumption about past realizations representing the future might
not be realistic, if markets fundamentally change in the observed time period, or
unexpected extreme events happen.  Such changes can happen at least in every
several years, often making the collection of enough representative historical data
impossible.
•It can represent the tails of the distribution inaccurately because of low number of
samples corresponding to the low probability tail events. Also these extreme values
can highly depend on the given historical sample, and can fluctuate a lot when the
sample changes.
•It depends on the observations being independent and identically distributed. With-
out this assumption, for example if the data exhibits autocorrelation, volatility
clustering, etc., the distribution estimated based on historical scenarios will be in-
accurate.
3.1.3 Monte Carlo simulation
With this approach we can generate a large number of scenarios according to a specified
distribution. It can be useful in cases when there is a lack of historical scenarios available
in the desired timeframe, but we have a model of the relevant probability distribution.
This allows us to generate scenarios through a parametric approach. It has the following
steps:
- Select a (multivariate) probability distribution that explains all interesting features
of the quantity of interest, e. g. fat tails and tail-dependence of return.
- Estimate the distribution parameters using historical (independent and identically
distributed) data samples.
- Generate scenarios by sampling from the fitted distribution.
Later we will see an example of Monte Carlo scenario generation in Sec. 5.5.1.
## 16

3.1.4 Performance assessment
We advise to have two separate sets of scenario data.
•The first one is thein-sample data, which we use for running the optimization and
building the portfolio. We assume it known at the time of portfolio construction.
•The other data set is theout-of-sample data, which is for assessing the performance
of the optimal portfolio. Out-of sample data is assumed to become available after
the portfolio has been built.
3.2 Modeling the distribution of returns
In this section we describe how to estimate the distribution of security return over the
time period of investment. It can be in the form of the estimated expected return and
covariance matrix of securities, or in the form of a set of return scenarios.
The simplest case is when we have sufficient amount of return data for the desired time
period, then we can estimate their distribution easily and proceed with the optimization.
However, such data is seldom available, especially if the time period is very long, for
reasons mentioned in Sec. 3.1.2. Therefore often we need to use higher frequency (shorter
timeframe) data to estimate the distribution, then project the distribution to the longer
timeframe of interest. This is typically not straightforward to do. We will describe this
procedure first for stocks, then also outline the general method for other securities.
3.2.1 Notions of return
There are two different notions of return. Let푃
## 푡
## 0
and푃
## 푡
## 1
be the prices of a security at
the beginning and end of a time period.
Linear return
Also calledsimple return, calculated as
## 푅
lin
## =
## 푃
## 푡
## 1
## 푃
## 푡
## 0
## −1.
This return definition is the one we used so far in this book, the return whose distribution
we would like to compute over the time period of investment.
We can aggregate linear returns across securities, meaning that the linear return of a
portfolio is the average of the linear returns of its components:
## 푅
lin
x
## =
## ∑︁
## 푖
## 푥
## 푖
## 푅
lin
## 푖
## .
## (3.1)
This is a property we need to be able to validly compute portfolio return and portfolio
risk. However, it is not easy to scale linear return from one time period to another, for
example to compute monthly return from daily return.
## 17

Logarithmic return
Also calledcontinuously compounded return, calculated as
## 푅
log
= log
## (︂
## 푃
## 푡
## 1
## 푃
## 푡
## 0
## )︂
## .
We can aggregate logarithmic returns across time, meaning that the total logarith-
mic return over퐾time periods is the sum of all퐾single-period logarithmic returns:
## 푅
log
## 퐾
= log (푃
## 푡
## 퐾
## /푃
## 푡
## 0
## ) =
## ∑︀
## 퐾
## 푘=1
log
## (︀
## 푃
## 푡
## 푘
## /푃
## 푡
## 푘−1
## )︀
. This property makes it very easy to scale
logarithmic return from one time period to another. However, we cannot average logarith-
mic returns the same way as linear returns, therefore they are unsuitable for computation
of portfolio return and portfolio risk.
Relationship between returns
The two notions of return are related by
## 푅
log
= log
## (︀
## 1 +푅
lin
## )︀
## .
## (3.2)
We must not confuse them, especially on longer investment time periods [Meu10a]. Log-
arithmic returns are suitable for projecting from shorter to longer time periods, while
linear returns are suitable for computing portfolio level quantities.
3.2.2 Data preparation for stocks
Because both returns have properties necessary for portfolio optimization, the data prepa-
ration procedure for a stock portfolio is the following:
- We start with logarithmic return data over the time period of estimation (e. g. one
day if the data has daily frequency).
- We estimate the distribution of logarithmic returns on this time period.  If we
assume that logarithmic returns are normally distributed, then here we estimate
their mean vector and covariance matrix.
- Using the property of aggregation across time we scale this distribution to the time
period of investment (e. g. one year). We can scale the mean and covariance of
logarithmic returns by the “square-root rule”
## 1
. This means that ifℎis the time
period of investment and휏is the time period of estimation, then
## 휇
## ℎ
## =
## ℎ
## 휏
## 휇
## 휏
## ,Σ
## ℎ
## =
## ℎ
## 휏
## Σ
## 휏
## .
- Finally, we convert it into a distribution of linear returns over the period of in-
vestment. Then we can use the property of cross-sectional aggregation to compute
portfolio return and portfolio risk. We show an example working with the assump-
tion of normal distribution for logarithmic returns in Sec. 3.4.
## 1
Originally the square-root rule for stocks states that we can annualize the standard deviation휎
## 휏
of
휏-day logarithmic returns by휎
ann
## =휎
## 휏
## √︀
252/휏, where휎
ann
is the annualized standard deviation, and
252is the number of business days in a year.
## 18

3.2.3 Data preparation in general
We can generalize the above procedure to other types of securities; see in detail in [Meu05].
The role of the logarithmic return in case of stocks is generalized by the concept ofmarket
invariant.  A market invariant is a quantity that determines the security price and is
repeating (approximately) identically across time. Thus we can model it as a sequence of
independent and identically distributed random variables. The steps will be the following:
- Identify the market invariants. As we have seen, the invariant for the stock market
is the logarithmic return. However, for other markets it is not necessarily the return,
e. g. for the fixed-income market the invariant is the change in yield to maturity.
- Estimate the joint distribution of the market invariant over the time period of es-
timation. Apart from historical data on the invariants, any additional information
can be used. We can use parametric assumptions, approximate through moments,
apply factor models, shrinkage estimators, etc., or simply use the empirical distri-
bution, i. e., a set of scenarios.
- Project the distribution of invariants to the time period of investment. Here we
will assume that the invariants are additive across time, i. e., the invariant corre-
sponding to a larger time interval is the sum of invariants corresponding to smaller
intervals (the property that logarithmic returns have). Then the projection is easy
to do through the characteristic function (see in [Meu05]), or we can also scale the
moments by applying the “square-root rule” (see in [Meu10b]).
- Map the distribution of invariants into the distribution of security prices at the
investment horizon through a pricing function. Then compute the distribution of
linear returns from the distribution of prices. If we have a set of scenarios, we can
simply apply the pricing function on each of them.
This process will be followed in the case studies section in an example.
## 3.3 Extensions
In this section we discuss some use cases which need a more general definition of the
MVO problem.
3.3.1 Generalization of linear return
While it is common to use linear return in portfolio optimization, it is not the most
general approach. In certain cases we need to extend its definition to be able to do model
the optimization problem [Meu10c]. As we have seen in Sec. 3.2.1, the key property of
linear return is the aggregation across securities (3.1). It allows us to define the expected
portfolio return and the portfolio variance. We repeat the formula here in detail:
## 푅
lin
x
## =
## 푊
## ℎ
## −푤
## 0
## 푤
## 0
## =
## ∑︁
## 푖
## 푣
## 푖
## (푃
## ℎ,푖
## −푝
## 0,푖
## )
v
## T
p
## 0
## =
## ∑︁
## 푖
## 푣
## 푖
## 푝
## 0,푖
## ∑︀
## 푖
## 푣
## 푖
## 푝
## 0,푖
## 푃
## ℎ,푖
## −푝
## 0,푖
## 푝
## 0,푖
## =
## ∑︁
## 푖
## 푥
## 푖
## 푅
lin
## 푖
## ,
## (3.3)
where푤
## 0
## =v
## T
p
## 0
is the initial wealth,푊
## ℎ
## =v
## T
## 푃
## ℎ
is the final wealth,vis the vector of
security holdings in terms of quantity,p
## 0
is the vector of initial security prices, and푃
## ℎ
## 19

is the vector of final security prices. We can see that maximizing linear return implicitly
assumes that we wish to maximize final wealth.
Based on equation (3.3) there are two components in the aggregation formula that
have to be well defined:
•Linear return of a security: It is given for security푖as
## 푅
lin
## 푖
## =
## 푃
## ℎ,푖
## −푝
## 0,푖
## 푝
## 0,푖
## (3.4)
Linear return is not well defined if the price of the security푝
## 0,푖
is zero. This can
occur for example with swaps and futures.
•Portfolio weight: It is given for security푖as
## 푥
## 푖
## =
## 푣
## 푖
## 푝
## 0,푖
## 푤
## 0
## .
## (3.5)
Portfolio weight is not well defined if the initial wealth푤
## 0
(the total portfolio value
at time푡=  0) is zero. This can occur for example in the case of dollar neutral
long-short portfolios.
To be able to do portfolio optimization in the above mentioned special cases, we need
to extend the definitions of portfolio weight and linear return such that we can apply the
aggregation property (3.3).
•To extend the definition of linear return, we associate with each security a general-
ized normalizing quantity orbasis푏
## 푖
that takes the role of the security price푝
## 0,푖
in
the denominator of formula (3.4):
## 푅
lin
## 푖
## =
## 푃
## ℎ,푖
## −푝
## 0,푖
## 푏
## 푖
## (3.6)
The basis depends on the nature of the security; for swaps it can be the notional,
for options it can be the strike or the underlying value, etc. It can be any value
that results in an intuitive return definition to the portfolio manager.  In most
cases though it will be the price of the security, giving back the usual linear return
definition (3.4).
•To extend the definition of the portfolio weight, we introduce a generalizedportfolio
basis푏
## P
that takes the role of the initial portfolio value푤
## 0
in the denominator of
formula (3.5). We also use the relevant security basis푏
## 푖
in the numerator:
## 푥
## 푖
## =
## 푣
## 푖
## 푏
## 푖
## 푏
## P
## .
## (3.7)
In general, the basis quantities푏
## 푖
## (푖= 1,...,푁)and푏
## P
have to satisfy the following
properties:
- They are positive. This guarantees that for a long position, a positive net profit
(P&L) will correspond to a positive return.
- They are measured in the same money units as the P&L. This ensures that the
return is dimensionless.
## 20

- They are homogeneous, i.e. if푏is the basis for one unit of security, then the basis
for푛unit of securities will be푛푏. This ensures that the return is independent of
the position size.
- They are known at the beginning of the investment period (at time푡= 0). This
ensures that the return will correspond to the full investment period.
By defining a basis value for each security and a basis value for the portfolio, com-
puting the expected portfolio return and portfolio variance will be possible through the
generalized aggregation formula:
## 푅
lin
x
## =
## ∑︁
## 푖
## 푣
## 푖
## 푏
## 푖
## 푏
## P
## 푃
## ℎ,푖
## −푝
## 0,푖
## 푏
## 푖
## =
## ∑︁
## 푖
## 푥
## 푖
## 푅
lin
## 푖
## ,
## (3.8)
We can observe that in formula (3.8), the security level basis values푏
## 푖
cancel out. This
means that the value of the security level basis does not affect the portfolio return. It
only matters in the context of interpreting the security weight and security return.
3.3.2 Portfolio scaling
During the introduction of the MVO problem in Sec. 2 we interpreted푥
## 푖
as the fraction
of wealth invested into security푖, such that the sum of weights is1. This is, however,
not the only possibility. From formula (3.8) we can see that the portfolio return and
its interpretation or scaling is only affected by the portfolio level basis value푏
## P
. We can
select it independently of the security level basis values푏
## 푖
(푖= 1,...,푁), and thus change
the scaling of the portfolio weights. Some natural choices:
## •푏
## P
## =
## ∑︀
## 푖
## 푣
## 푖
## 푏
## 푖
. This choice ensures that the portfolio weights푥
## 푖
## (푖= 1,...,푁)sum
to1, and thus represent fractions of푏
## P
## .
## •푏
## P
## =
## ∑︀
## 푖
## 푣
## 푖
## 푝
## 0,푖
## =푤
## 0
. In this case we normalize the P&L with the total portfolio
value. For long only portfolio this is the same as the initial capital.
## •푏
## P
## =
## ∑︀
## 푖
## |푣
## 푖
## |푝
## 0,푖
, the gross exposure. This provides an intuitive fraction interpreta-
tion to푥
## 푖
for long-short portfolios as well.
## •푏
## P
## =퐶
init
, the initial capital.
## •푏
## P
= 1. In this case formula (3.8) will become the total net profit (P&L) in dollars,
and the portfolio weights will also be measured in dollars.
In this book, we will use푏
## P
## =
## ∑︀
## 푖
## 푣
## 푖
## 푏
## 푖
by default. Any other choice will be explicitly
stated.
3.3.3 Long-short portfolios
When working with a long-short portfolio, we also have to extend the MVO problem
slightly. If the investor can short sell and also use leverage (e. g. margin loan), then
the total value of the investment (the gross exposure) can be greater than the amount
of initial capital. In case of leverage, the gross exposure provides better insight into the
risks taken than the total capital, so being fully invested is no longer meaningful as a sole
constraint.
## 21

Therefore in the optimization problem formulation of typical long-short portfolios,
we will substitute the budget constraint (2.5) to a gross exposure limit, i. e., a leverage
constraint:
## ∑︁
## 푖
## |푣
## 푖
## |푝
## 0,푖
## ≤퐿·퐶
init
## ,
where퐶
init
is the initial invested capital, and퐿is the leverage limit. If we normalize here
with푏
## P
## =퐶
init
, then we get
## ‖x‖
## 1
## ≤퐿.
For example, Regulation-T states that for long positions the margin requirement is 50%
of the position value, and for short positions the collateral requirement is 150% of the
position value (of which 100% comes from short sale proceeds).  This translates into
퐿= 2. A special case of퐿= 1would mean that we can short sell but have no leverage.
A more general version of the leverage constraint is
## ∑︁
## 푖
## 푚
## 푖
## |푥
## 푖
## |≤1.
where푚
## 푖
is the margin requirement of position푖. In case of Reg-T we had푚
## 푖
## =
## 1
## 2
for all
## 푖.
We might also impose anenhanced active equitystructure on the portfolio, like 120/20
or 130/30. This is typically considered when it is possible to use the short sale proceeds
to purchase more securities (another form of leverage), so there is no need to use margin
loans. Such a portfolio has 100% market exposure, which is expressed by
## ∑︁
## 푖
## 푣
## 푖
## 푝
## 0,푖
## =퐶
init
## ,
or writing the same usingxafter normalizing again with푏
## P
## =퐶
init
, we get the ususal
budget constraint
## ∑︁
## 푖
## 푥
## 푖
## = 1.
For example, 130/30 type portfolio would have the constraints‖x‖
## 1
## ≤1.6and1
## T
x= 1.
We can also usefactor neutralityconstraints on a long-short portfolio. We can achieve
this simply by adding a linear equality constraint expressing that the portfolio should be
orthogonal to a vector훽of factor exposures:
## 훽
## T
x= 0.
A special case of this is when the factor exposures are all ones; then the portfolio will be
dollar neutral:
## 1
## T
x= 0.
We have to note that in the case of dollar neutrality, the total portfolio value is0.
Referring back to the discussion about portfolio weights in Sec. 3.3.1, in this case the
portfolio weights cannot be defined as (3.5).  Instead, we need to define a푏
## P
that is
different from푤
## 0
. See also in Sec. 3.3.2.
Note also that if we model using the quadratic cone instead of the rotated quadratic
cone andx=0is a feasible solution, then there will be no optimal portfolios which
are not fully invested. The solutions will be eitherx=0or some risky portfolio with
## ‖x‖
## 1
= 1. See a detailed discussion about this in Sec. 13.3.
## 22

## 3.4 Example
In this example we will show a case with real data, that demonstrates the steps in Sec.
3.2.3 and leads to the expected return vector and the covariance matrix we have seen in
## Sec. 2.4.
3.4.1 Problem statement
Suppose that we wish to invest in the U.S. stock market with a long-only strategy. We
have chosen a set of eight stocks and we plan to re-invest any dividends. We start to
invest at time푡= 0and the time period of investment will beℎ= 1year, ending at time
## 푡= 1.
We also have a pre-existing allocationv
## 0
measured in number of shares.  We can
express this allocation also in fractions of total dollar valuev
## T
## 0
p
## 0
, byx
## 0
## =v
## 0
## ∘p
## 0
## /v
## T
## 0
p
## 0
## .
Our goal is to derive a representation of the distribution of one year linear returns at
time푡= 1, and use it to solve the portfolio optimization problem. Here we will represent
the distribution with the estimate휇of the expected one year linear returns휇=E(푅)
and with the estimateΣof the covariance of one year linear returnsΣ = Cov(푅), at the
time point푡= 1.
3.4.2 Data collection
We obtain a time-series of daily stock prices from data providers, for a five year period
(specifically from 2016-03-21 until 2021-03-18), adjusted for splits and dividends. During
this time period the market was generally bullish, with only short downturn periods. This
will be reflected in the estimated mean return vector and in the covariance structure. See
a deeper analysis in Sec. 5.5.1.
We choose an estimation time period of one week as a balance between having enough
independent observations and the homogeneity of the data series. Thus휏= 1/52year.
At this point we assume that the price data is available in the pandas DataFrame
df_prices. The graphs of the price time-series can be seen on Fig. 3.1:
3.4.3 Estimation of moments
Now we will go over the steps in Sec. 3.2.3.
Market invariants
For stocks, both linear and logarithmic returns are market invariants, however it is easier
to project logarithmic returns to longer time periods.  It also has an approximately
symmetrical distribution, which makes it easier to model. Therefore we resample each
price time series to weekly frequency, and obtain a series of approximately 250 non-
overlapping observations:
df_weekly_prices = df_prices.resample('W').last()
Next we compute weekly logarithmic returns from the weekly prices, followed by basic
handling of missing values:
## 23

Fig. 3.1: Daily prices of the 8 stocks in the example portfolio.
df_weekly_log_returns = \
np.log(df_weekly_prices) - np.log(df_weekly_prices.shift(1))
df_weekly_log_returns = df_weekly_log_returns.dropna(how='all')
df_weekly_log_returns = df_weekly_log_returns.fillna(0)
Distribution of invariants
To estimate the distribution of market invariants, in this example we choose a parametric
approach and fit the weekly logarithmic returns to a multivariate normal distribution.
This requires the estimation of the distribution parameters휇
log
## 휏
andΣ
log
## 휏
. For simplicity
we use the sample statistics denoted by휇
log
## 휏
andΣ
log
## 휏
. The “log” superscript indicates
that these statistics correspond to the logarithmic returns. In code this looks like
return_array = df_weekly_log_returns.to_numpy()
m_weekly_log = np.mean(return_array, axis=0)
S_weekly_log = np.cov(return_array.transpose())
## 24

Projection of invariants
We project the distribution of the weekly logarithmic returns represented by휇
log
## 휏
and
## Σ
log
## 휏
to the one year investment horizon. Because the logarithmic returns are additive
across time, the projected distribution will also be normal with parameters휇
log
## ℎ
## =
## ℎ
## 휏
## 휇
log
## 휏
andΣ
log
## ℎ
## =
## ℎ
## 휏
## Σ
log
## 휏
## .
m_log = 52 * m_weekly_log
## S_log = 52 * S_weekly_log
Distribution of linear returns
To obtain the distribution of linear returns at the investment horizonℎ, we first derive
the distribution of security prices at the investment horizon.  Using the characteristic
function of the normal distribution, and the pricing function푃
## ℎ
## =p
## 0
exp
## (︀
## 푅
log
## )︀
, we get
## E(푃
## ℎ
## )=p
## 0
## ∘exp
## (︁
## 휇
log
## ℎ
## +
## 1
## 2
diag(Σ
log
## ℎ
## )
## )︁
## ,
## Cov(푃
## ℎ
## )   =E(푃
## ℎ
## )E(푃
## ℎ
## )
## T
∘(exp(Σ
log
## ℎ
## )−1).
## (3.9)
In code, this will look like
p_0 = df_weekly_prices.iloc[0].to_numpy()
m_P = p_0 * np.exp(m_log + 1/2*np.diag(S_log))
S_P = np.outer(m_P, m_P) * (np.exp(S_log) - 1)
Then the estimated moments of the linear return is easy to get by휇=
## 1
p
## 0
## ∘E(푃
## ℎ
## )−1
andΣ=
## 1
p
## 0
p
## T
## 0
∘Cov(푃
## ℎ
), where∘denotes the elementwise product and division by a
vector or a matrix is also done elementwise.
m = 1 / p_0 * m_P - 1
S = 1 / np.outer(p_0, p_0) * S_P
Notice that we could have computed the distribution of linear returns from the dis-
tribution of logarithmic returns directly is this case, using the simple relationship (3.2).
However in general for different securities, especially for derivatives we derive the distri-
bution of linear returns from the distribution of prices. This case study is designed to
demonstrate the general procedure. See details in [Meu05, Meu11].
Also in particular for stocks we could have started with linear returns as market
invariants, and model their distribution. Projecting it to the investment horizon, however,
would have been much more complicated. There exist no scaling formulas for the linear
return distribution or its moments as simple as the ones for logarithmic returns.
## 25

## Chapter 4
Dealing with estimation error
As we have seen in Sec. 2, Markowitz portfolio optimization is a convenient and useful
framework. However, in practice there is one important limitation [MM08]. The optimal
solution is extremely sensitive to changes in the vector휇of estimated expected returns
and the estimated covariance matrixΣ. Small changes in these input parameters often
result in large changes in the optimal portfolio. The optimization basically magnifies the
impact of estimation errors, yielding unintuitive, questionable portfolios and extremely
small or large positions, which are difficult to implement. The instability causes unwar-
ranted turnover and transaction costs.
It would help to use a larger estimation window, but the necessary amount of data
grows unrealistically high quickly, because the size of the covariance matrix increases
quadratically with the number of securities푁[Bra10, CY16].
Fortunately there are multiple approaches to mitigating this issue. These can signifi-
cantly reduce the impact of estimation errors and stabilize the optimization.
In the following we explore the main aspects of overcoming the estimation error issues.
4.1 Estimation of mean
The optimization is particularly sensitive to estimation errors in expected returns, small
variations in sample means can lead to sizeable portfolio readjustments. Estimation based
only on historical time-series can result in poor out-of-sample portfolio performance.
Sample mean is hard to estimate accurately from historical data, because for all unbiased
estimators the standard error fundamentally depends on the length (duration) of the
time-series [Dod12]. Therefore to get better accuracy it is necessary to extend the time
horizon, which is often problematic because data from a longer time interval might contain
more structural changes, i. e. lack stationarity in its underlying parameters.
Despite these difficulties, the below methods offer an improvement on mean estima-
tion.
## 26

4.1.1 Black-Litterman model
One way to deal with estimation error is to combine noisy data with prior informa-
tion. We can base prior beliefs on recent regulatory, political and socioeconomic events,
macroeconomy news, financial statements, analyst ratings, asset pricing theories, insights
about market dynamics, econometric forecasting methods, etc. [AZ10]
The Black-Litterman model considers the market equilibrium returns implied by
CAPM as a prior estimate, then allows the investor to update this information with
their own views on security returns. This way we do not need noisy historical data for
estimation [Bra10, CJPT18].
Thus we assume the distribution of expected return휇to be풩(휇
eq
,Q), where휇
eq
is the equilibrium return vector, and the covariance matrixQrepresents the investor’s
confidence in the equilibrium return vector as a realistic estimate.
The investor’s views are then modeled by the equationB휇=q+휀, where휀∼풩(0,V).
Each row of this equation represents a view in the form of a linear equation, allowing
for both absolute and relative statements on one or more securities. The views are also
uncertain, we can use the diagonal ofVto set the confidence in them, small variance
meaning strong confidence in a view.
By combining the prior with the views using Bayes’s theorem we arrive at the estimate
## 휇
## BL
=Mq+ (I−MB)휋,
## (4.1)
whereM=QB
## T
## (BQB
## T
## +V)
## −1
## .
The prior휇
eq
is implied by the solutionx=
## 1
## 훿
## Σ
## −1
휇of problem (2.3), by assuming
thatx=x
mkt
, i. e., weights according to market capitalization.
We can also understand the Black–Litterman model as an application of generalized
least-squares to combine two information sources (e. g. historical data and exogeneous
views) [Bra10, The71]. Assuming the sources are independent, we write them into one
linear equation with block structure as
## (︂
## 휋
q
## )︂
## =
## (︂
## I
## B
## )︂
## 휇+
## (︂
## 휀
## 휋
## 휀
q
## )︂
## ,(4.2)
where휋is the prior,휀
## 휋
## ∼ 풩(0,Q),휀
q
∼ 풩(0,V),QandVnonsingular. The solution
will be
## 휇
## GLS
## = (Q
## −1
## +B
## T
## V
## −1
## B)
## −1
## (Q
## −1
## 휋+B
## T
## V
## −1
q).
## (4.3)
## Substituting휋=휇
eq
we get a different form of휇
## BL
## .
## 1
Because the Black-Litterman model gives an expected return vector relative to the
market equilibrium return, the optimal portfolio will also be close to the market portfolio,
meaning it should not contain extreme positions. A drawback of this method is that the
exogeneous views are assumed independent of historical data, which can be difficult to
satisfy in practice. The model is extended further in [BGP12] to views on volatility and
market dynamics.
## 1
We can derive this using(A+B)
## −1
## =A
## −1
## −A
## −1
## B(A+B)
## −1
for nonsingular matrices.
## 27

4.1.2 Shrinkage estimation
Sample estimators are unbiased, but perform well only in the limit case of an infinite
number of observations. For small samples their variance is large. In contrast, constant
estimators have no variance, but display large bias.Shrinkage estimatorsimprove the
sample estimator by adjusting (shrinking) the sample estimator towards a constant esti-
mator, theshrinkage target, basically finding the optimal tradeoff between variance and
bias.
Shrinkage can also be thought of as regularization or a form of empirical Bayes esti-
mation. Also the shrinkage target has to be consistent with other prior information and
optimization constraints.
1.James–Stein estimator:
This is the most widely known shrinkage estimator for the estimation of mean
vector of a normal random variable with known covariance [EM76, LC98, Ric99].
The sample mean휇
sam
is normally distributed with mean휇and covarianceΣ/푇,
whereΣis the covariance matrix of the data. Assumingbas target, the James–Stein
estimator will be
## 휇
## JS
## =b+ (1−훼)(휇
sam
## −b),
where theshrinkage coefficientis
## 훼=
## 1
## 푇
## ̃
## 푁−2
## (휇
sam
## −b)
## T
## Σ
## −1
## (휇
sam
## −b)
## ,
and
## ̃
푁= Tr(Σ)/휆
max
(Σ)is the effective dimension. The estimator improves휇
sam
for
## ̃
푁 >2, i. e., whenΣ/푇has not too different eigenvalues. Otherwise an estimator
with coordinatewise different shrinkage coefficient is preferable, such as the one in
## [EM75].
The targetbis arbitrary, but it is common to set it as the mean of means1
## T
## 휇
sam
## /푁.
This depends on the data, making the number of parameters to estimate one less,
so the dimension
## ̃
푁should be adjusted accordingly.
We can further improve휇
## JS
by the positive-part rule, when we set(1−훼)to zero
whenever it would be negative.
2.Jorion’s estimator[Jor86]:
This estimator was derived in the context of portfolio analysis through an empirical
Bayes approach. It uses the target푏1, where푏is the volatility-weighted mean of
means:
## 푏=
## 1
## T
## Σ
## −1
## 휇
sam
## 1
## T
## Σ
## −1
## 1
## .
The shrinkage coefficient in this case is
## 훼=
## 푁+ 2
## 푁+ 2 +푇(휇
sam
## −푏1)
## T
## Σ
## −1
## (휇
sam
## −푏1)
## .
IfΣis not known, it can be replaced by
## 푇−1
## 푇−푁−2
Σ, whereΣis the sample covariance
matrix. The assumption of normality is not critical, but it gives more improvement
over휇
sam
in “symmetric” situations, where variances are similar across data series.
## 28

4.2 Estimation of the covariance matrix
In contrast to the estimation of the mean, the standard error of the sample variance
depends only on the sample size, making it possible to estimate from higher frequency
data.  Still, if the number of securities is high relative to the number of samples, the
optimal solution can suffer from two issues [MM08]:
•Ill conditioning: We need to have sufficient amount of data to get a well-conditioned
covariance estimate. A rule of thumb is that the number of observations푇should
be an order of magnitude greater than the number of securities푁.
•Estimation error: The estimation error of the covariance matrix increases quadrat-
ically (in contrast to linear increase in the case of the mean), so if푁/푇is large it
can quickly become the dominant contributing factor to loss of accuracy.
When푁/푇is too large, the following regularization methods can offer an improvement
over the sample covariance matrix [CM13]. Moreover, we can also apply factor models in
this context, we discuss this in more detail in Sec. 5.
4.2.1 Covariance shrinkage
The idea is the same as in Sec. 4.1.2, we try to achieve a balanced bias–variance tradeoff
by shrinking the sample covariance matrix towards a shrinkage target. We can choose the
latter in many ways, but it is important to be consistent with other prior information, e.
g. what is implied by constraints.
The most well known shrinkage estimator is by Ledoit and Wolf; see [LW03a, LW03b,
LW04] and [CM13] for a quick review. It combines the sample covariance matrixΣ
sam
with the targetB:
## Σ
## LW
## = (1−훼)Σ
sam
## +훼B.
## (4.4)
We have to estimate the shrinkage intensity parameter훼depending on the targetB. In
practice it is also truncated so that훼∈[0,1]. Ledoit and Wolf propose three type of
targets:
•Multiple of the identity matrix:
## B
## I
## =  ̄푠
## 2
## I,
## (4.5)
where ̄푠
## 2
is the average sample variance. This target is optimal among all targets
of the form푐Iwith푐∈R. The corresponding optimal훼is
## 훼=
## 1
## 푇
## 2
## ∑︀
## 푇
## 푘=1
## Tr
## (︁
## [︀
z
## 푘
z
## T
## 푘
## −Σ
sam
## ]︀
## 2
## )︁
## Tr
## (︀
## [Σ
sam
## −B
## I
## ]
## 2
## )︀
## ,
wherez
## 푘
is observation푘of the centered data matrixZ. See the details in [LW04].
The sample covariance matrixΣ
sam
can be ill-conditioned because estimation tends
to scatter the sample eigenvalues further away from the mean ̄휎
## 2
of the true unknown
eigenvalues. This raises the condition number ofΣ
sam
relative to the true matrixΣ
and this effect is stronger as the condition number ofΣis better or as푁/푇grows.
## 29

The above shrinkage estimator basically pulls all sample eigenvalues back towards
their grand mean ̄푠
## 2
, the estimate of ̄휎
## 2
, thus stabilizing the matrix. We can also
see this as a form of regularization.
•Single factor covariance matrices implied by the CAPM
## 2
## :
## B
## CAPM
## =푠
## 2
mkt
## 훽훽
## T
## +Σ
## 휀
## ,
## (4.6)
where푠
## 2
mkt
is the sample variance of market returns,훽is the vector of factor ex-
posures, andΣ
## 휀
is the diagonal matrix containing the variances of the residuals.
The single factor model is discussed in Sec. 5. In practice a proxy of the market
factor could be the equally-weighted or the market capitalization-weighted portfolio
of the constituents of a market index, resulting in two different shrinkage targets.
The optimal shrinkage intensity is derived in [LW03b].
•Constant correlation covariance matrix:
## B
## CC
## =  ̄푟
## √
s
## √
s
## T
+ (1− ̄푟)Diag(s),
## (4.7)
wheres= diag(Σ
sam
), and ̄푟=
## 2
## 푛(푛−1)
## ∑︀
## 푛−1
## 푖=1
## ∑︀
## 푛
## 푗=푖+1
## 푟
## 푖,푗
is the average sample cor-
relation. The optimal shrinkage intensity is derived in [LW03a].
Notice that all three targets are positive definite matrices. Shrinkage towards a posi-
tive target guarantees that the resulting estimate is also positive, even when the sample
covariance matrix itself is singular. Further advantage of this estimator is that it works
also in the case of singular covariance matrices, when푁 > 푇.
In [LW20], the authors present a nonlinear version of this estimator, which can apply
different shrinkage intensity to each sample eigenvalue, resulting in even better perfor-
mance.
4.2.2 Covariance de-noising
According to [dP19], the shrinkage method in Sec. 4.2.1 does not discriminate between
the eigenvalues associated with noise and the eigenvalues associated with signal, thus it
weakens the signal as well. With the help of random matrix theory the method discussed
here shrinks only the part of the covariance matrix that is associated with noise. Taking
the covariance matrixΣit consists of the following steps:
- Compute the correlation matrix from the covariance matrix:C=D
## −1/2
## ΣD
## −1/2
## ,
whereD= Diag(Σ).
- Compute the eigendecomposition ofCand compute the empirical distribution of
the eigenvalues using Kernel Density Estimation.
- Fit the Marčenko–Pastur distribution to the empirical distribution, which gives the
theoretical bounds휆
## +
and휆
## −
on the eigenvalues associated with noise. This way
we separate the spectrum into a random matrix (noise) component and the signal
component. The eigenvalues of the latter will be above the theoretical upper bound
## 휆
## +
## .
## 2
The Capital Asset Pricing Model (CAPM) relates the expected return of securities (particularly
stocks) to their systematic risk. We can calculate it asE(푅
## 푖
## ) =푟
f
## +훽
## 푖
## (E(푅
mkt
## )−푟
f
), whereE(푅
## 푖
## )is
the expected return,푅
f
is the risk-free rate,훽
## 푖
is the measure of systematic risk, andE(푅
mkt
)is the
expected return of the market.
## 30

- Change the eigenvalues below휆
## +
to their average, arriving at the de-noised corre-
lation matrix
## ̃
## C.
- Recover the de-noised covariance matrix:
## ̃
## Σ=D
## 1/2
## ̃
## CD
## 1/2
## .
4.2.3 Robust estimation
The reason for estimation error is partly that maximum likelihood estimators are highly
sensitive to deviations from the assumed (typically normal) distribution. The empirical
distribution of security returns usually deviates from the normal distribution [VD09].
Therefore it can be helpful to use robust estimation methods in the construction of mean-
variance portfolios. Robust estimators are not as efficient as the maximum likelihood
estimator but are stable even when the underlying model is not perfectly satisfied by the
available data.
There are two approaches to involve robust statistics in portfolio selection:
•One-step methods: We perform the robust estimation and the portfolio optimization
in a single step. We substitute the portfolio risk and portfolio return expressions by
their robust counterparts. See for example in [VD09]. We discuss some examples
in section Sec. 8.
•Two-step methods: First we compute the robust estimates of the mean vector and
the covariance matrix of the data. This is followed by solving the usual portfolio
optimization problem with the parameters replaced by their robust estimates. There
are various robust covariance estimators, such as Minimum Covariance Determinant
(MCD), 2D Winsorization, S-estimators. See for example in [RSTF20, WZ07]. We
do not cover this topic in detail in this book.
4.3 Using constraints
Solutions from unconstrained portfolio optimization – while having elegant analytical
formulas – can be unreliable in practice. The optimization can significantly overweight
securities with large estimated returns, negative correlations, and small variances. The
securities with the largest estimation error will get the largest positions. There will also
be many zero positions, contradicting diversification [AZ10, MM08].
Financially meaningful constraints on the portfolio weights can also act as regular-
ization, reducing error in the optimal portfolio [CM13]. In [DGNU09],퐿
## 1
and퐿
## 2
norm
constraints are introduced for this purpose:
maximize휇
## T
x−
## 훿
## 2
x
## T
## Σx
subject to1
## T
x=   1,
## ‖x‖
## 푝
## 푝
## ≤푐.
## (4.8)
If푝=  1and푐=  1we get back the constraintx≥0, which prevents short-selling.
In [JM03] the authors found that preventing short-selling or limiting position size is
equivalent to shrinking all covariances of securities for which the respective constraint
is binding. The short-selling constraint also implies shrinkage effect on the mean vector
toward zero. In a conic optimization problem, the 1-norm constraint can be modeled
based on Sec. 13.1.1.
## 31

For the case푝=  1and푐 >1with the constraint1
## T
x=  1also present, we get a
“short-sale budget”, meaning that the total weight of short positions will be bounded by
(푐−1)/2. This allows the possibility of optimizing e. g. 130/30 type portfolios with
## 푐= 1.6.
If푝= 2and the only constraint is1
## T
x= 1, then the minimum feasible value of푐
is1/푁, giving thex=1/푁portfolio as the only possible solution. With larger values
of푐we get an effect equivalent to the Ledoit–Wolf shrinkage towards multiple of the
identity. For other shrinkage targetsB, the corresponding constraint will bex
## T
## Bx≤푐
or‖G
## T
x‖
## 2
## 2
≤푐whereGG
## T
=B. In a conic optimization problem, we can model the
2-norm constraint based on Sec. 13.1.1.
In general,
•adding an퐿
## 1
norm-constraint is equivalent to shrinking all covariances of securities
that are being sold short. Instead of the elementwise short-sale constraints here we
impose a global short-sale budget using only one constraint. This means that the
implied shrinkage coefficient will be the same for all securities. According to the
usual behavior of LASSO regression, the퐿
## 1
norm-constrained portfolios are likely
to assign a zero weight to at least some of the securities. This could be beneficial if
we wish to invest only into a small number of securities.
•adding an퐿
## 2
norm-constraint is equivalent to shrinking the sample covariance ma-
trix towards the identity matrix. According to properties of ridge regression, the퐿
## 2
norm-constrained portfolios will typically have a non-zero weight for all securities,
which is good if we want full diversification.
4.4 Improve the optimization
In dealing with estimation error it is also a possibility to directly improve the optimization
procedure.
4.4.1 Resampled portfolio optimization
To overcome estimation uncertainty we can use nonparametric bootstrap resampling on
the available historical return data. This way we can create multiple instances of the
data and generate multiple expected return and covariance matrix estimates using any
estimation procedure. Then we compute the efficient frontier from all of them. Finally,
we average the obtained solutions to make the effect of the estimation errors cancel out.
This procedure is thoroughly analysed in [MM08].
Note that we should not average over portfolios of too different variances. Thus the
averaging procedure assumes that for each pair of inputs we generate푚points on the
efficient frontier, and rank them1to푚. Then the portfolios with the same rank will be
averaged.
In this process we can treat the number of simulated return samples in each batch of
resampled data as a parameter. It can be used to measure the level of certainty of the
expected return estimate. A large number of simulated returns is consistent with more
certainty, while a small number is consistent with less certainty.
While this method offers good results in terms of diversification and mitigating the
effects of estimation error, it has to be noted that it does this at the cost of intensive
computational work.
## 32

According to [MM08], improving the optimization procedure is more beneficial than
to use improved estimates (e.  g.  shrinkage) as input parameter.  However, the two
approaches do not exclude each other, so they can be used simultaneously.
4.4.2 Nested Clustering Optimization (NCO)
A recent method to tackle estimation error and error sensitivity of the optimization is
described in [dP19]. The NCO method is capable of controlling for noise in the inputs,
and also for instabilities arising from the covariance structure:
•Noise can arise from lack of data. As푁/푇approaches1, the number of data points
will approach the number of degrees of freedom in covariance estimation.  Also
based on random matrix theory, the smallest eigenvalue of the covariance matrix
will be close to zero, raising the condition number.
•Instability in the optimal solution comes from the correlation structure, the exis-
tence of highly correlating clusters of securities. These will also raise the condition
number of the covariance matrix. The most favorable correlation structure is that
of the identity matrix.
The steps of NCO are the following:
- Cluster the securities into highly-correlated groups based on the correlation matrix
to get a partition푃of the security universe. We could apply hierarchical clustering
methods, or the method recommended in [dPL19]. It could be worthwhile to do
the clustering also on the absolute value of the correlation matrix to see if it works
better.
- Run portfolio optimization for each cluster separately.  Letx
## 푘
denote the푁-
dimensional optimal weight vector of cluster푃
## 푘
, such that푥
## 푘,푖
## = 0,∀푖 /∈푃
## 푘
## .
- Reduce the original covariance matrixΣinto a covariance matrixΣ
cl
between
clusters:Σ
cl
## 푘,푙
## =x
## T
## 푘
## Σx
## 푙
. The correlation matrix computed fromΣ
cl
will be closer
to identity, making the inter-cluster optimization more accurate.
- Run the inter-cluster portfolio optimization by treating each cluster as one security
and using the reduced covariance matrixΣ
cl
.  We will denote the resulting푘-
dimensional optimal weight vector byx
cl
## .
- Generate the final optimal portfolio:x=
## ∑︀
## 푘
## 푥
cl
## 푘
x
## 푘
## .
By splitting the problem in the above way into two independent parts, the error caused
by intra-cluster noise cannot propagate across clusters.
In the paper the author also proposes a method for estimating the error in the optimal
portfolio weights. We can use it with any optimization method, and facilitates comparison
of methods in practice. The steps of this procedure can be found in Sec. 13.4.
## 33

## 4.5 Example
In this part we add shrinkage estimation to the case study introduced in the previous
chapters. We start at the point where the expected weekly logarithmic returns and their
covariance matrix is available:
return_array = df_weekly_log_returns.to_numpy()
m_weekly_log = np.mean(return_array, axis=0)
S_weekly_log = np.cov(return_array.transpose())
The eigenvalues of the covariance matrix are1e-3 * [0.2993, 0.3996, 0.4156, 0.
5468, 0.6499, 0.9179, 1.0834, 4.7805]. We apply the Ledoit–Wolf shrinkage with
target (4.5):
## N = S_weekly_log.shape[0]
T = return_array.shape[0]
# Ledoit--Wolf shrinkage
## S = S_weekly_log
s2_avg = np.trace(S) / N
B = s2_avg * np.eye(N)
Z = return_array.T - m_weekly_log[:, np.newaxis]
alpha_num = alpha_numerator(Z, S)
alpha_den = np.trace((S - B) @ (S - B))
alpha = alpha_num / alpha_den
S_shrunk = (1 - alpha) * S + alpha * B
The functionalpha_numeratoris to compute the sum in the numerator of훼:
def alpha_numerator(Z, S):
s = 0
## T = Z.shape[1]
for k in range(T):
z = Z[:, k][:, np.newaxis]
X = z @ z.T - S
s += np.trace(X @ X)
s /= (T**2)
return s
In this example, we get훼= 0.0843, and the eigenvalues will become1e-3 * [0.3699,
0.4618, 0.4764, 0.5965, 0.6909, 0.9363, 1.0879, 4.4732], closer to their sample
mean as expected.
Next we implement the James–Stein estimator for the expected return vector:
# James--Stein estimator
m = m_weekly_log[:, np.newaxis]
o = np.ones(N)[:, np.newaxis]
## S = S_shrunk
iS = np.linalg.inv(S)
b = (o.T @ m / N) * o
N_eff = np.trace(S) / np.max(np.linalg.eigvalsh(S))
alpha_num = max(N_eff - 3, 0)
(continues on next page)
## 34

(continued from previous page)
alpha_den = T * (m - b).T @ iS @ (m - b)
alpha = alpha_num / alpha_den
m_shrunk = b + max(1 - alpha, 0) * (m - b)
m_shrunk = m_shrunk[:, 0]
In this case though it turns out that the effective dimension
## ̃
푁would be too low for the
estimator to give an improvement over the sample mean. This is because the eigenvalues
of the covariance matrix are spread out too much, meaning that the uncertainty of the
mean vector is primarily along the direction of one or two eigenvectors, effectively reducing
the dimensionality of the estimation.
We can check the improvement on the plot of the efficient frontier Fig. 4.2. We can
observe the portfolio composition for different risk-aversion levels on Fig. 4.2.
Fig. 4.1: The efficient frontier.
## 35

Fig. 4.2: Portfolio compositionxwith varying level if risk-aversion훿.
## 36

## Chapter 5
Factor models
The purpose offactor modelsis to impose a structure on financial variables and their
covariance matrix by explaining them through a small number of common factors. This
can help to overcome estimation error by reducing the number of parameters, i. e., the
dimensionality of the estimation problem, making portfolio optimization more robust
against noise in the data. Factor models also provide a decomposition of financial risk to
systematic and security specific components [CM13]. Factor models can be generalized
in many ways; see in [BS11].
## 5.1 Definition
## Let푍
## 푡
be an푁-dimensional random vector representing a financial variable at time푡.
We can write푍
## 푡
as a linear function of components as
## 푍
## 푡
## =훽퐹
## 푡
## +휃
## 푡
## ,
where퐹
## 푡
is a퐾-dimensional random vector representing thecommon factorsat time푡,
훽is the푁×퐾matrix offactor exposures(orloadings,betas), and휃
## 푡
## =훼+휀
## 푡
is the
specific componentsuch thatE(휃
## 푡
## ) =훼and휀
## 푡
is white noise
## 1
with covarianceΣ
## 휃
## . If푍
## 푡
represents security returns, then훽E(퐹
## 푡
)is the expected explained return and훼is the
expected unexplained return.
Factor models typically work with the following assumptions:
•Exactfactor model: All common movement between pairs of variables is modeled
by the factors. This means that the covariances of푍
## 푡
is determined only by the
covariances of퐹
## 푡
. This gives the conditionsCov(휀
## 푡
## 1
## ,퐹
## 푡
## 2
) =0for all푡
## 1
## ,푡
## 2
and that
## Cov(휀
## 푡
## ) = Σ
## 휀
is diagonal.
## 2
•Staticfactor model:퐹
## 푡
only has a contemporaneous effect on푍
## 푡
## .
## 3
•Weakly stationary factors: The sequence of random variables퐹
## 푡
are weakly station-
ary so thatE(퐹
## 푡
## ) =휇
## 퐹
andCov(퐹
## 푡
## ) = Σ
## 퐹
. This allows us to estimate the model
from (historical) scenarios.
## 1
For a white noise process휀
## 푡
we haveE(휀
## 푡
) =0andCov(휀
## 푡
## 1
## ,휀
## 푡
## 2
## ) = Ωif푡
## 1
## =푡
## 2
, whereΩdoes not
depend on푡, otherwise0.
## 2
IfΣ
## 휀
is not diagonal then we have anapproximatefactor model.
## 3
Additional lags of퐹
## 푡
in the푍
## 푡
equations can be easily allowed, then we obtain a dynamic factor
model.
## 37

With these assumptions, we can write the expected value of푍
## 푡
as
## 휇
## 푍
## =훼+훽휇
## 퐹
## .
The covariance matrix will be given by
## Σ
## 푍
## =훽Σ
## 퐹
## 훽
## T
## + Σ
## 휃
## .
These two equations allow the following properties:
•Number of parameters: The covariance matrixΣ
## 푍
has only푁퐾+푁+퐾(퐾+ 1)/2
parameters, which is linear in푁, in contrast to having푁(푁+ 1)/2covariances,
which is quadratic in푁.
•Risk decomposition: Because the common factors and the specific components are
uncorrelated, we can separate the risks associated with each. For a portfolioxthe
portfolio level factor exposures are given byb=훽
## T
xand we can write the total
portfolio variance asb
## T
## Σ
## 퐹
b+x
## T
## Σ
## 휃
x.
•While the factor structure may introduce a bias on the covariance estimator, it will
also lower its variance owing to the reduced number of parameters to estimate.
5.2 Classes of factor models
5.2.1 Explicit factor models
In these models the factors are predefined based on financial or economic theory, indepen-
dently from the data. They are observed from e. g. macroeconomic quantities (inflation,
economic growth, etc.) or from security characteristics (industry, dividend yield, market
capitalization, etc.) [Con95]. The goal of these models is typically to explain security
returns. A drawback of explicit factor models is the misspecification risk. The derivation
of the covariance matrixΣ
## 푍
strongly relies on the orthogonality between the factors퐹
## 푡
and the residuals휃
## 푡
, which might not be satisfied if relevant factors are missing from the
model.
Macroeconomic models
In the case ofmacroeconomic factor modelswe observe the historical factor time-series
Fand apply time-series regression to get estimators for훽,훼, and휀. However, enough
stationary data must be available for an accurate regression.
The simplest macroeconomic factor models use a single factor as common risk compo-
nent. In Sharpe’s single factor model this common factor is the market risk. In practice,
we can approximate the market risk factor using the returns of a stock index, by either
forming an equally-weighted or a market capitalization-weighted portfolio of the index
constituents. The covariance matrix with single factor model structure has only2푁+ 1
parameters to estimate.
## 38

Fundamental models
There are two methods to estimatefundamental factor models:
•BARRA method: We compute the estimate훽of the훽from the observed security
specific attributes (assumed to be time invariant). Then we do cross-sectional re-
gression for each time instant푡to obtain the factor time-seriesFand its estimated
covariance matrixΣ
## 퐹
## :F
## 푡
## = (훽
## T
## Σ
## −1
## 휃
## 훽)
## −1
## 훽
## T
## Σ
## −1
## 휃
## Z
## 푡
, whereΣ
## 휃
is the diagonal ma-
trix of estimated specific variances. It is there to take into account cross-sectional
heteroskedasticity in the model.
•Fama–French method: For each time푡we order the securities into quintiles by a
given security attribute. Then we long the the top quintile and short the bottom
quintile.  The factor realization at time푡corresponding to the chosen attribute
will be the return of this hedged portfolio. After obtaining the factor time-series
corresponding to each attribute, we can estimate훽using time-series regression.
5.2.2 Implicit factor models
Implicit factor models derive both the factors and the factor exposures from the data, so
these does not need any external input. However, the statistical estimation procedures
involved are prone to discovering spurious correlations, and they can only work if we
assume the factor exposures to be time invariant over the estimation period. Also, implicit
factors do not have financial interpretation. Mainly two methods are used to derive the
factors.
Factor analysis
This method assumes a more specific structure, anormal factor modelthat has the
additional requirementsE(퐹
## 푡
) =0andCov(퐹
## 푡
## ) =I.
•To satisfy the first condition, we redefine훼
## ′
## =훼+훽E(퐹
## 푡
## ).
•To satisfy the second condition, we observe that the variables훽andF
## 푡
can only
be determined up to an invertible matrixH, because훽F
## 푡
## =훽H
## −1
## HF
## 푡
. Thus we
decompose the factor covariance asΣ
## 퐹
## =QQ
## T
and chooseH=Q
## −1
to arrive at
the desired structure.
The covariance matrix will then becomeΣ
## 푍
## =훽훽
## T
## + Σ
## 휃
.  The matrixQis still
determined only up to a rotation. This freedom can help in finding interpretation for the
factors.
Further assuming that the variables푍
## 푡
are independent and identically normally
distributed, we can compute estimates훼,훽, andΣ
## 휃
using maximum likelihood
method.  Then we use cross-sectional regression to estimate the factor time-series:
## F
## 푡
## =  (훽
## T
## Σ
## −1
## 휃
## 훽)
## −1
## 훽
## T
## Σ
## −1
## 휃
## (z
## 푡
−훼).  Here we usedΣ
## −1
## 휃
as weighting to address cross-
sectional heteroskedasticity in휀
## 푡
## .
The number of factors can be determined e.  g.  using likelihood ratio test.  The
drawback of factor analysis is that it is not efficient for large problems.
## 39

## Principal Component Analysis
## Definition
Principal component analysis(PCA) is an affine dimension reduction method. Let us
define factors (calledprincipal components) through퐹
## 푡
=d+A푍
## 푡
, assumingE(퐹
## 푡
## ) =0,
anddim(퐹
## 푡
) =퐾 < 푁= dim(푍
## 푡
). Then we can approximate푍
## 푡
with
## ̃
## 푍
## 푡
## =훼+훽퐹
## 푡
## . The
best such approximation is obtained by the eigendecompositionΣ
## 푍
## =VΛV
## T
, where the
matrixΛis diagonal with the eigenvalues휆
## 1
## ,...,휆
## 푁
in it ordered from largest to smallest,
and the matrixVcontains the corresponding eigenvectorsv
## 1
## ,...,v
## 푁
as columns.
If we partition the eigenvector matrix asV= [V
## 퐾
## ,V
## 푁−퐾
], whereV
## 퐾
consists of the
first퐾eigenvectors, we can construct the solution:
## 훽=V
## 퐾
## ,
## 훼=E(푍
## 푡
## ),
## F
## 푡
## =V
## T
## 퐾
## (푍
## 푡
## −E(푍
## 푡
## )),
## 휀
## 푡
## =푍
## 푡
## −
## ̃
## 푍
## 푡
## =V
## 푁−퐾
## V
## T
## 푁−퐾
## (푍
## 푡
## −E(푍
## 푡
## )).
Note that for휀
## 푡
we haveE(휀
## 푡
) =0andCov(퐹
## 푡
## ,휀
## 푡
) =0, as required in the factor model
definition. Also the factors will be uncorrelated:Σ
## 퐹
## =
## 1
## 푇
## 퐹
## 푡
## 퐹
## T
## 푡
## = Λ
## 퐾
, containing the first
퐾eigenvalues in the diagonal.
Intuitively PCA does an orthogonal projection of푍
## 푡
onto the hyperplane spanned by
the퐾directions corresponding to the퐾largest eigenvalues. This way the projection
## ̃
## 푍
## 푡
contains the most randomness of the original variable푍
## 푡
that an affine transformation
can preserve. The eigenvalue휆
## 푖
measures the randomness of principal component퐹
## 푡,푖
## ,
the randomness of푍
## 푡
along the directionv
## 푖
. The ratio
## ∑︀
## 퐾
## 푖=1
## 휆
## 푖
## /
## ∑︀
## 푁
## 푖=1
## 휆
## 푖
is the fraction
of randomness explained by the factor model approximation.
Advantages of PCA based factor models is that they are computationally simple, they
need no external data, and that they avoid misspecification risk because the residuals and
the factors are orthogonal by construction. Also they yield factors ranked according to
their fraction of explained variance, which can help determining the number of factors퐾
to use.
Number of factors
In practice, the number of factors퐾is unknown and has to be estimated. Too few
factors reduce the explanatory power of the model, too many could lead to retaining
insignificant factors. In [BN01] the authors propose an information criteria to estimate
## 퐾:
## 퐾
## *
= argmin
## 퐾
log
## (︀
## 휀
## 푇
## 퐾
## 휀
## 퐾
## )︀
## +퐾
## (︂
## 푁+푇
## 푁푇
## )︂
log
## (︂
## 푁푇
## 푁+푇
## )︂
## ,
where휀
## 퐾
is the vector of residuals in the case of퐾factors.
If we wish to keep the number of factors time invariant, then a heuristic method can
help:퐾=⌊log(푁)⌋.
## 40

PCA on the correlation matrix
We can also do PCA on the correlation matrix:
•We get the correlation matrixΩ
## 푍
from the covariance matrixΣ
## 푍
byΩ
## 푍
## =
## D
## −1/2
## Σ
## 푍
## D
## −1/2
, whereD= Diag(Σ
## 푍
## ).
•Then we keep only the퐾largest eigenvalues:
## ̃
## Ω
## 푍
## =V
## 퐾
## Λ
## 퐾
## V
## T
## 퐾
## .
•To guarantee that this approximation will also be a correlation matrix, we add a
diagonal correction termDiag
## (︁
## I−
## ̃
## Ω
## 푍
## )︁
## .
•Finally, we transform the result back into a covariance matrix.
This method can give better performance when the scale of data variables is very
different.
Practical considerations
In practice, PCA relies on the assumption that the number of observations푇is large
relative to the number of securities푁. If this does not hold, i. e.,푁 > 푇, then we can
do PCA in a different way. Suppose thatZis the푁×푇data matrix, and휇is the mean
of the data. Then
•We do eigendecomposition on the푇×푇matrix
## 1
## 푁
## (Z−휇1
## T
## )
## T
## (Z−휇1
## T
## ) =WΛW
## T
## .
•We get the principal component matrix asF= ΛW
## T
## .
The most efficient way to compute PCA is to use singular value decomposition (SVD)
directly on the data matrixZ. Then we getZ=VΛW
## T
. Now it is easy to see the
connection between the two PCA approaches:
## F=V
## T
## Z=V
## T
## VΛW
## T
## = ΛW
## T
## .
5.3 Portfolio optimization with factor model
## 5.3.1 Sparsity
Suppose we have the decomposition of the covariance matrixΣ
## 푍
## =훽Σ
## 퐹
## 훽
## T
## +Σ
## 휃
, where
## Σ
## 퐹
is the퐾×퐾sample factor covariance matrix and퐾is the number of factors.
Typically we have only a few factors, so퐾≪푁and thusΣ
## 퐹
is much lower dimensional
than the푁×푁matrixΣ
## 푍
.  This makes it much cheaper to find the decomposition
## Σ
## 퐹
## =FF
## T
, and consequently the factorizationΣ
## 푍
## =GG
## T
, where
## G=
## [︁
## 훽F   Σ
## 1/2
## 휃
## ]︁
## .(5.1)
This form ofGis typically very sparse. In practice sparsity is more important than the
number of variables and constraints in determining the computational efficiency of the
optimization problem. Thus it can be beneficial to focus on the number of nonzeros in the
matrixGand try to reduce it. Indeed, the푁×(푁+퐾)dimensionalGis larger than the
## 41

푁×푁dimensional Cholesky factor ofΣ
## 푍
would be, but inGthere are only푁(퐾+ 1)
nonzeros in contrast to the푁(푁+ 1)/2nonzeros in the Cholesky factor.  Because in
practice퐾tends to be a small number independent of푁, we can conclude that the usage
of a factor model reduced the number of nonzeros, and thus the storage requirement by
a factor of푁. This will in most cases also lead to a significant reduction in the solution
time.
5.3.2 Modeling risk terms
In the risk minimization setting (2.1) of the Markowitz problem, according to Sec. 13.1.1
we can model the factor risk termx
## T
## 훽Σ
## 퐹
## 훽
## T
x≤푡
## 1
as(
## 1
## 2
## ,푡
## 1
## ,F
## T
## 훽
## T
x)∈ 풬
## 퐾+2
, and the
specific risk termx
## T
## Σ
## 휃
x≤푡
## 2
as(
## 1
## 2
## ,푡
## 2
## ,Σ
## 1/2
## 휃
x)∈ 풬
## 푁+2
. The latter can be written in a
computationally more favorable way as
## (︁
## 1
## 2
## ,푡
## 2
## ,diag
## (︁
## Σ
## 1/2
## 휃
## )︁
## ∘x
## )︁
## ∈ 풬
## 푁+2
. The resulting
risk minimization problem will then look like
minimize푡
## 1
## +푡
## 2
subject to(
## 1
## 2
## ,푡
## 1
## ,F
## T
## 훽
## T
x)∈ 풬
## 퐾+2
r
## ,
## (︁
## 1
## 2
## ,푡
## 2
## ,diag
## (︁
## Σ
## 1/2
## 휃
## )︁
## ∘x
## )︁
## ∈ 풬
## 푁+2
r
## ,
## 휇
## T
x≥푟
min
## ,
x∈ ℱ.
## (5.2)
We can also have prespecified limits훾
## 1
for the factor risk and훾
## 2
for the specific risk.
Then we can use the return maximization setting:
maximize휇
## T
x
subject to(
## 1
## 2
## ,훾
## 2
## 1
## ,F
## T
## 훽
## T
x)∈ 풬
## 퐾+2
r
## ,
## (︁
## 1
## 2
## ,훾
## 2
## 2
## ,diag
## (︁
## Σ
## 1/2
## 휃
## )︁
## ∘x
## )︁
## ∈ 풬
## 푁+2
r
## ,
x∈ ℱ.
## (5.3)
5.4 Shrinkage as factor model
In section Sec. 4.2.1 we discussed that shrinkage is a regularization scheme, useful in
handling the inaccuracy in the covariance matrix estimate (the sample covariance matrix
can be singular and also its offdiagonal elements can be out-of-sample unstable).  We
can also look at the shrinkage of the covariance matrix as a factor model [Kak16]. This
requires that the target matrixBis also written as factor model:
## B=훽Σ
## 퐹
## 훽
## T
## +Σ
## 휃
## ,
where the number of factors퐾should be퐾≪푁so that the factor covarianceΣ
## 퐹
is
more stable than the sample covarianceΣ
sam
. Note that all three targets in section Sec.
4.2.1 are given in this form.
We also assume that the sample covariance is decomposed into principal components
## Σ
sam
## =V
## 퐿
## Λ
## 퐿
## V
## T
## 퐿
, where some eigenvalues could be zero because of possible singularity,
so in general we assume퐿 < 푁nonzero eigenvalues.
Then, applying (4.4) the shrunk matrix can be expressed as the factor model
## Σ
shrunk
## =
## ̃
## 훽
## ̃
## Σ
## 퐹
## ̃
## 훽
## T
## +
## ̃
## Σ
## 휃
## ,
## 42

where the components are block matrices
## ̃
## Σ
## 휃
## =훼Σ
## 휃
## ,
## ̃
## 훽=
## [︀
## 훽V
## 퐿
## ]︀
## ,
## ̃
## Σ
## 퐹
## =
## [︂
## 훼Σ
## 퐹
## 0
## 0(1−훼)Λ
## 퐿
## ]︂
## .
We can further improve this model by dropping some of the “noisy” principal components,
and keep only
## ˆ
퐿 < 퐿eigenvalues, thus making the shrunk covariance more stable. We
consider the matrix
## Σ
shrunk
## =V
## ^
## 퐿
## Λ
## ^
## 퐿
## V
## T
## ^
## 퐿
## +cc
## T
## ∘B.
## (5.4)
Instead of using a shrinkage coefficient, here we require thatdiag(Σ
shrunk
) = diag(Σ
sam
## ),
which is a reasonable requirement, and determinesc:푐
## 2
## 푖
## =
## 1
## 푏
## 푖,푖
## ∑︀
## 퐿
## 푙=
## ^
## 퐿+1
## 휆
## 푙
## 푣
## 2
## 푖,푙
, where푏
## 푖,푖
is
a diagonal element ofBand푣
## 푖,푙
is an element ofV
## 퐿
. Note that (5.4) is a factor model,
ifBis a factor model.
## 4
So we arrived at another regularization scheme, which improves stability of the co-
variance matrix estimate. This method is also useful for combining principal components
with fundamental factors.
## 5.5 Example
In this chapter there are two examples. The first shows the application of macroeconomic
factor models on the case study developed in the preceding chapters. The second example
demonstrates the performance gain that factor models can yield on a large scale portfolio
optimization problem.
5.5.1 Single factor model
In the example in Sec. 4.5 we have seen that the effective dimension
## ̃
푁is low, indicating
that there are only one or two independent sources of risk for all securities. This suggests
that a single factor model might give a good approximation of the covariance matrix. In
this example we will use the return of the SPY ETF as market factor. The SPY tracks
the S&P 500 index and thus is a good proxy for the U.S. stock market. Then our model
will be:
## 푅
## 푡
## =훼+훽푅
## M,푡
## +휀
## 푡
## ,
where푅
## M
is the return of the market factor. To estimate this model using time-series
regression, we need to obtain scenarios of linear returns on the investment time horizon
(ℎ= 1year in this example), both for the individual securities and for SPY.
To get this, we add SPY as the ninth security, and proceed exactly the same way as
in Sec. 3.4 up to the point where we have the expected yearly logarithmic return vector
## 휇
log
## ℎ
and covariance matrixΣ
log
## ℎ
. Then we generate Monte Carlo scenarios using these
parameters.
## 4
This is becausecc
## T
## ∘(훽Σ
## 퐹
## 훽
## T
## +Σ
## 휃
) = [Diag(c)훽]Σ
## 퐹
[Diag(c)훽]
## T
+ Diag(c∘c)Σ
## 휃
## .
## 43

scenarios_log = \
np.random.default_rng().multivariate_normal(m_log, S_log, 100000)
Next, we convert the scenarios to linear returns:
scenarios_lin = np.exp(scenarios_log) - 1
Then we do the linear regression using theOLSclass of thestatsmodelspackage. The
independent variableXwill contain the scenarios for the market returns and a constant
term. The dependent variableywill be the scenarios for one of the security returns.
params = []
resid = []
X = np.zeros((scenarios_lin.shape[0], 2))
X[:, 0] = scenarios_lin[:, -1]
## X[:, 1] = 1
for k in range(N):
y = scenarios_lin[:, k]
model = sm.OLS(y, X, hasconst=True).fit()
resid.append(model.resid)
params.append(model.params)
resid = np.array(resid)
params = np.array(params)
After that we derive the estimates훼,훽,푠
## 2
## M
, anddiag(Σ
## 휃
)of the parameters훼,훽,
## 휎
## 2
## M
, anddiag(Σ
## 휃
## )respectively.
a = params[:, 1]
B = params[:, 0]
s2_M = np.var(X[:, 0])
S_theta = np.cov(resid)
diag_S_theta = np.diag(S_theta)
At this point, we can compute the decomposition (5.1) of the covariance matrix:
G = np.block([[B[:, np.newaxis] * np.sqrt(s_M), np.sqrt(S_theta)]])
We can see that in this8×9matrix there are only16nonzero elements:
G = np.array([
## [0.174, 0.253, 0,      0,      0,      0,      0,      0,      0     ],
## [0.189, 0,     0.205,  0,      0,      0,      0,      0,      0     ],
## [0.171, 0,     0,      0.181,  0,      0,      0,      0,      0     ],
## [0.180, 0,     0,      0,      0.190,  0,      0,      0,      0     ],
## [0.274, 0,     0,      0,      0,      0.314,  0,      0,      0     ],
## [0.225, 0,     0,      0,      0,      0,      0.201,  0,      0     ],
## [0.221, 0,     0,      0,      0,      0,      0,      0.218,  0     ],
## [0.191, 0,     0,      0,      0,      0,      0,      0,      0.213 ]
## ])
This sparsity can considerably speed up the optimization. See the next example in
Sec. 5.5.2 for a large scale problem where this speedup is apparent.
WhileMOSEKcan handle the sparsity efficiently, we can exploit this structure also
at the model creation phase, if we handle the factor risk and specific risk parts separately,
## 44

avoiding a large matrix-vector product:
G_factor = B[:, np.newaxis] * np.sqrt(s_M)
g_specific = np.sqrt(diag_S_theta)
factor_risk = G_factor.T @ x
specific_risk = Expr.mulElm(g_specific, x)
Then we can form the risk constraint in the usual way:
M.constraint('risk', Expr.vstack(gamma2, 0.5, factor_risk, specific_risk),
Domain.inRotatedQCone())
Finally, we compute the efficient frontier in the following points:
deltas = np.logspace(start=-1, stop=1.5, num=20)[::-1]
If we plot the efficient frontier on Fig. 5.1, and the portfolio composition on Fig. 5.2
we can compare the results obtained with and without using a factor model.
Fig. 5.1: The efficient frontier.
## 45

Fig. 5.2: Portfolio compositionxwith varying level if risk-aversion훿.
5.5.2 Large scale factor model
In this example we will generate Monte Carlo based return data and compare optimization
runtime between the Cholesky decomposition based and factor model based representa-
tion of the covariance matrix.
The following function generates the data, and the factor model:
def random_factor_model(N, K, T):
# Generate K uncorrelated, zero mean factors, with weighted variance
S_F = np.diag(range(1, K + 1))
rng = np.random.default_rng(seed=1)
Z_F = rng.multivariate_normal(np.zeros(K), S_F, T).T
# Generate random factor model parameters
B = rng.normal(size=(N, K))
a = rng.normal(loc=1, size=(N, 1))
e = rng.multivariate_normal(np.zeros(N), np.eye(N), T).T
# Generate N time-series from the factors
Z = a + B @ Z_F + e
# Residual covariance
S_theta = np.cov(e)
diag_S_theta = np.diag(S_theta)
(continues on next page)
## 46

(continued from previous page)
# Optimization parameters
m = np.mean(Z, axis=1)
S = np.cov(Z)
return m, S, B, S_F, diag_S_theta
The following code computes the comparison by increasing the number of securities
푁. The factor model in this example will have퐾= 10common factors, which is kept
constant, because it typically does not depend on푁.
# Risk limit
gamma2 = 0.1
# Number of factors
## K = 10
# Generate runtime data
list_runtimes_orig = []
list_runtimes_factor = []
for n in range(5, 15):
## N = 2**n
## T = N + 2**(n-1)
m, S, B, S_F, diag_S_theta = random_factor_model(N, K, T)
F = np.linalg.cholesky(S_F)
## G_factor = B @ F
g_specific = np.sqrt(diag_S_theta)
G_orig = np.linalg.cholesky(S)
optimum_orig, runtime_orig = Markowitz(N, m, G_orig, gamma2)
optimum_factor, runtime_factor = \
Markowitz(N, m, (G_factor, g_specific), gamma2)
list_runtimes_orig.append((N, runtime_orig))
list_runtimes_factor.append((N, runtime_factor))
tup_N_orig, tup_time_orig = list(zip(*list_runtimes_orig))
tup_N_factor, tup_time_factor = list(zip(*list_runtimes_factor))
The function callMarkowitz(N, m, G, gamma2)runs the Fusion model, the same way
as in Sec. 2.4. If instead of the argumentGwe specify the tuple(G_factor, g_specific),
then the risk constraint in the Fusion model is created such that it exploits the risk factor
structure:
# M is the Fusion model object
factor_risk = G_factor.T @ x
specific_risk = Expr.mulElm(g_specific, x)
total_risk = Expr.vstack(factor_risk, specific_risk)
M.constraint('risk', Expr.vstack(gamma2**0.5, total_risk),
(continues on next page)
## 47

(continued from previous page)
Domain.inQCone())
To get the runtime of the optimization, we add the following line to the model:
time = M.getSolverDoubleInfo("optimizerTime")
The results can be seen on Fig. 5.3, showing that the factor model based covariance
matrix modeling can result in orders of magnitude faster solution times for large scale
problems.
Fig. 5.3: Runtimes with and without using a factor model.
## 48

## Chapter 6
Transaction costs
Rebalancing a portfolio generates turnover, i. e., buying and selling of securities to change
the portfolio composition. The basic Markowitz model assumes that there are no costs
associated with trading, but in reality, turnover incurs expenses. In this chapter we extend
the basic model to take this into account in the form of transaction cost constraints. We
also show some practical constraints, which can also limit turnover through limiting
position sizes.
We can classify transaction costs into two types [WO11]:
•Fixed costsare independent of transaction volume. These include brokerage com-
missions and transfer fees.
•Variable costsdepend on the transaction volume. These comprise execution costs
such as market impact, bid/ask spread, or slippage; and opportunity costs of failed
or incomplete execution.
Note that to be able to compare transaction costs with returns and risk, we need to
aggregate them over the length of the investment time period.
In the optimization problem, let
## ̃
x=x−x
## 0
denote the change in the portfolio with
respect to the initial holdingsx
## 0
. Then in general we can take into account transaction
costs with the function퐶, where퐶(
## ̃
x)is the total transaction cost incurred by the change
## ̃
xin the portfolio. Here we assume that transaction costs are separable, i.e., the total
cost is the sum of the costs associated with each security:퐶(
## ̃
x) =
## ∑︀
## 푛
## 푖=1
## 퐶
## 푖
## ( ̃푥
## 푖
), where
the function퐶
## 푗
## ( ̃푥
## 푖
)specifies the transaction costs incurred for the change in the holdings
of security푖. We can then write the MVO model with transaction cost in the following
way:
maximize휇
## T
x
subject to1
## T
x+
## ∑︀
## 푛
## 푖=1
## 퐶
## 푖
## ( ̃푥
## 푖
## )   =1
## T
x
## 0
## ,
x
## T
## Σx≤훾
## 2
## ,
x∈ ℱ.
## (6.1)
The constraint1
## T
x+
## ∑︀
## 푛
## 푖=1
## 퐶
## 푖
## ( ̃푥
## 푖
## )  =1
## T
x
## 0
expresses theself-financingproperty of the
portfolio. This means that no external cash is put into or taken out of the portfolio, we
pay the costs from the existing portfolio components. We can e. g. assign one of the
securities to be a cash account.
## 49

6.1 Variable transaction costs
The simplest model that handles variable costs makes the assumption that costs grow
linearly with the trading volume [BBD+17, LMFB07].  We can use linear costs, for
example, to model the cost related to the bid/ask spread, slippage, borrowing or shorting
cost, or fund management fees. Let the transaction cost function for security푖be given
by
## 퐶
## 푖
## ( ̃푥
## 푖
## ) =
## {︂
## 푣
## +
## 푖
## ̃푥
## 푖
## , ̃푥
## 푖
## ≥0,
## −푣
## −
## 푖
## ̃푥
## 푖
## , ̃푥
## 푖
## <0,
where푣
## +
## 푖
and푣
## −
## 푖
are the cost rates associated with buying and selling security푖. By
introducing positive and negative part variables ̃푥
## +
## 푖
= max( ̃푥
## 푖
## ,0)and ̃푥
## −
## 푖
= max(− ̃푥
## 푖
## ,0)
we can linearize this constraint to퐶
## 푖
## ( ̃푥
## 푖
## ) =푣
## +
## 푖
## ̃푥
## +
## 푖
## +푣
## −
## 푖
## ̃푥
## −
## 푖
. We can handle any piecewise
linear convex transaction cost function in a similar way. After modeling the variables ̃푥
## +
## 푖
and ̃푥
## −
## 푖
as in Sec. 13.1.1, the optimization problem will then become
maximize휇
## T
x
subject to1
## T
x+⟨v
## +
## ,
## ̃
x
## +
## ⟩+⟨v
## −
## ,
## ̃
x
## −
## ⟩=   1,
## ̃
x=
## ̃
x
## +
## −
## ̃
x
## −
## ,
## ̃
x
## +
## ,
## ̃
x
## −
## ≥0,
x
## T
## Σx≤훾
## 2
## ,
x∈ ℱ.
## (6.2)
In this model the budget constraint ensures that the variables
## ̃
x
## +
and
## ̃
x
## −
will not both
become positive in any optimal solution.
6.2 Fixed transaction costs
We can extend the previous model with fixed transaction costs. Considering fixed costs is
a way to discourage trading very small amounts, thus obtaining a sparse portfolio vector,
i. e., one that has many zero entries.
## Let푓
## +
## 푖
and푓
## −
## 푖
be the fixed costs associated with buying and selling security푖. The
extended transaction cost function is given by
## 퐶
## 푖
## ( ̃푥
## 푖
## ) =
## ⎧
## ⎨
## ⎩
## 0, ̃푥
## 푖
## = 0,
## 푓
## +
## 푖
## +푣
## +
## 푖
## ̃푥
## 푖
## , ̃푥
## 푖
## >0,
## 푓
## −
## 푖
## −푣
## −
## 푖
## ̃푥
## 푖
## , ̃푥
## 푖
## <0.
This function is not convex, but we can still formulate a mixed integer optimization
problem based on Sec. 13.2.1 by introducing new variables. Lety
## +
andy
## −
be binary
## 50

vectors. Then the optimization problem with transaction costs will become
maximize휇
## T
x
subject to1
## T
x+⟨f
## +
## ,y
## +
## ⟩+⟨f
## −
## ,y
## −
## ⟩+
## +⟨v
## +
## ,
## ̃
x
## +
## ⟩+⟨v
## −
## ,
## ̃
x
## −
## ⟩=   1,
## ̃
x=
## ̃
x
## +
## −
## ̃
x
## −
## ,
## ̃
x
## +
## ,
## ̃
x
## −
## ≥0,
## ̃
x
## +
## ≤u
## +
## ∘y
## +
## ,
## ̃
x
## −
## ≤u
## −
## ∘y
## −
## ,
y
## +
## +y
## −
## ≤1,
y
## +
## ,y
## −
## ∈ {0,1}
## 푁
## ,
x
## T
## Σx≤훾
## 2
## ,
x∈ ℱ,
## (6.3)
whereu
## +
andu
## −
are vectors of upper bounds on the amounts of buying and selling in
each security and∘is the elementwise product. The products푢
## +
## 푖
## 푦
## +
## 푖
and푢
## −
## 푖
## 푦
## −
## 푖
ensure
that if security푖is traded (푦
## +
## 푖
## = 1or푦
## −
## 푖
= 1), then both fixed and variable costs are
incurred, otherwise (푦
## +
## 푖
## =푦
## −
## 푖
= 0) the transaction cost is zero. Finally, the constraint
y
## +
## +y
## −
≤1ensures that the transaction for each security is either a buy or a sell, and
never both.
6.3 Market impact costs
In reality, each trade alters the price of the security. This effect is calledmarket impact. If
the traded quantity is small, the impact is negligible and we can assume that the security
prices are independent of the amounts traded.  However, for large traded volumes we
should take market impact into account.
While there is no standard model for market impact, in practice an empirical power
law is applied [GK00] [p. 452]. Let
## ̃
## 푑
## 푖
## =푑
## 푖
## −푑
## 0,푖
be the traded dollar amount for security
푖. Then the average relative price change is
## ∆푝
## 푖
## 푝
## 푖
## =±푐
## 푖
## 휎
## 푖
## (︃
## |
## ̃
## 푑
## 푖
## |
## 푞
## 푖
## )︃
## 훽−1
## ,
## (6.4)
where휎
## 푖
is the volatility of security푖for a unit time period,푞
## 푖
is the average dollar
volume in a unit time period, and the sign depends on the direction of the trade. The
number푐
## 푖
has to be calibrated, but it is usually around one. Equation (6.4) is called the
“square-root” law, because훽−1is empirically shown to be around1/2[TLD+11].
The relative price difference (6.4) is the impact cost rate, assuming
## ̃
## 푑
## 푖
dollar amount
is traded. After actually trading this amount, we get the total market impact cost as
## 퐶
## 푖
## (
## ̃
## 푑
## 푖
## ) =
## ∆푝
## 푖
## 푝
## 푖
## ̃
## 푑
## 푖
## =푎
## 푖
## |
## ̃
## 푑
## 푖
## |
## 훽
## ,
## (6.5)
where푎
## 푖
## =±푐
## 푖
## 휎
## 푖
## /푞
## 훽−1
## 푖
.  Thus if훽−1  =  1/2, the market impact cost increases with
훽= 3/2power of the traded dollar amount.
We can also express the market impact cost in terms of portfolio fraction ̃푥
## 푖
instead
of
## ̃
## 푑
## 푖
by normalizing푞
## 푖
with the total portfolio valuev
## T
p
## 0
## .
## 51

Using Sec. 13.1.1 we can model푡
## 푖
## ≥ | ̃푥
## 푖
## |
## 훽
with the power cone as(푡
## 푖
## ,1, ̃푥
## 푖
## )∈
## 풫
## 1/훽,(훽−1)/훽
## 3
. Hence, it follows that the total market impact cost term
## ∑︀
## 푁
## 푖=1
## 푎
## 푖
## | ̃푥
## 푖
## |
## 훽
can be
modeled by
## ∑︀
## 푁
## 푖=1
## 푎
## 푖
## 푡
## 푖
under the constraint(푡
## 푖
## ,1, ̃푥
## 푖
## )∈풫
## 1/훽,(훽−1)/훽
## 3
## .
Note however, that in this model nothing forces푡
## 푖
to be small as possible to ensure
## 푡
## 푖
## =| ̃푥
## 푖
## |
## 훽
holds at the optimal solution. This freedom allows the optimizer to try reducing
portfolio risk by incorrectly treating푎
## 푖
## 푡
## 푖
as a risk-free security. Then it would allocate
more weight to푎
## 푖
## 푡
## 푖
while reducing weight allocated to risky securities, basically throwing
away money.
There are two solutions, which can prevent this unwanted behavior:
•Adding a penalty term−훿
## T
tto the objective function to prevent excess growth
of the variables푡
## 푖
. We have to calibrate the hyper-parameter vector훿so that the
penalty would not become too dominant.
•Adding a risk-free security to the model.  In this case the optimizer will prefer
to allocate to the risk-free security, which has positive return (the risk-free rate),
instead of allocating to푎
## 푖
## 푡
## 푖
## .
Let us denote the weight of the risk-free security by푥
f
and the risk-free rate of return
by푟
f
. Then the portfolio optimization problem accounting for market impact costs will
be
maximize휇
## T
x+푟
f
## 푥
f
subject to1
## T
x+a
## T
t+푥
f
## =   1,
x
## T
## Σx≤훾
## 2
## ,
## (푡
## 푖
## ,1, ̃푥
## 푖
## )∈ 풫
## 1/훽,(훽−1)/훽
## 3
## , 푖= 1,...,푁,
x,푥
f
## ∈ ℱ.
## (6.6)
Note that if we model using the quadratic cone instead of the rotated quadratic cone
and a risk free security is present, then there will be no optimal portfolios for which
## 0< 푥
f
<1. The solutions will be either푥
f
= 1or some risky portfolio with푥
f
## = 0. See
a detailed discussion about this in Sec. 13.3.
6.4 Cardinality constraints
Investors often prefer portfolios with a limited number of securities. We do not need to
use all of the푁securities to achieve good diversification, and this way we can also reduce
costs significantly. We can create explicit limits to constrain the number of securities.
Suppose that we allow at most퐾coordinates of the difference vector
## ̃
x=x−x
## 0
to
be non-zero, where퐾is (much) smaller than the total number of securities푁.
We can again model this type of constraint based on Sec. 13.2.1 by introducing a
binary vectoryto indicate|
## ̃
x|̸=0, and by bounding the sum ofy. The basic Markowitz
## 52

model then gets updated as follows:
maximize휇
## T
x
subject to1
## T
x=   1,
## ̃
x=x−x
## 0
## ,
## ̃
x≤u∘y,
## ̃
x≥ −u∘y,
## 1
## T
y≤퐾,
y∈ {0,1}
## 푁
## ,
x
## T
## Σx≤훾
## 2
## ,
x∈ ℱ,
## (6.7)
where the vectoruis some a priori chosen upper bound on the amount of trading in each
security.
6.5 Buy-in threshold
In the above examples we assumed that trades can be arbitrarily small. In reality, how-
ever, it can be meaningful to place lower bounds on traded amounts to avoid unrealisti-
cally small trades and to control the transaction cost. These constraints are calledbuy-in
threshold.
## Let
## ̃
x=x−x
## 0
be the traded amount. Let also
## ̃
x
## +
= max(
## ̃
x,0)and
## ̃
x
## −
= max(−
## ̃
x,0)
be the positive and negative part of
## ̃
x. These we model according to Sec. 13.2.1. Then the
buy-in threshold basically means that
## ̃
x
## ±
## ∈ {0}∪[ℓ
## ±
## ,u
## ±
], whereℓ
## ±
andu
## ±
are vectors
of lower and upper bounds on
## ̃
x
## +
and
## ̃
x
## −
respectively.
This is a semi-continuous variable, which we can model based on Sec. 13.2.1.  We
introduce binary variablesy
## ±
and constraintsℓ
## ±
## ∘y
## ±
## ≤
## ̃
x
## ±
## ≤u
## ±
## ∘y
## ±
. The optimization
problem would then become a mixed integer problem of the form
maximize휇
## T
x
subject to1
## T
x=   1,
x−x
## 0
## =
## ̃
x
## +
## −
## ̃
x
## −
## ,
## ̃
x
## +
## ,
## ̃
x
## −
## ≥0,
## ̃
x
## +
## ≤u
## +
## ∘y
## +
## ,
## ̃
x
## +
## ≥ℓ
## +
## ∘y
## +
## ,
## ̃
x
## −
## ≤u
## −
## ∘y
## −
## ,
## ̃
x
## −
## ≥ℓ
## −
## ∘y
## −
## ,
y
## +
## +y
## −
## ≤1,
y
## +
## ,y
## −
## ∈ {0,1}
## 푁
## ,
x
## T
## Σx≤훾
## 2
## ,
x∈ ℱ.
## (6.8)
This model is of course compatible with the fixed plus linear transaction cost model
discussed in Sec. 6.2.
## 53

## 6.6 Example
In this chapter we show two examples. The first demonstrates the modeling of market
impact through the use of the power cone, while the second example presents fixed and
variable transaction costs and the buy-in threshold.
6.6.1 Market impact model
As a starting point, we refer back to problem (2.13). We will extend this problem with
the market impact cost model. To compute the coefficients푎
## 푖
in formula (6.5), we assume
that daily volume data is also available in the dataframedf_volumes. We also compute
the mean of the daily volumes, and the daily volatility for each security as the standard
deviation of daily linear returns:
# Compute average daily volume and daily volatility (std. dev.)
df_lin_returns = df_prices.pct_change()
vty = df_lin_returns.std()
vol = (df_volumes * df_prices).mean()
According  to  the  data,   the  average  daily  dollar  volumes  are10
## 8
## ·
[3.9883,4.2416,6.0054,4.2584,30.4647,34.5619,5.0077,8.4950], and the daily volatilities
are[0.0164,0.0154,0.0146,0.0155,0.0191,0.0173,0.0186,0.0169].  Thus in this example
we will choose the size of our portfolio to be10billion dollars so that we can see a
significant market impact.
Then we update the Fusion model introduced in Sec. 2.4.2 with new variables and
constraints:
def EfficientFrontier(N, m, G, deltas, a, beta, rf):
with Model("MarketImpact") as M:
## # Variables
# The variable x is the fraction of holdings in each security.
# x must be positive, this imposes the no short-selling constraint.
x = M.variable("x", N, Domain.greaterThan(0.0))
# Variable for risk-free security (cash account)
xf = M.variable("xf", 1, Domain.greaterThan(0.0))
# The variable s models the portfolio variance term in the objective.
s = M.variable("s", 1, Domain.unbounded())
# Auxiliary variable to model market impact
t = M.variable("t", N, Domain.unbounded())
# Budget constraint with transaction cost terms
M.constraint('budget', Expr.sum(x) + xf + t.T @ a == 1.0)
# Power cone to model market impact
M.constraint('mkt_impact', Expr.hstack(t, Expr.constTerm(N, 1.0), x),
Domain.inPPowerCone(1.0 / beta))
(continues on next page)
## 54

(continued from previous page)
# Objective (quadratic utility version)
delta = M.parameter()
M.objective('obj', ObjectiveSense.Maximize,
x.T @ m + rf * xf - delta * s)
# Conic constraint for the portfolio variance
M.constraint('risk', Expr.vstack(s, 1, G.T @ x),
Domain.inRotatedQCone())
columns = ["delta", "obj", "return", "risk", "t_resid",
"x_sum", "xf", "tcost"] + df_prices.columns.tolist()
df_result = pd.DataFrame(columns=columns)
for d in deltas:
# Update parameter
delta.setValue(d)
# Solve optimization
## M.solve()
# Save results
portfolio_return = m @ x.level() + np.array([rf]) @ xf.level()
portfolio_risk = np.sqrt(2 * s.level()[0])
t_resid = t.level() - np.abs(x.level())**beta
row = pd.Series([d, M.primalObjValue(), portfolio_return,
portfolio_risk, sum(t_resid), sum(x.level()),
sum(xf.level()), t.level() @ a] + \
list(x.level()), index=columns)
df_result = df_result.append(row, ignore_index=True)
return df_result
The new rows are:
•The row for the variable푥
f
, which represents the weight allocated to the cash
account. The annual return on it is assumed to be푟
f
= 1%. We constrain푥
f
to be
positive, meaning that borrowing money is not allowed.
•The row for the auxiliary variablet.
•The row for the market impact constraint modeled using the power cone.
We modified the budget constraints to include푥
f
and the market impact costa
## T
t.
The objective also contains the risk-free part of portfolio return푟
f
## 푥
f
## .
In this example, we start with100%cash, meaning that푥
f
## 0
## = 1andx
## 0
## =0. Trans-
action cost is thus incurred for the total weightx.
Next, we compute the efficient frontier with and without market impact costs. We
select훽= 3/2and푐
## 푖
= 1. The following code produces the results:
deltas = np.logspace(start=-0.5, stop=2, num=20)[::-1]
portfolio_value = 10**10
(continues on next page)
## 55

(continued from previous page)
rel_vol = vol / portfolio_value
a1 = np.zeros(N)
a2 = (c * vty / rel_vol**(beta - 1)).to_numpy()
ax = plt.gca()
for a in [a1, a2]:
df_result = EfficientFrontier(N, m, G, deltas, a, beta, rf)
mask = df_result < 0
mask.iloc[:, :2] = False
df_result[mask] = 0
df_result.plot(ax=ax, x="risk", y="return", style="-o",
xlabel="portfolio risk (std. dev.)",
ylabel="portfolio return", grid=True)
ax.legend(["return without price impact", "return with price impact"])
On Fig. 6.1 we can see the return reducing effect of market impact costs. The left
part of the efficient frontier (up to the so calledtangency portfolio) is linear because a
risk-free security was included. However, in this case borrowing is not allowed, so the
right part remains the usual parabola shape.
Fig. 6.1: The efficient frontier with risk-free security included, and market impact cost
taken into account.
## 56

6.6.2 Transaction cost models
In this example we show a problem that models fixed and variable transaction costs and
the buy-in threshold. Note that we do not model the market impact here.
We will assume now thatxcan take negative values too (short-selling is allowed), up
to the limit of30%portfolio size. This way we can see how to apply different costs to
buy and sell trades. We also assume thatx
## 0
=0, so
## ̃
x=x.
The following code defines variables used as the positive and negative part variables
ofxand the binary variablesy
## +
## ,y
## −
indicating whether there is buying or selling in a
security:
# Real variables
xp = M.variable("xp", N, Domain.greaterThan(0.0))
xm = M.variable("xm", N, Domain.greaterThan(0.0))
# Binary variables
yp = M.variable("yp", N, Domain.binary())
ym = M.variable("ym", N, Domain.binary())
Next we add two constraints. The first linksxpandxmtox, so that they represent
the positive and negative parts. The second ensures that for each coordinate ofypand
ymonly one of the values can be1.
# Constraint assigning xp and xm to the positive and negative part of x.
M.constraint('pos-neg-part', x == xp - xm)
# Exclusive buy-sell constraint
M.constraint('exclusion', yp + ym <= 1.0)
We update the budget constraint with the variable and fixed transaction cost terms.
The fixed cost of buy and sell trades are held by the variablesfpandfm. These are
typically given in dollars, and have to be divided by the total portfolio value.  The
variable cost coefficients arevpandvm. If these are given as percentages, then we do not
have to modify them.
# Budget constraint with transaction cost terms
fixcost_terms = yp.T @ fp + ym.T @ fm
varcost_terms = xp.T @ vp + xm.T @ vm
budget_terms = Expr.sum(x) + varcost_terms + fixcost_terms
M.constraint('budget', budget_terms == 1.0)
Next, the 130/30 leverage constraint is added. Note that the transaction cost terms
from the budget constraint should also appear here, otherwise the two constraints com-
bined would allow a little more leverage than intended. (The sum ofxwould not reach
1because of the cost terms, leaving more space in the leverage constraint for negative
positions.)
# Auxiliary variable for 130/30 leverage constraint
z = M.variable("z", N, Domain.unbounded())
# 130/30 leverage constraint
M.constraint('leverage-gt', z >= x)
(continues on next page)
## 57

(continued from previous page)
M.constraint('leverage-ls', z >= -x)
## M.constraint('leverage-sum',
Expr.sum(z) + varcost_terms + fixcost_terms == 1.6)
Finally, to be able to differentiate between zero allocation (not incurring fixed cost)
and nonzero allocation (incurring fixed cost), and to implement buy-in threshold, we need
bound constraint involving the binary variables:
# Bound constraints
M.constraint('ubound-p', xp <= up * yp)
M.constraint('ubound-m', xm <= um * ym)
M.constraint('lbound-p', xp >= lp * yp)
M.constraint('lbound-m', xm >= lm * ym)
The full updated model will then look like the following:
def EfficientFrontier(N, m, G, deltas, vp, vm, fp, fm, up, um,
lp, lm, pcoef):
with Model("TransactionCost") as M:
# Real variables
# The variable x is the fraction of holdings in each security.
x = M.variable("x", N, Domain.unbounded())
xp = M.variable("xp", N, Domain.greaterThan(0.0))
xm = M.variable("xm", N, Domain.greaterThan(0.0))
# Binary variables
yp = M.variable("yp", N, Domain.binary())
ym = M.variable("ym", N, Domain.binary())
# Constraint assigning xp and xm to the pos. and neg. part of x.
M.constraint('pos-neg-part', x == xp - xm)
# s models the portfolio variance term in the objective.
s = M.variable("s", 1, Domain.unbounded())
# Auxiliary variable for 130/30 leverage constraint
z = M.variable("z", N, Domain.unbounded())
# Bound constraints
M.constraint('ubound-p', xp <= up * yp)
M.constraint('ubound-m', xm <= um * ym)
M.constraint('lbound-p', xp >= lp * yp)
M.constraint('lbound-m', xm >= lm * ym)
# Exclusive buy-sell constraint
M.constraint('exclusion', yp + ym <= 1.0)
# Budget constraint with transaction cost terms
fixcost_terms = yp.T @ fp + ym.T @ fm
varcost_terms = xp.T @ vp + xm.T @ vm
(continues on next page)
## 58

(continued from previous page)
budget_terms = Expr.sum(x) + varcost_terms + fixcost_terms
M.constraint('budget', budget_terms == 1.0)
# 130/30 leverage constraint
M.constraint('leverage-gt', z >= x)
M.constraint('leverage-ls', z >= -x)
## M.constraint('leverage-sum',
Expr.sum(z) + varcost_terms + fixcost_terms == 1.6)
# Objective (quadratic utility version)
delta = M.parameter()
penalty = pcoef * Expr.sum(xp + xm)
M.objective('obj', ObjectiveSense.Maximize,
x.T @ m - penalty - delta * s)
# Conic constraint for the portfolio variance
M.constraint('risk', Expr.vstack(s, 1, G.T @ x),
Domain.inRotatedQCone())
columns = ["delta", "obj", "return", "risk", "x_sum", "tcost"] + \
df_prices.columns.tolist()
df_result = pd.DataFrame(columns=columns)
for idx, d in enumerate(deltas):
# Update parameter
delta.setValue(d)
# Solve optimization
## M.solve()
# Save results
portfolio_return = m @ x.level()
portfolio_risk = np.sqrt(2 * s.level()[0])
tcost = np.dot(vp, xp.level()) + np.dot(vm, xm.level()) + \
np.dot(fp, yp.level()) + np.dot(fm, ym.level())
row = pd.Series([d, M.primalObjValue(), portfolio_return,
portfolio_risk, sum(x.level()), tcost] + \
list(x.level()), index=columns)
df_result = df_result.append(row, ignore_index=True)
return df_result
Here we also used a penalty term in the objective to prevent excess growth of the pos-
itive part and negative part variables. The coefficient of the penalty has to be calibrated
so that we do not overpenalize.
We also have to mention that because of the binary variables, we can only solve this
as a mixed integer optimization (MIO) problem. The solution of such a problem might
not be as efficient as the solution of a problem with only continuous variables. See Sec.
13.2 for details regarding MIO problems.
We compute the efficient frontier with and without transaction costs. The following
code produces the results:
## 59

deltas = np.logspace(start=-0.5, stop=2, num=20)[::-1]
ax = plt.gca()
for a in [0, 1]:
pcoef = a * 0.03
fp = a * 0.005 * np.ones(N)# Depends on portfolio value
fm = a * 0.01 * np.ones(N)# Depends on portfolio value
vp = a * 0.01 * np.ones(N)
vm = a * 0.02 * np.ones(N)
up = 2.0
um = 2.0
lp = a * 0.05
lm = a * 0.05
df_result = EfficientFrontier(N, m, G, deltas, vp, vm, fp, fm, up, um,
lp, lm, pcoef)
df_result.plot(ax=ax, x="risk", y="return", style="-o",
xlabel="portfolio risk (std. dev.)",
ylabel="portfolio return", grid=True)
ax.legend(["return without transaction cost",
"return with transaction cost"])
On Fig. 6.2 we can see the return reducing effect of transaction costs. The overall
return is higher because of the leverage.
Fig. 6.2: The efficient frontier with transaction costs taken into account.
## 60

## Chapter 7
Benchmark relative portfolio
optimization
We often measure the performance of portfolios relative to a benchmark. The benchmark
is typically a marketindexrepresenting an asset class or some segment of the market,
and its composition is assumed known. Benchmark relative portfolio management can
have two types of strategies:activeorpassive. The passive strategy tries to replicate
the benchmark, i. e. match its performance as closely as possible. In contrast, active
management seeks to consistently beat (outperform) the benchmark (after management
fees). This section is based on [CJPT18].
7.1 Active return
Let the portfolio and benchmark weights bexandx
bm
. In active management, quantities
of interest are the return and the risk relative to the benchmark. Theactive portfolio
return(return above the benchmark return) is
## 푅
x
a
## =x
## T
a
## 푅=x
## T
## 푅−x
## T
bm
## 푅=푅
x
## −푅
x
bm
## ,
wherex
a
## =x−x
bm
is theactive holdingsof the portfolio.
Theactive portfolio riskortracking errorwill be the standard deviation of active
return:
## 휎
x
a
## (푅
x
## ,푅
x
bm
## ) =
## √︀
x
## T
a
## Σx
a
## ,
whereΣis the covariance matrix of return. The tracking error measures how close the
portfolio return is to the benchmark return.  Outperforming the benchmark involves
additional risk; if the tracking error is zero then there cannot be any active return at all.
In general we can construct a class of functions for the purpose of measuring tracking
error differently, from any deviation measure. See in Sec. 8.
## 61

7.2 Factor model on active returns
In the active return there is still a systematic component attributable to the benchmark.
We can account for that using a single factor model. First we create a factor model for
security returns:
## 푅=훽푅
x
bm
## +휃,
where훽
## 푖
## =  Cov(푅
## 푖
## ,푅
x
bm
)/Var(푅
x
bm
)is the exposure of security푖to the benchmark,
Cov(휃) =0,Cov(푅
x
bm
## ,휃
## 푖
) = 0, andE(휃
## 푖
## ) =훼
## 푖
is the expected residual return. Under
this model, the covariance matrix of푅will be
## Σ =훽
## T
## 훽휎
## 2
x
bm
## + Σ
## 휃
## ,
where휎
## 2
x
bm
is the benchmark variance andΣ
## 휃
is the residual covariance matrix.
This factor model allows us to decompose the portfolio return into a systematic com-
ponent, which is explained by the benchmark, and a residual component, which is specific
to the portfolio:
## 푅
x
## =훽
x
## 푅
x
bm
## +휃
x
## ,
where훽
x
## =훽
## T
x,휃
x
## =휃
## T
x, and훼
x
## =훼
## T
x=E(휃
x
## ).
Finally, by subtracting the benchmark return from both sides we can write the active
return as:
## 푅
x
a
## = (훽
x
## −1)푅
x
bm
## +휃
x
## ,
where훽
x
−1is theactive beta. After computing the variance of the decomposed active
return, we can also write the square of the tracking error as
## 휎
## 2
x
a
## (푅
x
## ,푅
x
bm
## ) = (훽
x
## −1)
## 2
## 휎
## 2
x
bm
## +휔
## 2
x
## ,
where휎
## 2
x
bm
## = Var(푅
x
bm
), and휔
## 2
x
## = Var(휃
x
)is the residual risk.
We must note that if a different factor model is used to forecast risk and alpha
(which is often the case in practice), there could be factors included in one model but
not included in the other model.  The optimizer will interpret such misalignments as
factor return without risk or factor risk without return and it will exploit them as false
opportunities, leading to unintended biases in the results. Risk and alpha factors are
consideredalignedif alpha can be written as a linear combination of the risk factors. In
case of a misalignment, there are different approaches to mitigate it [KS13].
## 7.3 Optimization
An active investment strategy would try to gain higher portfolio alpha훼
x
at the cost
of accepting a higher tracking error. It follows that portfolio optimization with respect
to a benchmark will optimize the tradeoff between portfolio alpha and the square of the
tracking error.  Additional constrains specific to such problems can be bounds on the
## 62

portfolio active beta or on the active holdings. We can see examples in the following
model:
maximize훼
## T
x
subject to(x−x
bm
## )
## T
## Σ(x−x
bm
## )≤훾
## 2
## TE
## ,
x−x
bm
## ≥l
h
## ,
x−x
bm
## ≤u
h
## ,
## 훽
x
## −1≥l
## 훽
## ,
## 훽
x
## −1≤u
## 훽
## ,
x∈ ℱ,
## (7.1)
where훼and훽are estimates of훼and훽. To compute these estimates, we can do a linear
regression. However, this tends to overestimate the betas of stocks with high benchmark
exposure and underestimate the betas of the stocks with low benchmark exposure. To
improve the estimation, shrinkage towards one (the beta of the benchmark) can be helpful:
## 훽
shrunk
## = (1−푐)훽+푐1,
where we must estimate the optimal shrinkage factor푐.
## 7.4 Extensions
7.4.1 Variance constraint
Optimization of alpha with constraining only the tracking error can increase total port-
folio risk.  According to [Jor04] it can be helpful to constrain also the total portfolio
variance, especially in cases when the benchmark portfolio is relatively inefficient:
maximize훼
## T
x
subject to(x−x
bm
## )
## T
## Σ(x−x
bm
## )≤훾
## 2
## TE
## ,
x
## T
## Σx≤훾
## 2
## ,
x∈ ℱ.
## (7.2)
7.4.2 Passive management
In the case of passive management, the goal of optimization is to construct a benchmark
tracking portfolio, i. e., to have a tracking error as small as possible, given the constraints.
This usually also means that훼
x
= 0. Of course without constraints or trading costs, the
optimal solution is the benchmark index. Therefore optimization in passive management
may only be useful when constraints are needed or liquidity issues are important [MM08].
7.4.3 Linear tracking error measures
The tracking error is one possible measure of closeness between the portfolio and the
benchmark. However, there can be other measures [RWZ99]. For example, we can use the
mean absolute deviation(MAD) measure, i. e.,E(|푅
x
## −푅
x
bm
|). Advantage of this measure
is its better robustness against outliers in the data. Applying scenario approximation to
the expectation we get
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## ⃒
## ⃒
r
## T
## 푘
## (x−x
bm
## )
## ⃒
## ⃒
. After modeling the absolute value function
## 63

(see Sec. 13.1.1), we can formulate the benchmark tracking problem with this measure
as an LO model:
maximize
x,t
## 훼
## T
x
subject to
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 푡
## 푘
## ≤훾,
t+R
## T
## (x−x
bm
## )≥0,
t−R
## T
## (x−x
bm
## )≥0,
x∈ ℱ,
## (7.3)
whereRis the return data matrix with one observationr
## 푘
, 푘= 1,...,푇in each column.
If the investor perceives risk as portfolio return being below the benchmark return,
we can also use downside deviation measures. One example is thelower partial moment
## LPM
## 1
measure:E(max(−푅
x
## +푅
x
bm
,0)). The scenario approximation of this expectation
will be
## 1
## 푇
## ∑︀
## 푇
## 푘=1
max
## (︀
## −r
## T
## 푘
## (x−x
bm
## ),0
## )︀
. After modeling the maximum (see Sec. 13.1.1)
by defining a new variable푡
## −
## 푘
= max
## (︀
## −r
## T
## 푘
## (x−x
bm
## ),0
## )︀
, we can solve the problem as an
## LO:
maximize훼
## T
x
subject to
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 푡
## −
## 푘
## ≤훾,
t
## −
## ≥ −R
## T
## (x−x
bm
## ),
t
## −
## ≥0,
x∈ ℱ.
## (7.4)
Note that for a symmetric portfolio return distribution, this will be equivalent to the
MAD model.
Linear models might be also preferable because of their more intuitive interpretation.
By measuring the tracking error according to a linear function, the measurement unit of
the objective function is percentage instead of squared percentage.
## 7.5 Example
Here we show an example of a benchmark relative optimization problem. The benchmark
will be the equally weighted portfolio of the eight stocks from the previous examples,
thereforex
bm
=1/푁. The benchmark is created by the following code by aggregating
the price data of the eight stocks:
# Create benchmark
df_prices['bm'] = df_prices.iloc[:-2, 0:8].mean(axis=1)
Then we follow the same Monte Carlo procedure as in Sec. 5.5.1, just with the bench-
mark instead of the market factor.  This will yield scenarios of linear returns on the
investment time horizon ofℎ= 1year, so that we can compute estimates훼and훽of훼
and훽using time-series regression.
In the Fusion model, we make the following modifications:
•We define the active holdings variablex
a
## =x−x
bm
by
# Active holdings
xa = x - xbm
•We modify the constraint on risk to be the constraint on tracking error:
## 64

# Conic constraint for the portfolio variance
M.constraint('risk', Expr.vstack(s, 1, G.T @ xa),
Domain.inRotatedQCone())
•We also specify bounds on the active holdings and on the portfolio active beta:
# Constraint on active holdings
M.constraint('bound-h', xa, Domain.inRange(lh, uh))
# Constraint on portfolio active beta
port_act_beta = x.T @ B - 1
M.constraint('bound-b', port_act_beta, Domain.inRange(lb, ub))
•Finally, we modify the objective to maximize the portfolio alpha:
# Objective (quadratic utility version)
delta = M.parameter()
M.objective('obj', ObjectiveSense.Maximize, x.T @ a - delta * s)
The complete Fusion model of the optimization problem (7.1) will then be
def EfficientFrontier(N, a, B, G, xbm, deltas, uh, ub, lh, lb):
with Model("Frontier") as M:
## # Variables
# The variable x is the fraction of holdings in each security.
# Non-negative, no short-selling
x = M.variable("x", N, Domain.greaterThan(0.0))
# Active holdings
xa = x - xbm
# Portfolio variance term in the objective.
s = M.variable("s", 1, Domain.unbounded())
# Budget constraint
## M.constraint('budget_x', Expr.sum(x) == 1.0)
# Constraint on active holdings
M.constraint('bound-h', xa, Domain.inRange(lh, uh))
# Constraint on portfolio active beta
port_act_beta = x.T @ B - 1
M.constraint('bound-b', port_act_beta, Domain.inRange(lb, ub))
# Conic constraint for the portfolio variance
M.constraint('risk', Expr.vstack(s, 1, G.T @ xa),
Domain.inRotatedQCone())
# Objective (quadratic utility version)
delta = M.parameter()
(continues on next page)
## 65

(continued from previous page)
M.objective('obj', ObjectiveSense.Maximize, x.T @ a - delta * s)
# Create DataFrame to store the results. SPY is removed.
columns = ["delta", "obj", "return", "risk"] + \
df_prices.columns[:-1].tolist()
df_result = pd.DataFrame(columns=columns)
for d in deltas:
# Update parameter
delta.setValue(d);
# Solve optimization
## M.solve()
# Save results
portfolio_return = a @ x.level()
portfolio_risk = np.sqrt(2 * s.level()[0])
row = pd.Series([d, M.primalObjValue(), portfolio_return,
portfolio_risk] + \
list(x.level()), index=columns)
df_result = pd.concat([df_result, row.to_frame().T],
ignore_index=True)
return df_result
We give the input parameters and compute the efficient frontier using the following
code:
deltas = np.logspace(start=-0.5, stop=2, num=20)[::-1]
xbm = np.ones(N) / N
uh = np.ones(N) * 0.5
lh = -np.ones(N) * 0.5
ub = 0.5
lb = -0.5
df_result = EfficientFrontier(N, a, B, G, xbm, deltas, uh, ub, lh, lb)
mask = df_result < 0
mask.iloc[:, :2] = False
df_result[mask] = 0
df_result
On Fig. 7.1 we plot the efficient frontier and on Fig. 7.2 the portfolio composition.
On the latter we see that as the tracking error decreases, the portfolio gets closer to the
benchmark, i. e., the equal-weighted portfolio.
## 66

Fig. 7.1: The benchmark relative efficient frontier.
Fig. 7.2: Portfolio compositionxwith varying level if risk-aversion훿.
## 67

## Chapter 8
Other risk measures
In the definitions (2.1)-(2.4) of the classical MVO problem the variance (or standard
deviation) of portfolio return is used as the measure of risk, making computation easy
and convenient. If we assume that the portfolio return is normally distributed, then the
variance is in fact the optimal risk measure, because then MVO can take into account all
information about return. Moreover, if푇is large compared to푁, the sample mean and
covariance matrix are maximum likelihood estimates (MLE), implying that the optimal
portfolio resulting from estimated inputs will also be a MLE of the true optimal portfolio
[Lau01].
Empirical observations suggest however, that the distribution of linear return is often
skewed, and even if it is elliptically symmetric, it can have fat tails and can exhibit
tail dependence
## 1
. As the distribution moves away from normality, the performance of a
variance based portfolio estimator can quickly degrade.
No perfect risk measure exists, though.  Depending on the distribution of return,
different measures can be more appropriate in different situations, capturing different
characteristics of risk.  Return of diversified equity portfolios are often approximately
symmetric over periods of institutional interest. Options, swaps, hedge funds, and private
equity have return distributions that are unlikely to be symmetric. Also less symmetric
are distributions of fixed-income and real estate index returns, and diversified equity
portfolios over long time horizons [MM08].
The measures presented here are expectations, meaning that optimizing them would
lead to stochastic optimization problems in general. As a simplification, we consider only
their sample average approximation by assuming that a set of linear return scenarios are
given.
## 1
Tail dependence between two random variables means that their correlation is greater for more
extreme events. Typical in financial markets, where extreme events are likely to happen together for
multiple securities.
## 68

8.1 Deviation measures
This class of measures quantify the variability around the mean of the return distribution,
similar to variance. If we associate investment risk with the uncertainty of return, then
such measures could be ideal.
Let푋,푌be random variables of investment returns, and let퐷be a mapping. The
general properties that deviation measures should satisfy are [RUZ06]:
- Positivity:퐷(푋)≥0with퐷(푋) = 0only if푋=푐∈R,
- Translation invariance:퐷(푋+푐) =퐷(푋), 푐∈R,
## 3. Subadditivity:퐷(푋+푌)≤퐷(푋) +퐷(푌),
- Positive homogeneity:퐷(푐푋) =푐퐷(푋), 푐≥0
Note that positive homegeneity and subadditivity imply theconvexityof퐷.
8.1.1 Robust statistics
A group of deviation measures are robust statistics. Maximum likelihood estimators are
highly sensitive to deviations from the assumed distribution. Thus if the return is not
normally distributed, robust portfolio estimators can be an alternative. These are less
efficient than MLE for normal distribution, but their performance degrades less quickly
under departures from normality. One suitable class of estimators to express portfolio
risk are M-estimators [VD09]:
## 퐷
## 훿
## (푅
x
) = min
## 푞
## E[훿(푅
x
## −푞)],
where훿is a convex loss function with unique minimum at zero. It has the sample average
approximationmin
## 푞
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 훿(x
## T
r
## 푘
## −푞).
## Variance
## Choosing훿
var
## (푦) =
## 1
## 2
## 푦
## 2
we get퐷
## 훿
var
, a different expression for the portfolio variance. The
optimal푞in this case is the portfolio mean return휇
x
. This gives us a way to perform
standard mean–variance optimization directly using scenario data, without the need for
a sample covariance matrix:
minimize
## 1
## 2푇
## ∑︀
## 푇
## 푘=1
## (x
## T
r
## 푘
## −푞)
## 2
subject tox∈ ℱ.
## (8.1)
By defining new variables푡
## +
## 푘
=  max
## (︀
x
## T
r
## 푘
## −푞,0
## )︀
and푡
## −
## 푘
=  max
## (︀
## −x
## T
r
## 푘
## +푞,0
## )︀
, then
using Sec. 13.1.1 we arrive at a QO model:
minimize
## 1
## 2푇
## ‖t
## +
## ‖
## 2
## +
## 1
## 2푇
## ‖t
## −
## ‖
## 2
x
## T
## R−푞=t
## +
## −t
## −
## ,
t
## +
## ,t
## −
## ≥0,
subject tox∈ ℱ,
## (8.2)
whereR=  [r
## 1
## ,...,r
## 푇
]is the scenario matrix, where each column is a scenario.  The
norms can be further modeled by the rotated quadratic cone; see in Sec. 13.1.1. While
this formulation does not need covariance estimation, it can still suffer from computational
inefficiency because the number of variables and the number of constraints depend on the
sample size푇.
## 69

## 훼-shortfall
## Choosing훿
sf,훼
(푦)   =훼푦−min(푦,0)or equivalently훿
sf,훼
## (푦)   =훼max(푦,0)  +  (1−
훼)max(−푦,0)for훼∈(0,1)will give the훼-shortfall퐷
## 훿
sf,훼
studied in [Lau01].  The
optimal푞will be the훼-quantile of the portfolio return.훼-shortfall is a deviation mea-
sure with favorable robustness properties when the portfolio return has an asymmetric
distribution, fat tailed symmetric distribution, or exhibits multivariate tail-dependence.
The훼parameter adjusts the level of asymmetry in the훿function, allowing us to penalize
upside and downside returns differently.
Portfolio optimization using sample훼-shortfall can be formulated as
minimize
## 훼
## 푇
## ∑︀
## 푇
## 푘=1
## (x
## T
r
## 푘
## −푞)−
## 1
## 푇
## ∑︀
## 푇
## 푘=1
min(x
## T
r
## 푘
## −푞,0)
subject tox∈ ℱ
## (8.3)
By defining new variables푡
## −
## 푘
= max(−x
## T
r
## 푘
+푞,0), and model accoring to Sec. 13.1.1 we
arrive at an LO model:
minimize훼(x
## T
## 휇−푞) +
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 푡
## −
## 푘
t
## −
## ≥ −x
## T
r
## 푘
## +푞,
t
## −
## ≥0,
subject tox∈ ℱ.
## (8.4)
A drawback of this model is that the number of constraints depends on the sample size
푇, resulting in computational inefficiency for large number of samples.
For elliptically symmetric return distributions the훼-shortfall is equivalent to the
variance in the sense that the corresponding sample portfolio estimators will be estimating
the same portfolio. In fact for normal distribution, the훼-shortfallis proportional to the
portfolio variance:퐷
## 훿
sf,훼
## =
## 휑(푞
## 훼
## )
## 훼
## √︀
## 퐷
## 훿
var
, where휑(푞
## 훼
)is the value of the standard normal
density function at its훼-quantile.
However when return is symmetric but not normally distributed, the sample portfolio
estimators for훼-shortfall can have less estimation error than sample portfolio estimators
for variance.
## MAD
A special case of훼-shortfall is for훼= 0.5. The function훿
## MAD
## (푦) =
## 1
## 2
|푦|gives us퐷
## 훿
## MAD
## ,
which is called themean absolute deviation(MAD) measure or the퐿
## 1
-risk. For this case
the optimal푞will be the median of the portfolio return, and the sample MAD portfolio
optimization problem can be formulated as
minimize
## 1
## 2푇
## ∑︀
## 푇
## 푘=1
## |x
## T
r
## 푘
## −푞|
subject tox∈ ℱ.
## (8.5)
After modeling the absolute value based on Sec. 13.1.1 we arrive at the following LO:
minimize
## 1
## 2푇
## ∑︀
## 푇
## 푘=1
## 푡
## 푘
subject tox
## T
## R−푞≥ −t,
x
## T
## R−푞≤t,
x∈ ℱ,
## (8.6)
whereRis the return data matrix with one observationr
## 푘
, 푘= 1,...,푇in each column.
Note that the number of constraints in this LO problem again depends on the sample
size푇.
## 70

For normally distributed returns, the MAD is proportional to the variance:퐷
## 훿
## 푀퐴퐷
## =
## √︁
## 2
## 휋
## √︀
## 퐷
## 훿
var
## .
## The퐿
## 1
-risk can also be applied without minimizing over푞. We can just let푞to be
the sample portfolio mean instead, i. e.,푞=x
## T
## 휇[KY91].
Risk measure from the Huber function
Another robust portfolio estimator can be obtained for the case of symmetric return
distributions using the Huber function
## 훿
## H
## (푦) =
## {︃
## 푦
## 2
## ,|푦|≤푐
## 2푐|푦|−푐
## 2
## ,|푦|> 푐
## ,
yielding the risk measure퐷
## 훿
## H
. A different form of the Huber function is훿
## H
(푦) = min
## 푢
## 푢
## 2
## +
2푐|푦−푢|, which leads to a QO formulation:
minimize
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 푢
## 2
## 푘
## +
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 2푐|x
## T
r
## 푘
## −푞−푢
## 푘
## |
subject tox∈ ℱ.
## (8.7)
Modeling the absolute value based on Sec. 13.1.1 we get
minimize
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 푢
## 2
## 푘
## +
## 1
## 푇
## ∑︀
## 푇
## 푘=1
## 2푐푡
## 푘
subject tox
## T
## R−푞−u≥ −t,
x
## T
## R−푞−u≤t,
x∈ ℱ.
## (8.8)
Note that the size of this problem depends on the number of samples푇.
8.1.2 Downside deviation measures
In financial context many distributions are skewed. Investors might only be concerned
with negative deviations (losses) relative to the expected portfolio return휇
x
, or in general
with falling short of some benchmark return푟
bm
.  In these cases downside deviation
measures are more appropriate.
A class of downside deviation measures arelower partial momentsof order푛:
## LPM
## 푛
## (푟
bm
) =E(max(푟
bm
## −푅
x
## ,0)
## 푛
## ),
where푟
bm
is some given target return.   The discrete version of this measure is
## ∑︀
## 푇
## 푘=1
## 푝
## 푘
max(푟
bm
## −x
## T
r
## 푘
## ,0)
## 푛
## ,wherer
## 푘
is a scenario of the portfolio return푅
x
occur-
ring with probability푝
## 푘
## .
We have the following special cases:
## •LPM
## 0
is the probability of loss relative to the target return푟
bm
## .LPM
## 0
is an
incomplete measure of risk, because it does not provide any indication of how
severe the shortfall can be, should it occur. Therefore it is best used as a constraint
while optimizing for a different risk measure.  This wayLPM
## 0
can still provide
information about the risk tolerance of the investor.
## •LPM
## 1
is theexpected loss, also calledtarget shortfall.
## 71

## •LPM
## 2
is calledtarget semi-variance.
While lower partial moments only consider outcomes below the target푟
bm
, the op-
timization still uses the entire distribution of푅
x
.  The right tail of the distribution
(representing the outcomes above the target) is captured in the mean휇
x
of the distribu-
tion.
TheLPM
## 푛
optimization problem can be formulated as [Lau01]
minimize
## ∑︀
## 푇
## 푘=1
## 푝
## 푘
max(푟
bm
## −x
## T
r
## 푘
## ,0)
## 푛
subject tox∈ ℱ.
## (8.9)
If we define the new variables푡
## −
## 푘
= max(푟
bm
## −x
## T
r
## 푘
,0), then for푛= 1we arrive at an
LO and for푛= 2we arrive at a QO problem:
minimize
## ∑︀
## 푇
## 푘=1
## 푝
## 푘
## (푡
## −
## 푘
## )
## 푛
subject tot
## −
## ≥푟
bm
## −x
## T
## R,
t
## −
## ≥0,
x∈ ℱ,
## (8.10)
wheret
## −
is푇dimensional vector. Thus there will be푁+푇variables, and the number
of constraints will also depend on the sample size푇.
Contrary to the variance,LPM
## 푛
measures are consistent with more general classes of
investor utility functions, and assume less about the return distribution. Thus they better
reflect investor preferences and are valid under a broader range of conditions [Har91].
However, LPMs are only useful for skewed distributions. If the return distribution is
symmetric,LPM
## 1
andLPM
## 2
based portfolio estimates will be equivalent to MAD and
variance based ones. In particular the MAD for a random variable with density푓(푥)
will be the same asLPM
## 1
of a random variable with density푓(푥) +푓(−푥). Also, the
mean-LPM optimization model is very sensitive to the changes in the target value.
8.2 Tail risk measures
Tail risk measures try to capture the risk of extreme events. The measures described
below are commonly defined for random variables treating loss as positive number, so to
apply them on security returns푅we have to flip the sign and define loss as퐿=−푅.
Let푋,푌be random variables of investment losses, and let휏be a mapping.  The
formal properties that a reasonable tail risk measure should satisfy are the following
## [FS02]:
- Monotonicity: If푋≤푌, then휏(푋)≤휏(푌),
- Translation invariance:휏(푋+푚) =휏(푋) +푚, 푚∈R,
## 3. Subadditivity:휏(푋+푌)≤휏(푋) +휏(푌),
- Positive homogeneity:휏(푐푋) =푐휏(푋), 푐≥0
If휏satisfies these properties then it is calledcoherent risk measure.  If we relax
condition 3 and 4 to the property ofconvexity, then we get the more general class ofconvex
risk measures. Not all risk measures used in practice satisfy these properties, violation of
condition 1 and/or 2 is typical. However, in the context of portfolio selection these are
less critical, the property of convexity is most important to achieve risk diversification
[Lau01].
## 72

8.2.1 Value-at-Risk
Denote the훼-quantile of a random variable퐿by푞
## 훼
(퐿) = inf{푥|P(퐿≤푥)≥훼}. If퐿
is the loss over a given time horizon, then thevalue-at-risk(VaR) of퐿with confidence
level훼(or risk level1−훼) is defined to be
VaR
## 훼
## (퐿) =푞
## 훼
## (퐿).
This is the amount of loss (a positive number) over the given time horizon that will
not be exceeded with probability훼. However, VaR does not give information about the
magnitude of loss in case of the1−훼probability event when losses are greater than푞
## 훼
## (퐿).
Also it is not a coherent risk measure (it does not respect convexity property), meaning
it can discourage diversification.
## 2
In other words, portfolio VaR may not be lower than
the sum of the VaRs of the individual securities.
8.2.2 Conditional Value-at-Risk
A modification of VaR that is a coherent risk measure isconditional value-at-risk(CVaR).
CVaR is the average of the1−훼fraction of worst case losses, i. e., the losses equal to
or exceedingVaR
## 훼
(퐿). Its most general definition (applicable also for loss distributions
with possible discontinuities) can be found in [RU02]. Let휆
## 훼
## =
## 1
## 1−훼
## (P(퐿≤푞
## 훼
## (퐿))−훼).
Then the CVaR of퐿with confidence level훼will be
CVaR
## 훼
## (퐿) =휆
## 훼
## 푞
## 훼
## (퐿) + (1−휆
## 훼
## )E(퐿|퐿 > 푞
## 훼
## (퐿)),
which is a linear combination of VaR and the quantity calledmean shortfall. The latter
is also not coherent on its own.
If the distribution functionP(퐿≤푞)is continuous at푞
## 훼
## (퐿)then휆
## 훼
= 0. If there is
discontinuity and we have to account for a probability mass concentrated at푞
## 훼
(퐿), then
## 휆
## 훼
is nonzero in general. This is often the case in practice, when the loss distribution is
discrete, for example for scenario based approximations.
CVaR for discrete distribution
Suppose that the loss distribution is described by points푞
## 1
## <···< 푞
## 푇
with nonzero
probabilities푝
## 1
## ,...,푝
## 푇
, and푖
## 훼
∈ {1,...,푇}is the index such that
## ∑︀
## 푖
## 훼
## −1
## 푖=1
## 푝
## 푖
## < 훼≤
## ∑︀
## 푖
## 훼
## 푖=1
## 푝
## 푖
. ThenVaR
## 훼
## (퐿) =푞
## 푖
## 훼
and
CVaR
## 훼
## (퐿)   =휆
## 훼
## 푞
## 푖
## 훼
## + (1−휆
## 훼
## )
## 1
## ∑︀
## 푖>푖
## 훼
## 푝
## 푖
## ∑︀
## 푖>푖
## 훼
## 푝
## 푖
## 푞
## 푖
## =
## =
## 1
## 1−훼
## (︁
## (
## ∑︀
## 푖
## 훼
## 푖=1
## 푝
## 푖
## −훼)푞
## 푖
## 훼
## +
## ∑︀
## 푖>푖
## 훼
## 푝
## 푖
## 푞
## 푖
## )︁
## ,
## (8.11)
where휆
## 훼
## =
## 1
## 1−훼
## (
## ∑︀
## 푖
## 훼
## 푖=1
## 푝
## 푖
−훼). As a special case, if we assume that푝
## 푖
## =
## 1
## 푇
, i. e., we have
a sample average approximation, then the above formula simplifies with푖
## 훼
## =⌈훼푇⌉.
It can be seen thatVaR
## 훼
(퐿)≤CVaR
## 훼
(퐿)always holds. CVaR is also consistent with
second-order stochastic dominance (SSD), i. e., the CVaR efficient portfolios are the ones
actually preferred by some wealth-seeking risk-averse investors.
## 2
VaR only becomes coherent when return is normally distributed, but in this case it is proportional
to the standard deviation.
## 73

Portfolio optimization with CVaR
If we substitute portfolio loss scenarios into formula (8.11), we can see that the quantile
## (−R
## T
x)
## 푖
## 훼
will depend onx. It follows that the ordering of the scenarios and the index푖
## 훼
will also depend onx, making it difficult to optimize. However, note that formula (8.11)
is actually the linear combination of largest elements of the vectorq. We can thus apply
Sec. 13.1.1 to get the dual form ofCVaR
## 훼
(퐿), which is an LO problem:
minimize푡+
## 1
## 1−훼
p
## T
u
subject tou+푡≥q,
u≥0.
## (8.12)
Note that problem (8.12) is equivalent to
min
## 푡
## 푡+
## 1
## 1−훼
## ∑︀
## 푖
## 푝
## 푖
max(0,푞
## 푖
## −푡).
## (8.13)
This convex function (8.13) is exactly the one found in [RU00], where it is also proven to
be valid for continuous probability distributions as well.
Now we can substitute the portfolio return intoq, and optimize overxto find the
portfolio that minimizes CVaR:
minimize푡+
## 1
## 1−훼
p
## T
u
subject tou+푡≥ −R
## T
x,
u≥0,
x∈ ℱ.
## (8.14)
Because CVaR is represented as a convex function in formula (8.13), we can also formulate
an LO to maximize expected return, while limiting risk in terms of CVaR:
maximize휇
## T
x
subject to푡+
## 1
## 1−훼
p
## T
u≤훾,
u+푡≥ −R
## T
x,
u≥0,
x∈ ℱ.
## (8.15)
The drawback of optimizing CVaR using problems (8.14) or (8.15) is that both the number
of variables and the number of constraints depend on the number of scenarios푇. This
can make the LO model computationally expensive for very large number of samples. For
example if the distribution of return is not known, we might need to obtain or simulate
a substantial amount of samples, depending on the confidence level훼.
8.2.3 Entropic Value-at-Risk
A more general risk measure in this class is theentropic value-at-risk(EVaR). EVaR is
also a coherent risk measure, with additional favorable monotonicity properties; see in
[AJ12]. It is defined as the tightest upper bound on VaR obtained from the Chernoff
inequality:
EVaR
## 훼
(퐿) = inf
## 푠>0
## 1
## 푠
log
## (︂
## 푀
## 퐿
## (푠)
## 1−훼
## )︂
## ,(8.16)
where푀
## 퐿
(푠) =E(e
## 푠퐿
)is the moment generating function of퐿. The EVaR incorporates
losses both less and greater than the VaR simultaneously, thus it always holds that
CVaR
## 훼
(퐿)≤EVaR
## 훼
## (퐿).
## 74

EVaR for discrete distribution
Based on the definition (8.16), the discrete version of the EVaR will be
EVaR
## 훼
(퐿) = inf
## 푠>0
## 1
## 푠
log
## (︂
## ∑︀
## 푖
## 푝
## 푖
e
## 푠푞
## 푖
## 1−훼
## )︂
## ,(8.17)
We can make formula (8.17) convex by substituting a new variable푡=
## 1
## 푠
## :
EVaR
## 훼
(퐿) = inf
## 푡>0
## 푡log
## (︃
## ∑︁
## 푖
## 푝
## 푖
e
## 푞
## 푖
## /푡
## )︃
## −푡log(1−훼).
## (8.18)
We can transform formula (8.18) into a conic optimization problem by substituting the
first term of the objective with a new variable푧and adding the new constraint푧≥
EVaR
## 훼
(퐿). Then we apply the rule Sec. 13.1.1:
minimize푧−푡log(1−훼),
subject to
## ∑︀
## 푇
## 푖=1
## 푝
## 푖
## 푢
## 푖
## ≤푡,
## (푢
## 푖
## ,푡,푞
## 푖
## −푧)∈퐾
exp
## , 푖= 1,...,푇,
## 푡≥0.
## (8.19)
Portfolio optimization with EVaR
Now we can substitute the portfolio return intoq, and optimize overxto find the portfolio
that minimizes EVaR:
minimize푧−푡log(1−훼)
subject to
## ∑︀
## 푇
## 푖=1
## 푝
## 푖
## 푢
## 푖
## ≤푡,
## (푢
## 푖
## ,푡,−r
## T
## 푖
x−푧)∈퐾
exp
## , 푖= 1,...,푇,
## 푡≥0,
## 휇
## T
x≥푟
min
## ,
x∈ ℱ.
## (8.20)
Because EVaR is represented as a convex function (8.18), we can also formulate a conic
problem to maximize expected return, while limiting risk in terms of EVaR:
maximize휇
## T
x
subject to푧−푡log(1−훼),≤훾,
## ∑︀
## 푇
## 푖=1
## 푝
## 푖
## 푢
## 푖
## ≤푡,
## (푢
## 푖
## ,푡,−r
## T
## 푖
x−푧)∈퐾
exp
## , 푖= 1,...,푇,
## 푡≥0,
x∈ ℱ.
## (8.21)
A disadvantage of the EVaR conic model is that it still depends on푇in the number of
exponential cone contraints.
Note that if we assume the return distribution to be a Gaussian mixture, we can find
a different approach to computing EVaR. See in Sec. 8.3.2.
## 75

8.2.4 Relationship between risk measures
Suppose that휏(푋)is a coherent tail risk measure that additionally satisfies휏(푋)>
−E(푋).  Suppose also that퐷(푋)is a deviation measure that additionally satisfies
퐷(푋)≤E(푋)for all푋≥0. Then these subclasses of risk measures can be related
through the following identities:
## 퐷(푋)   =휏(푋−E(푋))
## 휏(푋)   =퐷(푋)−E(푋)
## (8.22)
For example,훼-shortfall and CVaR is related this way. Details can be found in [RUZ06].
8.2.5 Practical considerations
Many risk measures in this chapter can be computed in practice through scenario based
approximations. The relevant optimization problems can then be conveniently formulated
as LO or QO problems.  The advantage of these models is that they do not need a
covariance matrix estimate. The simplification of the problem structure, however, comes
at the cost of increasing the problem dimension by introducing a number of new variables
and constraints proportional to the number of scenarios푇.
If푇is large, this can lead to computational burden not only because of the increased
number of variables and constraints, but also because the scenario matrixRalso depend-
ing on푇becomes very non-sparse, making the solution process less efficient.
If푇is too small, specifically푇 < 푁, then there will be fewer scenarios then parameters
to estimate. This makes the portfolio optimization problem very imprecise, and prone to
overfit the data. Also depending on other constraints, solution of LO problems can have
computational difficulties. To mitigate this, we can use regularization methods, such as
## 퐿
## 1
(lasso) or퐿
## 2
(ridge) penalty terms in the objective:
minimizeℛ
x
## +휆‖x−x
pri
## ‖
## 푝
## 푝
subject to휇
## T
x≥푅,
## 1
## T
x=   1,
## (8.23)
whereℛ
x
is the portfolio risk,x
pri
is a prior portfolio, and휆is the regularization strength
parameter. The penalty term will ensure that the extreme deviations from the prior are
unlikely. Thus휆basically sets the investor confidence in the portfoliox
pri
## . Using푝= 1,2
we arrive at LO and QO problems respectively. See details in [Lau01].
8.3 Expected utility maximization
Apart from selecting different risk measures, we can also approach portfolio optimization
through the use of utility functions. We specify a concave and increasing utility function
that measures the investors preference for each specific outcome. Then the objective is
to maximize the expected utility under the return distribution.
Expected utility maximization can take into account any type of return distribution,
while MVO works only with the first two moments, therefore it is accurate only for
normally distributed return. MVO is also equivalent with expected utility maximization
if the utility function is quadratic, because it models the investors indifference about
higher moments of return. The only advantage of MVO in this comparison is that it
works without having to discretize the return distribution and work with scenarios.
## 76

8.3.1 Optimal portfolio using gaussian mixture return
In [LB22] an expected utility maximization approach is taken, assuming that the return
distribution is a Gaussian mixture (GM). The benefits of a GM distribution are that it
can approximate any continuous distribution, including skewed and fat-tailed ones. Also
its components can be interpreted as return distributions given a specific market regime.
Moreover, the expected utility maximization using this return model can be formulated as
a convex optimization problem without needing return scenarios, making this approach
as efficient and scalable as MVO.
We denote security returns having Gaussian mixture (GM) distribution with퐾com-
ponents as
## 푅∼풢ℳ({휇
## 푖
## ,Σ
## 푖
## ,휋
## 푖
## }
## 퐾
## 푖=1
## ),
## (8.24)
where휇
## 푖
is the mean,Σ
## 푖
is the covariance matrix, and휋
## 푖
is the probability of component
푖. As special cases, for퐾= 1we get the normal distribution풩(휇
## 1
## ,Σ
## 1
), and forΣ
## 푖
## =
0, 푖= 1,...,퐾we get a scenario distribution with퐾return scenarios{휇
## 1
## ,...,휇
## 퐾
## }.
Using definition (8.24), the distribution of portfolio return푅
x
will also be GM:
## 푅
x
## ∼풢ℳ({휇
x,푖
## ,휎
## 2
x,푖
## ,휋
## 푖
## }
## 퐾
## 푖=1
## ),
## (8.25)
where휇
x,푖
## =휇
## T
## 푖
x, and휎
## 2
x,푖
## =x
## T
## Σ
## 푖
x.
To select the optimal portfolio we use the exponential utility function푈
## 훿
## (푥) = 1−푒
## −훿푥
## ,
where훿 >0is the risk aversion parameter. This choice allows us to write the expected
utility of the portfolio return푅
x
using the moment generating function:
## E(1−푒
## −훿푅
x
## ) = 1−푀
## 푅
x
## (−훿).
## (8.26)
Thus maximizing the function (8.26) is the same as minimizing the moment generat-
ing function of the portfolio return, or equivalently, we can minimize its logarithm, the
cumulant generating function:
minimize퐾
## 푅
x
## (−훿)
subject tox∈ ℱ,
## (8.27)
## If푅
x
is assumed to be a GM random variable, then its cumulant generating function will
be the following:
## 퐾
## 푅
x
(−훿) = log
## (︃
## 퐾
## ∑︁
## 푖=1
## 휋
## 푖
exp
## (︂
## −훿휇
## T
## 푖
x+
## 훿
## 2
## 2
x
## T
## Σ
## 푖
x
## )︂
## )︃
## (8.28)
The function (8.28) is convex inxbecause it is a composition of the convex and increasing
log-sum-exp function and a convex quadratic function. Note that for퐾= 1, we get back
the same quadratic utility objective as in version (2.3) of the MVO problem.
Assuming we have the GM distribution parameter estimates휇
## 푖
## ,Σ
## 푖
## , 푖=  1,...,퐾,
we can apply Sec. 13.1.1 and Sec. 13.1.1 to arrive at the conic model of the utility
maximization problem (8.27):
minimize푧
subject to
## ∑︀
## 퐾
## 푖=1
## 휋
## 푖
## 푢
## 푖
## ≤1,
## (푢
## 푖
## ,1,−훿휇
## T
## 푖
x+훿
## 2
## 푞
## 푖
## −푧)∈퐾
exp
## , 푖= 1,...,퐾,
## (푞
## 푖
## ,1,G
## T
x)∈ 풬
## 푁+2
r
## , 푖= 1,...,퐾,
x∈ ℱ,
## (8.29)
## 77

where푞
## 푖
is an upper bound for the quadratic term
## 1
## 2
x
## T
## Σ
## 푖
x, andG
## 푖
is such thatΣ
## 푖
## =
## G
## 푖
## G
## T
## 푖
## .
8.3.2 EVaR using Gaussian mixture return
We introduced Entropic Value-at-Risk (EVaR) in Sec. 8.2.3. EVaR can also be expressed
using the cumulant generating function퐾
## 퐿
(푠) = log(푀
## 퐿
(푠))of the loss퐿:
EVaR
## 훼
(퐿) = inf
## 푠>0
## 1
## 푠
## 퐾
## 퐿
## (푠)−
## 1
## 푠
log(1−훼).
## (8.30)
After substituting the return푅=−퐿instead of the loss, we see that퐾
## −푅
## (푠) =퐾
## 푅
## (−푠).
Assuming now that푅=푅
x
is the portfolio return, we get the following optimization
problem:
minimize
## 1
## 푠
## 퐾
## 푅
x
## (−푠)−
## 1
## 푠
log(1−훼)
subject tox∈ ℱ,
## (8.31)
We can find a connection between EVaR computation (8.31) and maximization of ex-
pected exponential utility (8.27). Suppose that the pair(x
## *
## ,푠
## *
)is optimal for problem
## (8.31). Thenx
## *
also optimal for problem (8.27), with risk aversion parameter훿=푠
## *
## .
By assuming a GM distribution for security return, we can optimize problem (8.31)
without needing a scenario distribution. First, to formulate it as a convex optimization
problem, define the new variable푡=
## 1
## 푠
## :
EVaR
## 훼
(퐿) = inf
## 푡>0
## 푡퐾
## 푅
x
## (︂
## −
## 1
## 푡
## )︂
## −푡log(1−훼).(8.32)
We can observe that the first term in formula (8.32) is the perspective of퐾
## 푅
x
## (−1).
Therefore by substituting the cumulant generating function (8.28) of the GM portfolio
return, we get a convex function in the portfoliox:
EVaR
## 훼
(퐿) = inf
## 푡>0
## 푡log
## (︃
## 퐾
## ∑︁
## 푖=1
## 휋
## 푖
exp
## (︂
## −
## 1
## 푡
## 휇
## T
## 푖
x+
## 1
## 2푡
## 2
x
## T
## Σ
## 푖
x
## )︂
## )︃
## −푡log(1−훼).
## (8.33)
Assuming we have the GM distribution parameter estimates휇
## 푖
## ,Σ
## 푖
, 푖= 1,...,퐾, we can
apply Sec. 13.1.1 and Sec. 13.1.1 to arrive at the conic model of the EVaR minimization
problem (8.31):
minimize푧−푡log(1−훼)
subject to
## ∑︀
## 퐾
## 푖=1
## 휋
## 푖
## 푢
## 푖
## ≤푡,
## (푢
## 푖
## ,푡,−휇
## T
## 푖
x+푞
## 푖
## −푧)∈퐾
exp
## , 푖= 1,...,퐾,
## (푞
## 푖
## ,1,G
## T
x)∈ 풬
## 푁+2
r
## , 푖= 1,...,퐾,
## 푡≥0,
x∈ ℱ,
## (8.34)
where푞
## 푖
is an upper bound for the quadratic term
## 1
## 2
x
## T
## Σ
## 푖
x, andG
## 푖
is such thatΣ
## 푖
## =
## G
## 푖
## G
## T
## 푖
## .
The huge benefit of this EVaR formulation is that its size does not depend on the num-
ber of scenarios, because it is derived without using a scenario distribution. It depends
only on the number of GM components퐾.
## 78

## 8.4 Example
This example shows how can we compute the CVaR efficient frontier using the dual form
of CVaR inMOSEKFusion.
8.4.1 Scenario generation
The input data is again obtained the same way as detailed in Sec. 3.4.2, but we do
only the steps until Sec. 3.4.3. This way we get the expected return estimate휇
log
and
the covariance matrix estimateΣ
log
of yearly logarithmic returns. These returns have
approximately normal distribution, so we can easily generate푇number of return scenarios
from them, using the numpy default random number generator. Here we choose푇=
- This number ensures to have a nonzero휆
## 훼
in formula (8.11), which is the most
general case.
# Number of scenarios
## T = 99999
# Generate logarithmic return scenarios assuming normal distribution
R_log = np.random.default_rng().multivariate_normal(m_log, S_log, T)
Next, we convert the received logarithmic return scenarios to linear return scenarios
using the inverse of formula (3.2).
# Convert logarithmic return scenarios to linear return scenarios
R = np.exp(scenarios_log) - 1
## R = R.T
We transpose the resulting matrix just to remain consistent with the notation in this
chapter, namely that each column ofRis a scenario. We also set the scenario probabilities
to be
## 1
## 푇
## :
# Scenario probabilities
p = np.ones(T) / T
8.4.2 The optimization problem
The optimization problem we solve here resembles problem (2.12), but we will change
the risk measure from portfolio standard deviation to portfolio CVaR:
maximize휇
## T
x−훿·CVaR
## 훼
## (−R
## T
x)
subject to1
## T
x=   1,
x≥0.
## (8.35)
Applying the dual CVaR formula (8.13), we get:
maximize휇
## T
x−훿
## (︀
## 푡+
## 1
## 1−훼
## ∑︀
## 푖
## 푝
## 푖
max(0,−r
## T
## 푖
x−푡)
## )︀
subject to1
## T
x=   1,
x≥0.
## (8.36)
We know that formula (8.13) equals CVaR only if it is minimal in푡. This will be satisfied
in the optimal solution of problem (8.36), because the CVaR term is implicitly forced to
become smaller, and푡is independent fromx.
## 79

Now we model the maximum function, and arrive at the following LO model of the
mean-CVaR efficient frontier:
maximize휇
## T
x−훿푡−
## 훿
## 1−훼
## ∑︀
## 푖
## 푝
## 푖
## 푢
## 푖
subject tou≥ −R
## T
x−푡,
u≥0,
## 1
## T
x=   1,
x≥0.
## (8.37)
8.4.3 The Fusion model
Here we show the Fusion model of problem (8.37).
def EfficientFrontier(N, T, m, R, p, alpha, deltas):
with Model("CVaRFrontier") as M:
## # Variables
# x - fraction of holdings relative to the initial capital.
# It is constrained to take only positive values.
x = M.variable("x", N, Domain.greaterThan(0.0))
# Budget constraint
## M.constraint('budget', Expr.sum(x) == 1)
# Auxiliary variables.
t = M.variable("t", 1, Domain.unbounded())
u = M.variable("u", T, Domain.unbounded())
# Constraint modeling maximum
M.constraint(u >= - R * x - Var.repeat(t, T))
## M.constraint(u >= 0)
## # Objective
delta = M.parameter()
cvar_term = t + u.T @ p / (1-alpha)
M.objective('obj', ObjectiveSense.Maximize,
x.T @ m - delta * cvar_term)
# Create DataFrame to store the results.
columns = ["delta", "obj", "return", "risk"] + \
df_prices.columns.tolist()
df_result = pd.DataFrame(columns=columns)
for d in deltas:
# Update parameter
delta.setValue(d)
# Solve optimization
## M.solve()
# Save results
portfolio_return = m @ x.level()
(continues on next page)
## 80

(continued from previous page)
portfolio_risk = t.level()[0] + \
1/(1-alpha) * np.dot(p, u.level())
row = pd.Series([d, M.primalObjValue(),
portfolio_return, portfolio_risk] + \
list(x.level()), index=columns)
df_result = df_result.append(row, ignore_index=True)
return df_result
Next, we compute the efficient frontier. We select the confidence level훼= 0.95. The
following code produces the optimization results:
alpha = 0.95
# Compute efficient frontier with and without shrinkage
deltas = np.logspace(start=-1, stop=2, num=20)[::-1]
df_result = EfficientFrontier(N, T, m, R, p, alpha, deltas)
On Fig. 8.1 we can see the risk-return plane, and on Fig. 8.2 the portfolio composition
for different levels of risk.
Fig. 8.1: The CVaR efficient frontier.
## 81

Fig. 8.2: Portfolio compositionxwith varying level of CVaR risk.
## 82

## Chapter 9
Risk budgeting
Traditional MVO only considers the risk of the portfolio and ignores how the risk is
distributed among individual securities. This might result in risk being concentrated into
only a few securities, when these gain too much weight in the portfolio.
Risk budgeting techniques were developed to give portfolio managers more control over
the amount of risk each security contributes to the total portfolio risk. They allocate the
risk instead of the capital, thus diversify risk more directly. Risk budgeting also makes
the resulting portfolio less sensitive to estimation errors, because it excludes the use of
expected return estimates [CK20, Pal20].
9.1 Risk contribution
If the risk measure is a homogeneous function of degree one, then we can use Euler
decomposition write the total portfolio riskℛ
x
as the sum of risk contributionsrc
x,푖
of
each security:
## ℛ
x
## =
## 푁
## ∑︁
## 푖=1
rc
x,푖
## =
## 푁
## ∑︁
## 푖=1
## 푥
## 푖
mrc
x,푖
## =
## 푁
## ∑︁
## 푖=1
## 푥
## 푖
## 휕ℛ
x
## 휕푥
## 푖
## =x
## T
## ∇ℛ
x
## (9.1)
wheremrc
x,푖
## =
## 휕ℛ
x
## 휕푥
## 푖
is calledmarginal risk contribution, because it measures the sensitiv-
ity of the portfolio standard deviation to changes in푥
## 푖
## .
9.2 Risk budgeting portfolio
With the above definitions, therisk budgeting portfolioaims to allocate the risk contri-
butions according to a predeterminedrisk profileb. In other words, it aims to find the
portfolioxthat solves the system
x∘∇ℛ
x
## =b∘ℛ
x
## =b∘x
## T
## ∇ℛ
x
## (9.2)
where1
## T
b= 1andb≥0. A special case of this is therisk parity portfolio, for which
## 푏
## 푖
## =
## 1
## 푁
## .
Using that∇ℛ
cx
## =∇ℛ
x
for homogeneousℛ
x
of degree one and푐∈R, we can see
that ifx
rb
is a risk budgeting portfolio, then so is푐x
rb
. In some solution approaches it is
useful to define a risk-normalized variabley=x/ℛ
x
, and get
y∘∇ℛ
y
## =b
## (9.3)
## 83

Working with this form is typically easier. After solving these equations, we can recover
the portfolioxby normalizing again.
9.3 Risk budgeting with variance
If we use portfolio variance as risk measure, i. e., setℛ
x
## =x
## T
Σx, then (9.2) will become
x∘Σx=b∘x
## T
## Σx,
## (9.4)
and (9.3) will become
y∘Σy=b
## (9.5)
Solving this system is inherently a non-convex problem because it has quadratic equality
constraints. However, we can still formulate convex optimization problems to find the
solution.
In general, however, we have to be aware that the conditions defining the risk bud-
geting portfolio are very restrictive. Therefore we have very limited possibility to further
constrain a risk budgeting problem, without making the risk budgeting portfolio infeasi-
ble.
9.3.1 Convex formulation using quadratic cone
Suppose we allocate the risk budget푏
## 푚
for each security푖in a group of securities풢
## 푚
## ,
and we have푀such groups. As special cases, we have푀=푁when each security has a
unique risk budget, thus each풢
## 푚
contains only one security. In contrast, we have푀= 1
when all risk budgets푏
## 푖
= 1/푁are the same, leading to the risk parity portfolio.
Let us now focus on group풢
## 푚
. We can define new variables훾
u,푚
and훾
l,푚
to bound
the risk contributions in this group from above and from below. First we express the risk
contributions as the fraction of the total risk푏
## 푚
x
## T
Σx. We can bound this from above to
get the constraint
## 푏
## 푚
x
## T
## Σx≤훾
## 2
u,푚
## ,
and model it using the quadratic cone.
Next, we bound the risk contributions from below as
## 푥
## 푖
(Σx)
## 푖
## ≥훾
## 2
l,푚
## .
## Assuming푥
## 푖
≥0and(Σx)
## 푖
≥0,  we can model this using the power cone
as(푥
## 푖
,(Σx)
## 푖
## ,훾
l,푚
## )∈ 풫
## 1/2,1/2
## 3
, or equivalently using the rotated quadratic cone as
## (푥
## 푖
## /
## √
2,(Σx)
## 푖
## /
## √
## 2,훾
l,푚
## )∈풬
## 3
r
## .
Finally, minimizing the difference between the upper and lower bounds, we get the
risk budgeting portfolio as the optimal solution. The full optimization problem will look
like
minimize
## ∑︀
## 푀
## 푚=1
## 훾
u,푚
## −훾
l,푚
subject to1
## T
x=   1,
## (훾
u,푚
## /
## √
## 푏
## 푚
## ,G
## T
x)∈ 풬
## 푘+1
## ,  푚= 1,...,푀,
## (푥
## 푖
,(Σx)
## 푖
## ,훾
l,푚
## )∈ 풫
## 1/2,1/2
## 3
## ,  푖∈풢
## 푚
## , 푚= 1,...,푀,
x,Σx≥0,
## 훾
u,푚
## ≥훾
l,푚
## ,  푚= 1,...,푀,
## (9.6)
## 84

whereΣ=GG
## T
forG∈R
## 푁×푘
## .
Note that we have to be careful adding further constraints to problem (9.6), because
these might make the risk budgeting portfolio infeasible.
9.3.2 Convex formulation using exponential cone
There also exists a different convex formulation of the risk budgeting problem, that works
not only in the positive orthant, but in any (prespecified) orthant of the portfolio space.
This allows us to work with long-short portfolios as well.
Observe that the risk budgeting equations (9.4) are the first-order optimality condi-
tions of the optimization problem
minimize
## 1
## 2
x
## T
## Σx−푐b
## T
log (z∘x)
subject toz∘x≥0.
## (9.7)
We can use the parameter푐to scale the sum of vectorb, leading to different magnitude
of the optimal solution. Thus we can directly find a solution that satisfies for example
## ∑︀
## 푖
## 푥
## 푖
= 1or in the long-short case
## ∑︀
## 푖
## |푥
## 푖
## |= 1.
Problem (9.7) can be modeled using the exponential cone in the following way:
minimize푠−푐b
## T
t
subject to(푠,1,G
## T
x)∈ 풬
## 푘+2
r
## ,
## (푧
## 푖
## 푥
## 푖
## ,1,푡
## 푖
## )∈퐾
exp
## ,  푖= 1,...,푁,
z∘x≥0,
## (9.8)
whereΣ=GG
## T
forG∈R
## 푁×푘
## .
While this convex approach works with any sign configurationz∈{+1,−1}
## 푁
ofx, we
have to specifyzas parameter, meaning we can still only compute the optimal solution
for a given orthant. The reason is that by design, there are solutions to (9.4) in each
orthant. There are2
## 푁
(normalized) solutions, one for each possiblez∘x>0[CK20], i.
e., one in each orthant.
## 1
So there is a local optimal solution in each orthant, meaning
that the problem is non-convex on the full space.
Also note that in this formulation we cannot add further constraints, because these
could alter the optimality conditions (9.4), making the solution invalid as a risk budgeting
portfolio.
9.3.3 Mixed integer formulation
In each orthant, the solution to (9.7) can have a different total risk. Therefore we can
try to find a risk budgeting portfolio that has low total risk. In order to do this, we can
extend problem (9.7) to be mixed integer. This will allow us to optimize over the full
space, including all long-short portfolios, without needing to prespecify the signs. After
defining separate variables based on Sec. 13.2.1 for the long and the short part of the
## 1
Of course the solutions in opposite orthants differ only by global sign, so these can be considered
the same solution.
## 85

portfolio, we get:
minimize
## 1
## 2
x
## T
## Σx−푐b
## T
log (x
## +
## +x
## −
## )
subject tox
## +
## ,x
## −
## ≥0,
x=x
## +
## −x
## −
## ,
x
## +
## ≤푀z
## +
## ,
x
## −
## ≤푀z
## −
## ,
z
## +
## +z
## −
## ≤1,
z
## +
## ,z
## −
## ∈ {0,1}
## 푁
## .
## (9.9)
What makes sure that problem (9.9) will find a low risk solution?  The first term of
the objective function is the sum of risk budgets, thus in any optimal solution, we must
havex
## T
## Σx=
## √
푐, because the risk budgeting conditions are satisfied. It follows that the
second term will decide the optimal objective value. This logarithmic term will become
the lowest if the monomial|x|
## 푐b
## =
## (︀
## ‖x‖
## 1
## |
## ˆ
x|
b
## )︀
## 푐
is largest, where
## ˆ
xdenotes a unit vector.
Depending onb, this implies an optimalxwith large 1-norm.  It follows that after
normalization, thisxwill yield a low value for the total riskx
## T
Σx. Note however, that
it is not guaranteed to get the lowest risk, because|
## ˆ
x|
b
can also vary.
A further tradeoff with the mixed integer approach is that we have no performance
guarantee, finding the optimal solution can take a lot of time. Most likely we will have
to settle with suboptimal portfolios in terms of risk.
## 9.4 Example
In this example we show how can we find a risk parity portfolio by solving a convex
optimization problem inMOSEKFusion.
The input data is again obtained the same way as detailed in Sec. 3.4.2. Here we
assume that the covariance matrix estimateΣof yearly returns is available.
The optimization problem we solve here is (9.8), which we repeat here:
minimize푠−푐b
## T
t
subject to(푠,1,G
## T
x)∈ 풬
## 푘+2
r
## ,
## (푧
## 푖
## 푥
## 푖
## ,1,푡
## 푖
## )∈퐾
exp
## ,  푖= 1,...,푁,
z∘x≥0,
## (9.10)
We search for a solution in the positive orthant, so we setz=1. We choose the risk
budget vector to beb= 1/푁, so that all securities contribute the same amount of risk.
The Fusion model of (9.10):
def RiskBudgeting(N, G, b, z, a):
with Model("RiskBudgeting") as M:
# Portfolio weights
x = M.variable("x", N, Domain.unbounded())
# Auxiliary variables
t = M.variable("t", N, Domain.unbounded())
s = M.variable("s", 1, Domain.unbounded())
# Objective: 1/2 * x'Sx - a * b'@ log(z*x) becomes s - a * t'@ b
(continues on next page)
## 86

(continued from previous page)
M.objective(ObjectiveSense.Minimize, s - a * (t.T @ b))
# Bound on risk term
M.constraint(Expr.vstack(s, 1, G.T @ x), Domain.inRotatedQCone())
# Bound on log term t <= log(z*x) becomes (z*x, 1, t) in K_exp
M.constraint(Expr.hstack(Expr.mulElm(z, x),
Expr.constTerm(N, 1.0), t),
Domain.inPExpCone())
# Create DataFrame to store the results.
columns = ["obj", "risk", "xsum", "bsum"] + \
df_prices.columns.tolist()
df_result = pd.DataFrame(columns=columns)
# Solve optimization
## M.solve()
# Save results
xv = x.level()
# Check solution quality
risk_budgets = xv * np.dot(G @ G.T, xv)
# Renormalize to gross exposure = 1
xv = xv / np.abs(xv).sum()
# Compute portfolio metrics
Gx = np.dot(G.T, xv)
portfolio_risk = np.sqrt(np.dot(Gx, Gx))
row = pd.Series([M.primalObjValue(), portfolio_risk,
np.sum(z * xv), np.sum(risk_budgets)] + \
list(xv), index=columns)
df_result = df_result.append(row, ignore_index=True)
row = pd.Series([None] * 4 + list(risk_budgets), index=columns)
df_result = df_result.append(row, ignore_index=True)
return df_result
The following code defines the parameters, including the matrixGsuch thatΣ=
## GG
## 푇
## .
# Number of securities
## N = 8
# Risk budget
b = np.ones(N) / N
# Orthant selector
z = np.ones(N)
(continues on next page)
## 87

(continued from previous page)
# Global setting for sum of b
c = 1
# Cholesky factor of the covariance matrix S
G = np.linalg.cholesky(S)
Finally, we produce the optimization results:
df_result = RiskBudgeting(N, G, b, z, c)
On Fig. 9.1 we can see the portfolio composition, and on Fig. 9.2 the risk contributions
of each security.
Fig. 9.1: The risk budgeting portfolio.
## 88

Fig. 9.2: The risk contributions of each security.
## 89

## Chapter 10
Robust optimization
In chapter Sec. 4 we have discussed in detail, that the inaccurate or uncertain input
parameters of a portfolio optimization problem can result in wrong optimal solutions. In
other words, the solution is very input sensitive. Robust optimization is another possible
modeling tool to overcome this sensitivity. It is a way of handling estimation errors in the
optimization problem instead of the input preparation phase. In the most common setup,
the parameters are the estimated mean and estimated covariance matrix of the security
returns. In robust optimization, we do not compute point estimates of these, but rather
an uncertainty set, where the true values lie with certain confidence. A robust portfolio
thus optimizes the worst-case performance with respect to all possible parameter values
within their corresponding uncertainty sets. [CJPT18, VD09]
10.1 Types of uncertainty
We can form different types of uncertainty sets around the unknown parameters, depend-
ing on the nature of the uncertainty, the sensitivity of the solution, and the available
information.
•Polytope: If we have a finite number of scenarios, we can form a polytope uncer-
tainty set by taking the convex hull of the scenarios.
•Interval: We can compute a confidence interval for each of the parameters.
•Ellipsoidal region: For vector variables, we can compute confidence regions.
We can model all of these types of uncertainty sets in conic optimization, allowing us
to solve robust optimization problems efficiently.
The size of the uncertainty sets reflects the desired level of robustness. For confidence
intervals, it is controlled by the confidence level.  There is of course a tradeoff, if the
uncertainty sets are chosen to be very large, then the resulting portfolios will be very
conservative, and they will perform much worse for any given parameter set, than the
portfolio designed for that set of parameters. On the other hand, if the size is chosen too
small, the resulting portfolio will not be robust enough.
## 90

10.2 Uncertainty in security returns
Consider problem (2.3), which we restate here:
maximize휇
## T
x−
## 훿
## 2
x
## T
## Σx
subject to1
## T
x=   1.
## (10.1)
Assume that the vector of mean returns휇belongs to the elliptical uncertainty set
## 풰
## 휇
## ={휇|(휇−휇
## 0
## )
## T
## 푄
## −1
## (휇−휇
## 0
## )≤훾
## 2
## },
## (10.2)
where푄is a known positive semidefinite matrix. Then the worst case expected portfolio
return will be
min
## 휇∈풰
## 휇
## 휇
## T
x=휇
## T
## 0
x−훾
## √︀
x
## T
## 푄x.
It follows that the robust version of (10.1) becomes
maximize휇
## T
## 0
x−훾
## √︀
x
## T
## 푄x−
## 훿
## 2
x
## T
## Σx
subject to1
## T
x=   1.
## (10.3)
10.3 Uncertainty in the factor model
In the article [GI03], the authors consider a factor model on security returns, treat its
parameters as uncertain using ellipsoidal uncertainty sets defined as confidence regions,
and formulate robust portfolio optimization problems.
Assume that for a random security return vector푅
## 푡
and factor return vector퐹
## 푡
at
time푡, the factor model takes the form
## 푅
## 푡
## =휇+훽퐹
## 푡
## +휃
## 푡
## ,
## (10.4)
where휇is the vector of mean security returns,훽is the factor loading matrix, and휃
## 푡
is the vector of residual returns.  We also assume an exact factor model (see Sec. 5),
meaning that the factor returns and residual returns are assumed to be independent, and
the residual covariance matrix퐷of휃
## 푡
is diagonal. Moreover,E(퐹
## 푡
) =0, so the factors
carry no information on the mean returns. A final assumption in this section is that the
factor covariance matrix푄∈R
## 퐾×퐾
is known exactly. This requirement will be relaxed
later.
The portfolio mean return and portfolio variance will beE(푅
x
## ) =휇
## T
xandVar(푅
x
## ) =
x
## T
## (훽푄훽
## T
+퐷)x. If we compute estimates휇,훽, andDof the above quantities, we can
reformulate problem (2.1):
minimize푡
## 1
## +푡
## 2
subject to휇
## T
x≥푟
min
## ,
x
## T
## Dx≤푡
## 2
## ,
x
## T
## 훽푄훽
## T
x≤푡
## 1
## ,
x∈ ℱ.
## (10.5)
## 91

10.3.1 Uncertainty sets
Instead of computing (10.5) using estimates, we assume variables휇,훽, andDto lie in
the following uncertainty sets:
•The diagonal elements휎
## 2
## 휃
of the matrixDcan take values in an uncertainty interval
## [휎
## 2
## 휃
## ,
## 휎
## 2
## 휃
## ]:
## 풰
## 퐷
={D|diag(D)∈[휎
## 2
## 휃
## ,휎
## 2
## 휃
## ]}
## (10.6)
•The factor loadings matrix훽belongs to the elliptical uncertainty set
## 풰
## 훽
## ={훽|훽=훽
## 0
## +B,‖B
## 푖
## ‖
## G
## ≤휌
## 푖
## ,푖= 1,...,푁}
## (10.7)
whereB
## 푖
is row푖of the matrixB, and‖b‖
## G
## =
## √
b
## T
Gbdenotes the elliptic norm
ofbwith respect to the positive definite matrixG∈R
## 퐾×퐾
## .
•The vector휇of mean returns is assumed to lie in the uncertainty interval
## 풰
## 휇
## ={휇|휇=휇
## 0
## +m,|m|≤훾}
## (10.8)
10.3.2 Robust problem formulation
The goal of robust portfolio selection is then to select portfolios that perform well for all
parameter values that constitute these sets of uncertainty. In other words, we are looking
for worst case optimal solutions, formulated as minmax optimization problems. Then we
can state the robust mean-variance optimization problem:
minimize푡
## 1
## +푡
## 2
subject tomin
## 휇∈풰
## 휇
## 휇
## T
x≥푟
min
## ,
max
## D∈풰
## 퐷
x
## T
## Dx≤푡
## 2
## ,
max
## 훽∈풰
## 훽
x
## T
## 훽푄훽
## T
x≤푡
## 1
## ,
x∈ ℱ.
## (10.9)
To convert the minmax problem (10.9) into a conic optimization problem, we first need
to represent the worst case expected portfolio return and portfolio variance using conic
constraints:
•We can evaluate the worst case expected portfolio return:
min
## 휇∈풰
## 휇
## 휇
## T
x=휇
## T
## 0
x−훾
## T
## |x|.
•We can evaluate the worst case residual portfolio variance:
max
## D∈풰
## 퐷
x
## T
## Dx=x
## T
## Diag(
## 휎
## 2
## 휃
## )x.
## 92

•We cannot easily evaluate the worst case factor portfolio variance. But we can show
that the constraint
max
## 훽∈풰
## 훽
x
## T
## 훽푄훽
## T
x≤푡
## 1
is equivalent to
## (휌
## T
## |x|,푡
## 1
## ,x)∈ℋ(훽
## 0
## ,푄,G).
## (10.10)
Relation (10.10) is a shorthand notation for the following:   DefineH=
## G
## −1/2
## 푄G
## −1/2
,  with spectral decompositionH=VΛV
## T
,  and definew=
## V
## T
## H
## 1/2
## G
## 1/2
## 훽
## T
## 0
x.  Then there exist휏,푠,u≥0that satisfy the set of conic con-
straints
## 휏+1
## T
u≤푡
## 1
## ,
## 푠≤1/휆
max
## (H),
## (휌
## T
## |x|)
## 2
## ≤푠휏,
## 푤
## 2
## 푖
## ≤(1−푠휆
## 푖
## )푢
## 푖
## ,  푖= 1,...,퐾
There is also a different but equivalent version of this statement, see [GI03].
10.3.3 Robust conic model
Now we can formulate the robust optimization problem (10.9):
minimize푡
## 1
## +푡
## 2
subject to휇
## T
## 0
x−훾
## T
## |x| ≥푟
min
## ,
x
## T
## Diag(
## 휎
## 2
## 휃
## )x≤푡
## 2
## ,
## (휌
## T
## |x|,푡
## 1
## ,x)∈ ℋ(훽
## 0
## ,푄,G),
x∈ ℱ,
## (10.11)
Finally, we can convert (10.11) into conic form by modeling the absolute value based on
Sec. 13.1.1 and the quadratic cone based on Sec. 13.1.1:
minimize푡
## 1
## +푡
## 2
subject to휇
## T
## 0
x−훾
## T
z≥푟
min
## ,
## (푡
## 2
## ,
## 1
## 2
## ,
## √︀
## 휎
## 2
## 휃
## ∘x)∈ 풬
## 푁+2
r
## ,
## (휌
## T
z,푡
## 1
## ,x)∈ ℋ(훽
## 0
## ,푄,G),
x≤z,
x≥ −z,
x∈ ℱ,
## (10.12)
and the constraint(휌
## T
z,푡
## 1
## ,x)∈ ℋ(훽
## 0
,푄,G)can be modeled using the hyperbolic con-
straint in Sec. 13.1.1:
## 휏+1
## T
u≤푡
## 1
## ,
## 푠≤1/휆
max
## (H),
## (푠,휏,휌
## T
z)∈ 풬
## 3
r
## ,
## (1−푠휆
## 푖
## ,푢
## 푖
## ,푤
## 푖
## )∈ 풬
## 3
r
## ,  푖= 1,...,퐾
## (10.13)
where휏,푠,u≥0are new variables,w=V
## T
## H
## 1/2
## G
## 1/2
## 훽
## T
## 0
x, and휆
## 푖
are eigenvalues of
## H=G
## −1/2
## 푄G
## −1/2
## =VΛV
## T
## .
## 93

10.3.4 Case of unknown factor covariance
In this section we cover the case when the factor covariance matrix푄is also uncertain,
and has the estimateQ. In this case, the robust portfolio optimization problem can still
be converted into a conic form, and solved efficiently.
We can give an uncertainty structure to either the factor covariance matrixQor its
inverseQ
## −1
. Both choices lead to the same worst case portfolio variance constraint. The
choice ofQ
## −1
is a bit more restrictive, but allows us to accomodate prior information
about the structure ofQ. See the details in [GI03]. Here we describe the case ofQ.
The matrix estimateQhas the uncertainty structure
## 풰
## 푄
## ={Q|Q=Q
## 0
## + ∆≥0,∆ = ∆
## T
## ,‖N
## −1/2
## ∆N
## −1/2
## ‖≤휁},
## (10.14)
whereQ
## 0
≥0, and the norm is the spectral norm or the Frobenius norm.
Then the worst case factor portfolio variance constraint
max
## 훽∈풰
## 훽
## ,Q∈풰
## 푄
x
## T
## 훽Q훽
## T
x≤푡
## 1
is equivalent to
## (휌
## T
## |x|,푡
## 1
## ,x)∈ℋ(훽
## 0
## ,Q
## 0
## +휁N,G).
## (10.15)
## 10.4 Parameters
In this section we discuss how the parameters of the uncertainty sets introduced in Sec.
10.3.1 can be computed from market data. Typically the parameters휇,훽,Dare es-
timated from the security return and factor return data, using multivariate linear re-
gression.  We can also compute multidimensional confidence regions with any desired
confidence level around the least-squares estimates. These confidence regions become the
uncertainty sets in the robust portfolio optimization problem. The regression procedure
also yields natural choices for the matrixGdefining the elliptic norm and the bounds휌,
## 훾,
## 휎
## 2
## 휃
. In [GI03], there are two methods discussed to construct the uncertainty sets from
data, here we detail only one of them.
In (10.4) the factor model is written for all security at one time instant푡. Now we
write the model for one security푖at all time instants:
## 푅
## 푖
## =휇
## 푖
## +훽
## 푖
## F+휃
## 푖
## ,  푖= 1,...,푁
where훽
## 푖
is row number푖of훽. We can write this in a shorter form as
## 푅
## 푖
## =A푌
## 푖
## +휃
## 푖
## ,  푖= 1,...,푁
where푌
## 푖
## = [휇
## 푖
## ,훽
## 푖
## ]
## T
## ∈R
## (퐾+1)×1
, andA= [1,F
## T
## ]∈R
## 푁×(퐾+1)
## .
Assuming that the matrixAis rank퐾+ 1, and we have market return seriesr
## 푖
, the
theory of ordinary least squares leads to the estimate
## ̄
y
## 푖
## = [
## ̄
## 휇
## 푖
## ,
## ̄
## 훽
## 푖
## ]
## T
## = (A
## T
## A)
## −1
## A
## T
r
## 푖
The휔elliptical confidence region aroundy
## 푖
is then
## 풰
## 푦
## 푖
## (휔) ={y
## 푖
## |(
## ̄
y
## 푖
## −y
## 푖
## )
## T
## (A
## T
## A)(
## ̄
y
## 푖
## −y
## 푖
## )≤(퐾+ 1)(푠
## 2
## 휃
## )
## 푖
## 푐
## 퐾+1
## (휔)},
## 94

where(푠
## 2
## 휃
## )
## 푖
## =‖r
## 푖
## −A
## ̄
y
## 푖
## ‖
## 2
/(푇−퐾−1)is estimate of the error variance(휎
## 2
## 휃
## )
## 푖
## ,푐
## 퐾+1
(휔)is the
휔critical value, the solution ofℱ
## 퐹
## (푐
## 퐾+1
) =휔, andℱ
## 퐹
is the CDF of the F-distribution
with degrees of freedom(퐾+ 1,푇−퐾−1).
Then the full휔
## 푁
confidence set forywill be풰
## 푦
## (휔) =풰
## 푦
## 1
## (휔)×···×풰
## 푦
## 푁
## (휔).
10.4.1 The parameters of풰
## 휇
If we project풰
## 푦
(휔)along the vector휇, we get the휔
## 푁
confidence set (10.8), where
## (휇
## 0
## )
## 푖
## =
## ̄
## 휇
## 푖
## ,
## 훾
## 푖
## =
## √︁
## (퐾+ 1)(A
## T
## A)
## −1
## 1,1
## (푠
## 2
## 휃
## )
## 푖
## 푐
## 퐾+1
## (휔)
10.4.2 The parameters of풰
## 훽
LetP=  [0,I]∈R
## 퐾×(퐾+1)
be the matrix projectingy
## 푖
along훽
## 푖
. If we project풰
## 푦
## (휔)
along훽, then we get the휔
## 푁
confidence set (10.7), where
## (훽
## 0
## )
## 푖
## =
## ̄
## 훽
## 푖
## ,
## G=(P(A
## T
## A)
## −1
## P
## T
## )
## −1
## =FF
## T
## −
## 1
## 푇
## (F1)(F1)
## T
## ,
## 휌
## 푖
## =
## √︀
## (퐾+ 1)(푠
## 2
## 휃
## )
## 푖
## 푐
## 퐾+1
## (휔)
10.4.3 The parameters of풰
## 퐷
It would be natural to choose the confidence interval around(푠
## 2
## 휃
## )
## 푖
, the estimate of the error
variance(휎
## 2
## 휃
## )
## 푖
, but we only have a single value. It would be possible to use bootstrapping
to construnct an upper bound this way, but it can be computationally expensive.
Since we only require an estimate of the worst case error variance(
## 휎
## 2
## 휃
## )
## 푖
for the robust
optimization problem, it is cheaper to use any reasonable estimate for this purpose.
10.4.4 The parameters of풰
## 푄
In case the factor covariance matrix is not known, we can construct its uncerainty region
also from data. According to [GI03], the휔
## 퐾
confidence set (10.14) can be parameterized
the following way:
## Q
## 0
## =Q
## ML
## ,
## N=Q
## ML
## ,
## 휁=휂/(1−휂),
whereQ
## ML
=G/(푇−1)is the maximum likelihood estimate (MLE) of푄computed from
factor return data, and휂is the unique solution of
## ℱ
## Γ
## (1 +휂)−ℱ
## Γ
## (1−휂) =휔,
## (10.16)
whereℱ
## Γ
is the CDF of aΓ(
## 푇+1
## 2
## ,
## 푇−1
## 2
)random variable
## 1
, and휔is the desired confidence
level.
## 2
Note that equation (10.16) restricts휔
## 퐾
to be at mostℱ
## Γ
## (2)
## 퐾
, which depends
## 1
In the distributionΓ(푎,푏),푎is theshapeparameter and푏is therateparameter.
## 2
There is a unique solution because the right-hand side of (10.16) is monotonic on[0,1], and takes
values also in[0,1].
## 95

on the number of data samples푇.  However, this limitation is not very restrictive in
practice.
## 3
## 10.5 Example
Here we show a code example of the robust optimization problem (10.3), that we restate
here:
maximize휇
## T
## 0
x−훾
## √︀
x
## T
## 푄x−
## 훿
## 2
x
## T
## Σx
subject to1
## T
x=   1.
## (10.17)
We start at the point where data is already prepared, and we show the optimization
model. This example considers an elliptical uncertainty region around the expected return
vector. If we compute the worst case portfolio return in this case, there will be two terms
with quadratic expressions. The first will be훾
## √︀
x
## T
푄x, where훾controls the size of the
uncertainty region. If훾= 0, then we get back the original, non-robust MVO problem.
The second quadratic expression
## 훿
## 2
x
## T
Σxmodels the portfolio risk, and훿is the risk
aversion coefficient.
We can model both terms using the second-order cones. For the term with square-
root, the quadratic cone is more appropriate, while the portfolio variance term can be
modeled using the rotated quadratic cone. We substitute the square-root term with the
new variable푠
## 푞
## =
## √︀
x
## T
푄x, then the objective of the problem will be
## # Objective
delta = M.parameter()
wc_return = x.T @ mu0 - gamma * sq
M.objective('obj', ObjectiveSense.Maximize, wc_return - delta * s)
Assuming that푄=G
## 푄
## G
## T
## 푄
, the square root term can be modeled as
## # Robustness
M.constraint('robustness', Expr.vstack(sq, GQ.T @ x), Domain.inQCone())
Similarly, we substitute the risk term with푠=
## 1
## 2
x
## T
Σx, and assumingΣ=GG
## T
, we
model the risk as
# Risk constraint
M.constraint('risk', Expr.vstack(s, 1, G.T @ x),
Domain.inRotatedQCone())
The full model would look like the following:
with Model("Robust") as M:
## # Variables
# The variable x is the fraction of holdings in each security.
# It is restricted to be positive, which imposes no short-selling.
x = M.variable("x", N, Domain.greaterThan(0.0))
# The variable s models the portfolio risk term.
(continues on next page)
## 3
Assuming퐾= 40factors, having푇≥50data samples allows for a confidence level of휔
## 퐾
## ≥0.995.
## 96

(continued from previous page)
s = M.variable("s", 1, Domain.greaterThan(0.0))
# The variable sq models the robustness term.
sq = M.variable("sq", 1, Domain.greaterThan(0.0))
# Budget constraint
## M.constraint('budget', Expr.sum(x) == 1.0)
## # Objective
delta = M.parameter()
wc_return = x.T @ mu0 - gamma * sq
M.objective('obj', ObjectiveSense.Maximize, wc_return - delta * s)
## # Robustness
M.constraint('robustness', Expr.vstack(sq, GQ.T @ x), Domain.inQCone())
# Risk constraint
M.constraint('risk', Expr.vstack(s, 1, G.T @ x),
Domain.inRotatedQCone())
# Create DataFrame to store the results. Last security names
# (the factors) are removed.
columns = ["delta", "obj", "return", "risk"] + \
df_prices.columns.tolist()
df_result = pd.DataFrame(columns=columns)
for d in deltas:
# Update parameter
delta.setValue(d)
# Solve optimization
## M.solve()
# Save results
portfolio_return = mu0 @ x.level() - gamma * sq.level()[0]
portfolio_risk = np.sqrt(2 * s.level()[0])
row = pd.Series([d, M.primalObjValue(),
portfolio_return, portfolio_risk] + \
list(x.level()), index=columns)
df_result = df_result.append(row, ignore_index=True)
Finally, we compute the efficient frontier in the following points:
deltas = np.logspace(start=-1, stop=2, num=20)[::-1]
If we plot the efficient frontier on Fig. 10.1, and the portfolio composition on Fig. 10.2
we can compare the results obtained with and without using robust optimization.
## 97

Fig. 10.1: The efficient frontier.
Fig. 10.2: Portfolio compositionxwith varying level if risk-aversion훿.
## 98

## Chapter 11
Multi-period portfolio optimization
Multi-period portfolio optimization is an extension of the single-period MVO problem.
Its objective is to select a sequence of trades over a series of time periods. In contrast to
repeated single period optimizations, it takes into account recourse and updated infor-
mation while planning trades for the subsequent period.
While multi period models are more complex, they can help us to naturally handle
various inter-temporal effects:
•Different time scales: We can model multiple, possibly conflicting return predictions
on different time scales.
•Transaction costs: Considers whether our trades in the current period put us in
favourable position to trade in future periods.
•Time-varying constraints: For example, reducing the leverage bound will likely
incur lower trading cost if done over several period.
•Time-varying return forecasts: For example, we may assign an exponential decay-
rate to the return predictions.
•Future events: We can act on or exploit known future events that will change risk,
liquidity, or volume, etc.
Dynamic programming is a common method to deal with multi-period problems,
however it is challenging due to the “curse of dimensionality”. Therefore in practice, we
use approximation methods, like approximate dynamic programming. Fortunately, the
resulting performance loss is typically negligible in practical scenarios.
In this chapter we describe a practical multi-period portfolio optimization problem
based on [BBD+17].
## 99

11.1 Single-period model
First we show the optimization problem for a single period to introduce the model ele-
ments and notation.
## 11.1.1 Definitions
Suppose we have푁securities and a cash account (labeled as security푁+ 1), and we
are at the beginning of period푡. Leth
## 푡
be theportfolio in dollarsin period푡, and let
## 푣
## 푡
## =1
## T
h
## 푡
be its total value. Then we can normalizeh
## 푡
to get theportfolio in weightsas
x
## 푡
## =h
## 푡
## /푣
## 푡
## .
## Letu
## 푡
be thedollar trade vectorandz
## 푡
be thenormalized trade vectorin period푡.
Then thepost-trade portfoliowill beh
## 푡
## +u
## 푡
orx
## 푡
## +z
## 푡
. In the following, we will use only
the normalized quantities.
11.1.2 Problem statement
At period푡, we wish to determine the trade vectorz
## 푡
. The starting portfoliox
## 푡
is known.
All other parameters (future quantities) have to be estimated. These are the mean return
## 휇
## 푡
, the risk functionℛ
## 푡
, the trading cost function휑
trade
## 푡
, and the holding cost function
## 휑
hold
## 푡
## .
The single-period optimization problem will be
maximize휇
## T
## 푡
## (x
## 푡
## +z
## 푡
## )−훿
## 푡
## ℛ
## 푡
## (x
## 푡
## +z
## 푡
## )−
## −휑
hold
## 푡
## (x
## 푡
## +z
## 푡
## )−휑
trade
## 푡
## (z
## 푡
## )
subject to1
## T
z
## 푡
## +휑
hold
## 푡
## (x
## 푡
## +z
## 푡
## ) +휑
trade
## 푡
## (z
## 푡
## )   =   0,
z
## 푡
## ∈ 풵
## 푡
## ,
x
## 푡
## +z
## 푡
## ∈ 풳
## 푡
## ,
## (11.1)
where훿
## 푡
is the risk aversion parameter, and풵
## 푡
and풳
## 푡
represent the set of trading and
the set of holding constraints respectively.
11.1.3 Post-trade computations
After (11.1) is solved, we obtain the optimal solutionz
## *
## 푡
together with the optimal cash
component푧
## *
## 푡,푁+1
.  However, the latter might be inaccurate, because it is determined
using estimated costs. After knowing the realized cost functions휑
hold
## 푡
and휑
trade
## 푡
, we can
use them to determine the accurate cash component from the self-financing condition:
## 푧
## 푡,푁+1
## =−1
## T
z
## *
## 푡,1..푁
## −휑
hold
## 푡
## (x
## 푡
## +z
## *
## 푡
## )−휑
trade
## 푡
## (z
## *
## 푡
## ).
However, this more precise cash quantity may result in small constraint violations.
Finally, we hold the post-trade portfolio until the end of period푡. Then we get the
realized return휇
## 푡
, and can compute the new total portfolio value푣
## 푡+1
. This allows us to
compute the realized portfolio return using the self financing condition:
## 푅
x,푡
## =
## 푣
## 푡+1
## −푣
## 푡
## 푣
## 푡
## =휇
## T
## (x
## 푡
## +z
## 푡
## )−휑
hold
## 푡
## (x
## 푡
## +z
## 푡
## )−휑
trade
## 푡
## (z
## 푡
## )
## (11.2)
## 100

The portfolio composition at the end of period푡can be computed using the realized
return휇
## 푡
## :
x
## 푡+1
## =
## 1
## 1 +푅
x,푡
## (1+휇
## 푡
## )∘(x
## 푡
## +z
## 푡
## ).
## (11.3)
This dynamics equation ensures that if1
## T
x
## 푡
= 1then we have1
## T
x
## 푡+1
## = 1.
11.1.4 Simplified problem
We can make two approximations to simplify problem (11.1).
•Cost terms: We can omit the cost terms from the self-financing condition, reducing
it to1
## T
z
## 푡
= 0. In this case the costs are still taken into account in the objective
as penalty terms. The benefit will be that the equation1
## T
## (x
## 푡
## +z
## 푡
) = 1will hold
exactly in all cases.
•Returns: If returns are very small in any period, then we can assume them to be
zero. Then we can approximate the dynamics equation (11.3) to bex
## 푡+1
## =x
## 푡
## +z
## 푡
## .
11.1.5 Holding constraints
Holding constraints are imposed on the post-trade portfoliox
## 푡
## +z
## 푡
, that is held until the
end of period푡. Such constraints can be for example the long only constraint, leverage,
position size limit, concentration limit, minimum cash balance, factor neutrality, etc.
Some of these constraints can actually be approximations of constraints onx
## 푡+1
## . When
we assume small returns, these approximations will also become more accurate.
11.1.6 Trading constraint
Trading constraints are imposed on the trade vectorz
## 푡
.  Such constraints can be for
example the turnover, trading limits, restrictions on the direction of trade, etc.
Here we assume the trading cost function휑
trade
## 푡
to be separable, i. e.,휑
trade
## 푡
## (x)  =
## ∑︀
## 푁
## 푖=1
## 휑
trade
## 푡,푖
## (푥
## 푖
). We also assume that there are no transaction costs associated with the
cash account.
11.2 Multi-period model
Here we extend the model (11.1) further by considering a planning horizon of퐻periods.
In this context, we would like to find the trade vectorz
## 0
for the first period by optimizing
z
## 푡
for all periods푡= 0,...,퐻−1.
## 1
The initial portfolio weight vectorx
## 0
is known. The
rest of the (future) input quantities휇
## 푡
## ,ℛ
## 푡
## ,휑
trade
## 푡
, and휑
hold
## 푡
have to be estimated for all
## 1
Only the first period trades are executed. However it is still useful to compute the trades for all
periods, to be sure not to carry out trades now that will put us in a bad position in the future.
## 101

periods. Then we have to solve the following problem:
maximize
## ∑︀
## 퐻−1
## 푡=0
## 휇
## T
## 푡
## (x
## 푡
## +z
## 푡
## )−훿
## 푡
## ℛ
## 푡
## (x
## 푡
## +z
## 푡
## )−
## −휑
hold
## 푡
## (x
## 푡
## +z
## 푡
## )−휑
trade
## 푡
## (z
## 푡
## )
subject to1
## T
z
## 푡
## +휑
hold
## 푡
## (x
## 푡
## +z
## 푡
## ) +휑
trade
## 푡
## (z
## 푡
## )   =   0,
z
## 푡
## ∈ 풵
## 푡
## ,
x
## 푡
## +z
## 푡
## ∈ 풳
## 푡
## ,
## 휇
## T
## (x
## 푡
## +z
## 푡
## )−휑
hold
## 푡
## (x
## 푡
## +z
## 푡
## )−휑
trade
## 푡
## (z
## 푡
## )   =푅
x,푡
## ,
## 1/(1 +푅
x,푡
## )(1+휇
## 푡
## )∘(x
## 푡
## +z
## 푡
## )   =x
## 푡+1
## ,
## (11.4)
where we repeat all constraints for all푡= 0,...,퐻−1.
The multi-period objective is the sum of the single-period objectives for each period
푡. Here we implicitly assumed that the returns are independent random variables, so the
variance of their sum is the sum of the variances.
Unfortunately (11.4) is not a convex problem, because of the dynamic equation.
Therefore we have to make a simplification.
11.2.1 Simplified model
We can apply the simplification of returns discussed in section Sec. 11.1.4 and use the
approximate dynamics equationx
## 푡+1
## =x
## 푡
## +z
## 푡
. This also allows us to eliminate the trade
variablesz
## 푡
from the model, and arrive at a simpler form:
maximize
## ∑︀
## 퐻−1
## 푡=0
## 휇
## T
## 푡
x
## 푡+1
## −훿
## 푡
## ℛ
## 푡
## (x
## 푡+1
## )−
## −휑
hold
## 푡
## (x
## 푡+1
## )−휑
trade
## 푡
## (x
## 푡+1
## −x
## 푡
## )
subject to1
## T
x
## 푡+1
## +휑
hold
## 푡
## (x
## 푡+1
## ) +휑
trade
## 푡
## (x
## 푡+1
## −x
## 푡
## )   =1
## T
x
## 푡
## ,
x
## 푡+1
## −x
## 푡
## ∈ 풵
## 푡
## ,
x
## 푡+1
## ∈ 풳
## 푡
## ,
## (11.5)
where we repeat all constraints for all푡= 0,...,퐻−1.
Note that this simplification does not mean we disregard returns, we only approximate
the portfolio dynamics between periods. The returns are still taken into account in the
objective.
## 11.2.2 Extension
An extension of (11.5) is to specify the terminal portfolio after the last period. Choice
for the terminal portfolio could depend on the use case. Some reasonable choices could
be
•The predicted benchmark portfolio, which ensures that the optimal portfolio we get
will not deviate much from the benchmark.
•100%cash, which ensures that the optimal portfolio we get will not be expensive
to liquidate.
Since we never execute the optimal trades for all periods, the purpose of multiperiod
planning with a terminal constraint is to avoid moving towards undesired positions, not
to actually end up holding the terminal portfolio.
## 102

Problem (11.5) with the terminal constraint added will look like:
maximize
## ∑︀
## 퐻−1
## 푡=0
## 휇
## T
## 푡
x
## 푡+1
## −훿
## 푡
## ℛ
## 푡
## (x
## 푡+1
## )−
## −휑
hold
## 푡
## (x
## 푡+1
## )−휑
trade
## 푡
## (x
## 푡+1
## −x
## 푡
## )
subject to1
## T
x
## 푡+1
## +휑
hold
## 푡
## (x
## 푡+1
## ) +휑
trade
## 푡
## (x
## 푡+1
## −x
## 푡
## )   =1
## T
x
## 푡
## ,
x
## 푡+1
## −x
## 푡
## ∈ 풵
## 푡
## ,
x
## 푡+1
## ∈ 풳
## 푡
## ,
x
## 퐻
## =x
term
## ,
## (11.6)
wherex
term
is the desired terminal portfolio, and we repeat all constraints for all푡=
## 0,...,퐻−1.
## 11.3 Example
Here we show a code example of the multiperiod portfolio optimization problem (11.5).
In this setup, we will use the following specification:
•The risk function will be the variance:ℛ
## 푡
## (x
## 푡+1
## ) =x
## T
## 푡+1
## Σ
## 푡
x
## 푡+1
## .
•The trading cost function will include a linear term, and a market impact term:
## 휑
trade
## 푡
## (x
## 푡+1
## −x
## 푡
## )  =
## ∑︀
## 푁
## 푖=1
## 푎
## 푡,푖
## |푥
## 푡+1,푖
## −푥
## 푡,푖
## |+
## ̃
## 푏
## 푡,푖
## |푥
## 푡+1,푖
## −푥
## 푡,푖
## |
## 3/2
## .  The푎
## 푡,푖
are the
coefficients of the linear cost term, and the푏
## 푡,푖
are the coefficients of the market
impact cost term.푏
## 푡,푖
## =
## ̃
## 푏
## 푡,푖
## 휎
## 푡,푖
## /
## (︁
## 푞
## 푡,푖
## 푉
## 푡
## )︁
## 1/2
, where
## ̃
## 푏
## 푡,푖
## =  1,휎
## 푡,푖
is the volatility of
security푖in period푡, and
## 푞
## 푡,푖
## 푉
## 푡
is the normalized dollar volume of security푖in period
## 푡.
•There will be no holding cost term:휑
hold
## 푡
## (x
## 푡+1
## ) = 0.
•The set of trading constraints will be empty:풵
## 푡
## ={}.
•The set of holding constraints will contain the long only constraint:풳
## 푡
## ={x
## 푡+1
## ≥
## 0}.
Based on the above, we will solve the following multiperiod optimization problem:
maximize
## ∑︀
## 퐻−1
## 푡=0
## 휇
## T
## 푡
x
## 푡+1
## −훿
## 푡
x
## T
## 푡+1
## Σ
## 푡
x
## 푡+1
## −
## −
## (︁
## ∑︀
## 푁
## 푖=1
## 푎
## 푡,푖
## |푥
## 푡+1,푖
## −푥
## 푡,푖
## |+푏
## 푡,푖
## |푥
## 푡+1,푖
## −푥
## 푡,푖
## |
## 3/2
## )︁
subject to1
## T
## (x
## 푡+1
## −x
## 푡
## ) +
## (︁
## ∑︀
## 푁
## 푖=1
## 푎
## 푡,푖
## |푥
## 푡+1,푖
## −푥
## 푡,푖
## |+
## ̃
## 푏
## 푡,푖
## |푥
## 푡+1,푖
## −푥
## 푡,푖
## |
## 3/2
## )︁
## =   0,
x
## 푡+1
## ≥0,
## (11.7)
where we repeat all constraints for all푡= 0,...,퐻−1.
Then we rewrite (11.7) into conic form:
maximize
## ∑︀
## 퐻−1
## 푡=0
## 휇
## T
## 푡
x
## 푡+1
## −훿
## 푡
## 푠
## 푡
## −
## −
## (︁
## ∑︀
## 푁
## 푖=1
## 푎
## 푡,푖
## 푣
## 푡,푖
## +푏
## 푡,푖
## 푤
## 푡,푖
## )︁
subject to(푠
## 푡
## ,0.5,G
## T
## 푡
x
## 푡+1
## )∈ 풬
## 푁+2
r
## ,
## |푥
## 푡+1
## −푥
## 푡
## | ≤푣
## 푡
## ,
## (푤
## 푡,푖
## ,1,푥
## 푡+1,푖
## −푥
## 푡,푖
## )∈ 풫
## 2/3,1/3
## 3
## ,  푖= 1,...,푁
## 1
## T
x
## 푡+1
## +
## (︁
## ∑︀
## 푁
## 푖=1
## 푎
## 푡,푖
## 푣
## 푡,푖
## +푏
## 푡,푖
## 푤
## 푡,푖
## )︁
## =1
## T
x
## 푡
## ,
x
## 푡+1
## ≥0,
## (11.8)
## 103

where we repeat all constraints for all푡= 0,...,퐻−1.
Finally, we implement (11.7) in Fusion API. The following auxiliary functions encap-
sulate specific parts of modeling, and help us to write a clearer code:
def absval(M, x, z):
M.constraint(z >= x)
## M.constraint(z >= -x)
def norm1(M, x, t):
z = M.variable(x.getSize(), Domain.greaterThan(0.0))
absval(M, x, z)
M.constraint(Expr.sum(z) == t)
Next we present the Fusion model, built inside a function, that we can easily call
later.
def multiperiod_mvo(N, T, m, G, x_0, delta, a, b):
with Model("Multiperiod") as M:
## # Variables
## # - Portfolio
x = M.variable("x", [N, T], Domain.greaterThan(0.0))
## # - Risk
s = M.variable("s", T)
# - Linear transaction cost
v = M.variable("v", [N, T])
# - Market impact cost
w = M.variable("w", [N, T])
## # Constraint
M.constraint("budget", Expr.sum(x, 0) == np.ones(T))
## # Objective
M.objective("obj", ObjectiveSense.Maximize,
Expr.add([ x[:, t].T @ m[t] - delta[t] * s[t] - \
v[:, t].T @ a[:, t] - w[:, t].T @ b[:, t]
for t in range(T)]))
# Conic constraints related to the objective
for t in range(T):
xt = x[:, t]
xtprev = x_0 if t == 0 else x[:, t - 1]
xtdiff = xt - xtprev
## M.constraint(f'risk_{t}',
Expr.flatten(Expr.vstack(s[t], 0.5, G[t].T @ xt)),
Domain.inRotatedQCone()
## )
absval(M, xtdiff, v[:, t])
## M.constraint(f'market_impact_{t}',
Expr.hstack(w[:, t], Expr.constTerm(N, 1.0), xtdiff),
Domain.inPPowerCone(2 / 3)
## )
(continues on next page)
## 104

(continued from previous page)
# Solve the problem
## M.solve()
# Get the solution values
x_value = x.level().reshape(N, T)
return x_value
Next, we define the parameters. Here we assume that we have an estimate of the
average daily volume and daily volatility (std. dev.) for all periods.
# Number of securities
## N = 8
# Number of periods
## T = 10
# Initial weights
x_0 = np.array([1] * N) / N
portfolio_value = 10**8
# Transaction cost
a = 0.05 * np.ones((N, T))
# Market impact
beta = 3 / 2
b = 1
# The variable vol contains the volume estimates
rel_volume = [v / portfolio_value for v in vol]# Relative volume.
# The variable vty contains the volatility estimates
impact_coef = \
np.vstack([(b * v / r**(beta - 1)).to_numpy()
for v, r in zip(vty, rel_volume)]).T
Assuming also that we have a list of estimates of the yearly mean return and covariance
matrix for each trading period, we compute the matrixGsuch thatΣ=GG
## T
for all
periods, using Cholesky factorization.
# S is the list of covariance estimates
G = [np.linalg.cholesky(s) for s in S]
Finally, we run the optimization with the risk aversion parameter훿=  10for each
period.
delta = np.array([10] * T)
# m is the list of mean return estimates
x = multiperiod_mvo(N, T, m, G, x_0, delta, a, impact_coef)
## 105

## Chapter 12
Regression and regularization
Regression is statistical tool used in many disciplines, in particular in finance and invest-
ing. It is used to determine the type and strength of the function relationship between
statistical variables. In some cases when data is scarce or has errors, regularization is
also useful. In this chapter we introduce regression and regularizaton in the context of
conic optimization along the lines of [SHAD13], and show how to apply these methods
for portfolio optimization.
12.1 Linear regression
The most basic regression problem assumes a linear relationshipy=Xw+휀between
푁explanatory variablesX=  [x
## 1
## ,...,x
## 푁
## ]∈R
## 푇×푁
and dependent variabley∈R
## 푇
## ,
and attempts to estimatew. This is commonly done using the method ofordinary least
squares (OLS), which minimizes the norm of the residual termy−Xw. In other words, we
are looking for the coefficient vectorwthat is the optimal solution of the unconstrained
least squares optimization problem
minimize‖y−Xw‖
## 2
## .
## (12.1)
The same problem can also be written with squared norm:
minimize‖y−Xw‖
## 2
## 2
## .
## (12.2)
The geometric interpretation is that we are looking for the vector in the column space
ofXthat is closest toy.  If the problem is unconstrained, the solution is simply an
orthogonal projecton ofyonto the column space ofX.
## 1
## 1
OLS is an approximate solution to the overdetermined system of linear equationsXw≈y, where
wis the unknown.
## 106

## 12.1.1 Assumptions
LetX
## 푖
andX
## 푗
be two observations. For the OLS method to give meaningful results, we
have to impose some assumptions:
•Exogeneity:E(휀|X
## 푖
)  =  0, meaning that the error term is orthogonal to the
explanatory variables, so there are no endogeneous drivers forXin the model.
This also impliesCov(휀,X) = 0.
•No autocorrelation: The error terms are uncorrelated between observations. This
implies that the off-diagonal ofCov(휀
## 푖
## ,휀
## 푗
## |X
## 푖
## ,X
## 푗
)is zero.
•Homoscedasticity: The error term has the same variance for all observations, i. e.,
for any values of the explanatory variables. This implies thatVar(휀|X
## 푖
## ) =휎
## 2
## 1.
•No linear dependence: The observation matrixXmust have full column rank.
We also assume thatXhas at least as many rows as columns, i.e.,푇≥푁.
Some of the above assumptions can be relaxed by using specific extensions of the OLS
method. However, these extensions might be more complex and might have a greater
data requirement in order to produce an equally precise model.
## 12.1.2 Solution
Normal equations
If problem (12.1) is unconstrained, we can also derive its explicit solution called the
normal equations:
## X
## T
Xw=X
## T
y.
## (12.3)
Note however, that this should be used only as a theoretical result. In practice, it can be
numerically unstable because of the matrix inversion step when solving forw.
Conic optimization
If we convert the problem (12.2) into a conic optimization problem, we can not only solve
it in a more efficient and numerically stable way, but will also be able to extend the
problem with constraints. Here we state the conic equivalent of (12.1):
minimize푡
subject to(푡,y−Xw)∈ 풬
## 푇+1
## .
## (12.4)
For (12.2) we use the rotated quadratic cone,
minimize푡
subject to(푡,0.5,y−Xw)∈ 풬
## 푇+2
r
## .
## (12.5)
Let us now extend (12.5) with constraints:
minimize푡
subject to(푡,0.5,y−Xw)∈ 풬
## 푇+2
r
## ,
## 1
## T
w=   1,
w≥0.
## (12.6)
## 107

12.1.3 Portfolio optimization as regression problem
Portfolio optimization problems can also take the form of (12.2), if instead of working
with the covariance matrix of securitiesΣ, we work directly with the security return
observation matrix (scenario matrix)R∈R
## 푁×푇
defined in Sec. 3.1, where푇is the
number of observations.  We assume here that the matrix is centered.  Then for the
sample covariance matrix, we have
## Σ=
## 1
## 푇−1
## RR
## T
## .
## (12.7)
Equation (12.7) gives us a way to define the matrixXin problem (12.2):X=
## R
## T
## /
## √
## 푇−1.
Then we can write a simple benchmark relative optimization problem that minimizes
tracking error as
minimize‖R
## T
x−r
bm
## ‖
## 2
## 2
## ,
subject to1
## T
x=   1,
x≥0.
## (12.8)
where we omitted the factor1/
## √
푇−1from the objective, andr
bm
## =R
## T
x
bm
is the
benchmark return series, assumingxandx
bm
represent the same security universe. In
general, we could also assume thatxandx
bm
represent different security universes with
different return dataRandR
bm
.  That is equivalent to assuming the same (larger)
universe for both, with different security weights fixed to zero.
The conic form of (12.8) becomes
minimize푡
subject to(푡,0.5,R
## T
x−r
bm
## )∈ 풬
## 푇+2
r
## ,
## 1
## T
x=   1,
x≥0.
## (12.9)
## 12.2 Regularization
In some cases the data matrixXin (12.2) has nearly dependent columns, i.e., we have
high correlations between the corresponding explanatory variables. We can also have less
observations than variables (푇 < 푁). In these situations, the results can be unreliable
and highly sensitive to small perturbations and rounding errors. We discuss this topic in
detail in the context of portfolio optimization, see in Sec. 4. To handle these issues, we
can also use regularization techniques to stabilize the computational results.
Regularization typically means that we add a penalty term to our objective func-
tion, that helps to direct the solution procedure towards optimal solutionswthat have
favorable properties. This way of adjusting the objective can also be viewed as asoft
constraint, meaning that we express a preference regarding the quality of the optimal
solution, but without using exact bounds.
## 108

12.2.1 Example penalty terms
Here we discuss three examples of regularization terms, two of which are commonly
applied. Letw
## 0
be a specific solution vector with desired properties.
Ridge regularization
Ridge regularization adds a quadratic penalty term to the objective function:
minimize‖Xw−y‖
## 2
## 2
+휆‖Γ(w−w
## 0
## )‖
## 2
## 2
## .
## (12.10)
IfΓ =I, then it is called L2 regularization, because it simply gives preference to solution
vectors with smaller norms.
We can derive the normal equations also in this case, and we can observe that there
is a relation between ridge regularization and covariance shrinkage:
## (X
## T
## X+휆Γ
## T
Γ)w=X
## T
y+휆Γ
## T
## Γw
## 0
## .
## (12.11)
The conic equivalent of (12.10) will introduce an extra quadratic cone constraint for the
regularization term:
minimize푡+휆푢
subject to(푡,0.5,Xw−y)∈ 풬
## 푇+2
r
## ,
(푢,0.5,(Γw−w
## 0
## ))∈ 풬
## 푁+2
r
## .
## (12.12)
LASSO regularization
LASSO regularization adds a linear penalty term to the objective function:
minimize‖Xw−y‖
## 2
## 2
## +휆‖w−w
## 0
## ‖
## 1
## .
## (12.13)
It is also called L1 regularization or sparse regularization, because it gives preference to
sparse solutions, i.e., ones with few nonzeros.
The conic equivalent of (12.13) will model the 1-norm constraint for the regularization
term, as described in Sec. 13.1.1:
minimize푡+휆푢
subject to(푡,0.5,Xw−y)∈ 풬
## 푇+2
r
## ,
z−(w−w
## 0
## )≥0,
z+ (w−w
## 0
## )≥0,
## 1
## T
z−푢=   0.
## (12.14)
## The3/2regularization
The penalty term discussed here is not common, but has applications in modeling market
impact cost (see Sec. 6.3). We add a subquadratic penalty term to the objective function:
minimize‖Xw−y‖
## 2
## 2
## +휆‖w−w
## 0
## ‖
## 3/2
## 3/2
## ,
## (12.15)
where‖w−w
## 0
## ‖
## 3/2
## 3/2
## =
## ∑︀
## 푖
## |푤
## 푖
## −푤
## 0,푖
## |
## 3/2
## .
The conic equivalent of (12.15) uses the power cone for the regularization term,
minimize푡+휆
## ∑︀
## 푖
## 푢
## 푖
subject to(푡,0.5,Xw−y)∈ 풬
## 푇+2
r
## ,
## (푢
## 푖
## ,1,푤
## 푖
## −푤
## 푖,0
## )∈ 풫
## 2/3,1/3
## 3
## , 푖= 1,...,푁.
## (12.16)
## 109

12.2.2 Regularization in portfolio optimization
In the context of portfolio optimization, examples of regularization terms appear when we
penalize trading costs or do robust optimization. Here we show an example of a trading
cost penalty. For robust optimization, see Sec. 10.
## Let
## ̃
x=x−x
## 0
denote the traded amount with respect to the initial holdingsx
## 0
## . In
constrast to Sec. 6, where costs are part of the budget constraint, making the portfolio
self-financing, here we implement trading costs as penalties in the objectve function.
Suppose we have linear trading costs, expressed by the penalty‖
## ̃
x‖
## 1
and market
impact costs, expressed by the penalty‖
## ̃
x‖
## 3/2
## 3/2
. Then problem (12.8) with trading costs
will be
minimize‖R
## T
x−r
bm
## ‖
## 2
## 2
## +휆
## 1
## ‖
## ̃
x‖
## 1
## +휆
## 2
## ‖
## ̃
x‖
## 3/2
## 3/2
## ,
subject to1
## T
x=   1,
x≥0.
## (12.17)
The conic form of (12.17) becomes
minimize푡+휆
## 1
## 푢+휆
## 2
## ∑︀
## 푖
## 푣
## 푖
subject to(푡,0.5,R
## T
x−r
bm
## )∈ 풬
## 푇+2
r
## ,
z−
## ̃
x≥0,
z+
## ̃
x≥0,
## 1
## T
z−푢=   0,
## (푣
## 푖
## ,1, ̃푥
## 푖
## )∈ 풫
## 2/3,1/3
## 3
## , 푖= 1,...,푁,
## 1
## T
x=   1,
x≥0.
## (12.18)
## 12.3 Example
In this chapter we present the example (12.18) asMOSEKFusion code. We will use
yearly linear return scenario data from the same eight stocks used in other examples.
The benchmark will be the return series of the SPY ETF.
12.3.1 Data preparation
We generate the data the same way as in Sec. 3.4 up to the point where we have the
expected yearly logarithmic return vector휇
log
## ℎ
and covariance matrixΣ
log
## ℎ
. Then we gen-
erate Monte Carlo scenarios using these parameters, and convert these to linear returns.
The number푇is the number of observations we generate.
# Generate logarithmic return observations assuming normal distribution
scenarios_log = \
np.random.default_rng().multivariate_normal(m_log, S_log, T)
# Convert logarithmic return observations to linear return observations
scenarios_lin = np.exp(scenarios_log) - 1
Next, we center the data and separate security data from the benchmark data. Note
that we also scale the returns by the factor of1/
## √
푇−1coming from (12.7). We do
this because the relative magnitude of the tracking error term matters compated to the
## 110

magnitude of the regularization terms. We would like to control these relative magnitudes
only by setting휆
## 1
and휆
## 2
parameters.
# Center the return data
centered_return = scenarios_lin - scenarios_lin.mean(axis=0)
# Security return scenarios (scaled)
security_return = scenarios_lin[:, :N] / np.sqrt(T - 1)
# Benchmark return scenarios (scaled)
benchmark_return = scenarios_lin[:, -1] / np.sqrt(T - 1)
12.3.2 Optimization model
We start by defining the variables.  The variablexrepresents the portfolio,푡is the
tracking error,푢andvare the penalty terms. The latter three helps us to model the
objective terms as constraints. We also add the usual budget constraint here.
## # Variables
# The variable x is the fraction of holdings in each security.
# It is restricted to be positive - no short-selling.
x = M.variable("x", N, Domain.greaterThan(0.0))
xt = x - x0
# The variable t models the OLS objective function term (tracking error).
t = M.variable("t", 1, Domain.unbounded())
# The variables u and v model the regularization terms
# (transaction cost penalties).
u = M.variable("u", 1, Domain.unbounded())
v = M.variable("v", N, Domain.unbounded())
# Budget constraint
## M.constraint('budget', Expr.sum(x) == 1.0)
The objective function will thus be the sum of the above variables:
## # Objective
penalty_lin = lambda_1 * u
penalty_32 = lambda_2 * Expr.sum(v)
M.objective('obj', ObjectiveSense.Minimize,
t + penalty_lin + penalty_32)
The constraints corresponding to the penalty terms are modeled by the following rows:
# Constraints for the penalties
norm1(M, xt, u)
## M.constraint('market_impact',
Expr.hstack(v, Expr.constTerm(N, 1.0), xt),
Domain.inPPowerCone(1.0 / beta))
Thenorm1custom function definition will be given below where the full code of the
Fusion model is presented.
## 111

Finally, we implement the tracking error constraint:
# Constraint for the tracking error
residual = R.T @ x - r_bm
## M.constraint('tracking_error',
Expr.vstack(t, 0.5, residual),
Domain.inRotatedQCone())
The complete Fusion model will then be the following code:
def absval(M, x, z):
M.constraint(z >= x)
## M.constraint(z >= -x)
def norm1(M, x, t):
z = M.variable(x.getSize(), Domain.greaterThan(0.0))
absval(M, x, z)
M.constraint(Expr.sum(z) == t)
def MinTrackingError(N, R, r_bm, x0, lambda_1, lambda_2, beta=1.5):
with Model("Regression") as M:
## # Variables
# The variable x is the fraction of holdings in each security.
# It is restricted to be positive - no short-selling.
x = M.variable("x", N, Domain.greaterThan(0.0))
xt = x - x0
# The variable t models the OLS objective function term
# (tracking error).
t = M.variable("t", 1, Domain.unbounded())
# The variables u and v model the regularization terms
# (transaction cost penalties).
u = M.variable("u", 1, Domain.unbounded())
v = M.variable("v", N, Domain.unbounded())
# Budget constraint
## M.constraint('budget', Expr.sum(x) == 1.0)
## # Objective
penalty_lin = lambda_1 * u
penalty_32 = lambda_2 * Expr.sum(v)
M.objective('obj', ObjectiveSense.Minimize,
t + penalty_lin + penalty_32)
# Constraints for the penalties
norm1(M, xt, u)
## M.constraint('market_impact',
Expr.hstack(v, Expr.constTerm(N, 1.0), xt),
Domain.inPPowerCone(1.0 / beta))
# Constraint for the tracking error
(continues on next page)
## 112

(continued from previous page)
residual = R.T @ x - r_bm
## M.constraint('tracking_error',
Expr.vstack(t, 0.5, residual),
Domain.inRotatedQCone())
# Create DataFrame to store the results.
# Last security name (the SPY) is removed.
columns = ["track_err", "lin_tcost", "mkt_tcost"] + \
df_prices.columns[:N].tolist()
df_result = pd.DataFrame(columns=columns)
# Solve optimization
## M.solve()
# Save results
tracking_error = t.level()[0]
linear_tcost = u.level()[0]
market_impact_tcost = np.sum(v.level())
row = pd.Series(
[tracking_error, linear_tcost, market_impact_tcost] + \
list(x.level()), index=columns)
df_result = pd.concat([df_result, pd.DataFrame([row])],
ignore_index=True)
return df_result
## 12.3.3 Results
Here we show how to run the optimization model, and present the results. First, we set
the number of stocks, then we set the penalty coefficients휆
## 1
and휆
## 2
to desired values,
finally we also define the initial holdings vectorx
## 0
to be the equal weighted portfolio in
this case.
## N = 8
lambda_1 = 0.0001
lambda_2 = 0.0001
x0 = np.ones(N) / N
Then we run the optimization model:
df_result = MinTrackingError(N, security_return.T,
benchmark_return, x0, lambda_1, lambda_2)
The optimal portfolio composition is
x= [0.0900,0.1667,0.1681,0.1712,0.0481,0.1014,0.1173,0.1373].
## 113

## Chapter 13
## Appendix
13.1 Conic optimization refresher
In this section we give a short summary about conic optimization. Read more about
the topic from a mathematical and modeling point of view in our other publication, the
MOSEKModeling Cookbook [MOSEKApS24].
Conic optimization is a class of convex optimization problems, which contains and
generalizes in an unified way many specific and well known convex models. These models
includelinear optimization(LO),quadratic optimization(QO),quadratically constrained
quadratic optimization(QCQO),second-order cone optimization(SOCO), andsemidefi-
nite optimization(SDO). The general form of a conic optimization problem is
maximizec
## T
x
subject toAx+b∈ 풦.
## (13.1)
where풦is a product of the following basic types of cones:
•Linear cone:
## R
## 푛
## ,R
## 푛
## +
## ,{0}.
Linear cones model all traditionally LO problems.
•Quadratic cone and rotated quadratic cone:
The quadratic cone is the set
## 풬
## 푛
## =
## {︂
## 푥∈R
## 푛
## ⃒
## ⃒
## ⃒
## ⃒
## 푥
## 1
## ≥
## √︁
## 푥
## 2
## 2
## +···+푥
## 2
## 푛
## }︂
## .
The rotated quadratic cone is the set
## 풬
## 푛
r
## =
## {︀
## 푥∈R
## 푛
## ⃒
## ⃒
## 2푥
## 1
## 푥
## 2
## ≥푥
## 2
## 3
## +···+푥
## 2
## 푛
## , 푥
## 1
## ,푥
## 2
## ≥0
## }︀
## .
Modeling with these two cones cover the class of SOCO problems, which include all
traditionally QO and QCQO problems as well. See in Sec. 13.1.2 for more details.
•Primal power cone:
## 풫
## 훼,1−훼
## 푛
## =
## {︂
## 푥∈R
## 푛
## ⃒
## ⃒
## ⃒
## ⃒
## 푥
## 훼
## 1
## 푥
## 1−훼
## 2
## ≥
## √︁
## 푥
## 2
## 3
## +···+푥
## 2
## 푛
## , 푥
## 1
## ,푥
## 2
## ≥0
## }︂
## ,
or its dual cone.
## 114

•Primal exponential cone:
## 퐾
exp
## =
## {︂
## 푥∈R
## 3
## ⃒
## ⃒
## ⃒
## ⃒
## 푥
## 1
## ≥푥
## 2
exp
## (︂
## 푥
## 3
## 푥
## 2
## )︂
## , 푥
## 1
## ,푥
## 2
## ≥0
## }︂
## ,
or its dual cone.
•Semidefinite cone:
## 풮
## 푛
## +
## =
## {︀
## 푋∈R
## 푛×푛
## ⃒
## ⃒
푋is symmetric positive semidefinite
## }︀
## .
Semidefinite cones model all traditionally SDO problems.
Each of these cones allow formulating different types of convex constraints.
13.1.1 Selection of conic constraints
In the following we will list the constraints appearing in financial context in this book
and show how can we convert them to conic form.
Maximum function
We can model the maximum constraintmax(푥
## 1
## ,푥
## 2
## ,...,푥
## 푛
)≤푐using linear constraints
by introducing an auxiliary variable푡:
## 푡≤푐,
## 푡≥푥
## 1
## ,
## .
## .
## .
## 푡≥푥
## 푛
## .
## (13.2)
For instance, we could write a series of constraintsmax(푥
## 푖
## ,0)≤푐
## 푖
## , 푖= 1,...,푛as
t≤c,t≥x,t≥0,
## (13.3)
wheretis an푛-dimensional vector.
Positive and negative part
A special case of modeling the maximum function is to model the positive part푥
## +
and
negative part푥
## −
of a variable푥. We define these as푥
## +
= max(푥,0)and푥
## −
= max(−푥,0).
We can model them explicitly based on Sec. 13.1.1 by relaxing the definitions to
inequalities푥
## +
## ≥max(푥,0)and푥
## −
≥max(−푥,0), or we can also model them implicitly
by the following set of constraints:
## 푥=푥
## +
## −푥
## −
## ,
## 푥
## +
## , 푥
## −
## ≥0.
## (13.4)
Note however, that in either case a freedom remains in the magnitude of푥
## +
and푥
## −
## .
This is because in the explicit case we relaxed the equalities, and in the impicit case
only the difference of the variables is constrained. In other words it will be possible for
## 푥
## +
and푥
## −
to be both positive, allowing optimal solutions where푥
## +
=  max(푥,0)and
## 푥
## −
= max(−푥,0)does not hold. We could ensure that only either푥
## +
or푥
## −
is positive
## 115

and never both by stating the complementarity constraint푥
## +
## 푥
## −
= 0(or in the vector case
## ⟨x
## +
## ,x
## −
⟩= 0), but unfortunately such an equality constraint is non-convex and cannot
be modeled.
We can do workarounds to ensure that equalities푥
## +
= max(푥,0)and푥
## −
= max(−푥,0)
hold in the optimal solution. One approach is to penalize the magnitude of these two
variables, so that if both are positive in any solution, then the solver could always im-
prove the objective by reducing them until either one becomes zero. Another possible
workaround is to formulate a mixed integer problem; see Sec. 13.2.1.
Absolute value
We can model the absolute value constraint|푥| ≤푐using the maximum function by
observing that|푥|= max(푥,−푥)(see Sec. 13.1.1):
## −푐≤푥≤푐.
## (13.5)
Another possibility is to model it using the quadratic cone:
## (푐,푥)∈풬
## 2
## .
## (13.6)
Sum of largest elements
Thesum of the푚largest elementsof a vectorxis the optimal solution of the LO problem
maximizex
## T
z
subject to1
## T
z=푚,
## 0≤z≤1.
## (13.7)
Herexcannot be a variable, because that would result in a nonlinear objective. Let us
take the dual of problem (13.7):
minimize푚푡+1
## T
u
subject tou+푡≥x,
u≥0.
## (13.8)
Problem (13.8) is actually the same asmin
## 푡
## 푚푡+
## ∑︀
## 푖
max(0,푥
## 푖
−푡). In this casexcan
be a variable, and thus it can also be optimized.
Linear combination of largest elements
We can slightly extend the problem in Sec. 13.1.1 such thatzcan have an upper bound
c≥0, and there is a real number0≤푏≤푐
sum
instead of the integer푚, where푐
sum
## =
## ∑︀
## 푖
## 푐
## 푖
## :
maximizex
## T
z
subject to1
## T
z=푐
sum
## −푏,
## 0≤z≤c.
## (13.9)
This has the optimal objective푐
frac
## 푖
## 푏
## 푥
## 푖
## 푏
## +
## ∑︀
## 푖>푖
## 푏
## 푐
## 푖
## 푥
## 푖
, where푖
## 푏
is such that
## ∑︀
## 푖
## 푏
## −1
## 푖=1
## 푐
## 푖
## < 푏≤
## ∑︀
## 푖
## 푏
## 푖=1
## 푐
## 푖
, and푐
frac
## 푖
## 푏
## =
## ∑︀
## 푖
## 푏
## 푖=1
## 푐
## 푖
## −푏 < 푐
## 푖
## 푏
## .
## 116

If we take the dual of problem (13.9), we get:
minimize(푐
sum
## −푏)푡+c
## T
u
subject tou+푡≥x,
u≥0,
## (13.10)
which is the same asmin
## 푡
## (푐
sum
## −푏)푡+
## ∑︀
## 푖
## 푐
## 푖
max(0,푥
## 푖
## −푡).
Manhattan norm (1-norm)
Letx∈R
## 푛
and observe that‖x‖
## 1
## =|푥
## 1
## |+···+|푥
## 푛
|. Then we can model theManhattan
normor1-normconstraint‖x‖
## 1
≤푐by modeling the absolute value for each coordinate:
## −z≤x≤z,
## 푛
## ∑︁
## 푖=1
## 푧
## 푖
## =푐,
## (13.11)
wherezis an auxiliary variable.
Euclidean norm (2-norm)
Letx∈R
## 푛
and observe that‖x‖
## 2
## =
## √︀
## 푥
## 2
## 1
## +···+푥
## 2
## 푛
. Then we can model theEuclidean
normor2-normconstraint‖x‖
## 2
≤푐using the quadratic cone:
## (푐,x)∈풬
## 푛+1
## .
## (13.12)
Hyperbolic constraint
Letx∈R
## 푛
and observe that‖x‖
## 2
## 2
## =x
## T
x=푥
## 2
## 1
## +···+푥
## 2
## 푛
. Then we can model the
hyperbolicconstraintx
## T
x≤푦푧, where푦,푧≥0using the rotated quadratic cone:
## (푦,푧,x)∈풬
## 푛+2
r
## .
## (13.13)
Squared Euclidean norm
We can model thesquared Euclidean normorsum-of-squaresconstraint‖x‖
## 2
## 2
## ≤푐using
the hyperbolic constraint in Sec. 13.1.1 and the rotated quadratic cone:
## (︀
## 푐,
## 1
## 2
## ,x
## )︀
## ∈풬
## 푛+2
r
## .
## (13.14)
Quadratic form
Letx∈R
## 푛
and letQ∈ 풮
## 푛
## +
, i. e., a symmetric positive semidefinite matrix. Then we
can model thequadratic formconstraint
## 1
## 2
x
## T
Qx≤푐either using the quadratic cone or
the rotated quadratic cone. To see this, observe that there exists a matrixG∈R
## 푛×푘
such thatQ=GG
## T
. Of course this decomposition can be done in many ways, so the
matrixGis not unique. The most interesting cases are when푘≪푛orGis very sparse,
because these make the optimization problem much easier to solve numerically (see in
## Sec. 13.1.2).
Most common ways to compute the matrixGare the following:
## 117

•Cholesky decomposition:Q=CC
## T
, whereCis a lower triangular matrix with
nonnegative entries in the diagonal. From this decomposition we haveG=C∈
## R
## 푛×푛
## .
•Eigenvalue decomposition:Q=VDV
## T
, where the diagonal matrixDcontains the
(nonnegative) eigenvalues ofQand the unitary matrixVcontains the corresponding
eigenvectors in its columns. From this decomposition we haveG=VD
## 1/2
## ∈R
## 푛×푛
## .
•Matrix square root:Q=Q
## 1/2
## Q
## 1/2
, whereQ
## 1/2
is the symmetric positive semidefi-
nite “square root” matrix ofQ. From this decomposition we haveG=Q
## 1/2
## ∈R
## 푛×푛
## .
•Factor model: IfQis a covariance matrix of some data, then we can approximate
the data series with the combination of푘≪푛common factors. Then we have
the decompositionQ=훽Q
## 퐹
## 훽
## T
+D, whereQ
## 퐹
## ∈R
## 푘×푘
is the covariance of the
factors,훽∈R
## 푛×푘
is the exposure of the data series to each factor, andDis
diagonal.  From this, by computing the Cholesky decompositionQ
## 퐹
## =FF
## T
we
haveG= [훽F,D
## 1/2
## ]∈R
## 푛×(푛+푘)
. The advantage of factor models is thatGis very
sparse and the factors have a direct financial interpretation (see Sec. 5 for details).
After obtaining the matrixG, we can write the quadratic form constraint as a sum-
of-squares
## 1
## 2
x
## T
## GG
## T
x≤푐, which is a squared Euclidean norm constraint
## 1
## 2
## ‖G
## T
x‖
## 2
## 2
## ≤푐.
We can choose to model this using the rotated quadratic cone as
## (︀
## 푐,1,G
## T
x
## )︀
## ∈풬
## 푘+2
r
## ,
## (13.15)
or we can choose to model its square root using the quadratic cone as
## (︀
## √
## 푐,G
## T
x
## )︀
## ∈풬
## 푘+1
## .
## (13.16)
Whether to use the quadratic cone or the rotated quadratic cone for modeling can be
decided based on which is more natural. Typically the quadratic cone is used to model
2-norm constraints, while the rotated quadratic cone is more natural for modeling of
quadratic functions. There can be exceptions, however; see for example in Sec. 2.3.
## Power
Let푥∈Rand훼 >1. Then we can model thepowerconstraint푐≥|푥|
## 훼
or equivalently
## 푐
## 1/훼
≥|푥|using the power cone:
## (푐,1,푥)∈풫
## 1/훼,(훼−1)/훼
## 3
## .
## (13.17)
## Exponential
Let푥∈R. Then we can model theexponentialconstraint푡≥푒
## 푥
using the exponential
cone:
## (푡,1,푥)∈퐾
exp
## .
## (13.18)
## 118

## Log-sum-exp
## Let푥
## 1
## ,...,푥
## 푛
∈R. Then we can model thelog-sum-expconstraint푡≥log (
## ∑︀
## 푛
## 푖=1
## 푒
## 푥
## 푖
## )by
applying rule Sec. 13.1.1푛times:
## ∑︀
## 푛
## 푖=1
## 푢
## 푖
## ≤1,
## (푢
## 푖
## ,1,푥
## 푖
## −푡)∈퐾
exp
## , 푖= 1,...,푛
## (13.19)
Perspective of function
Theperspectiveof a function푓(푥)is defined as푠푓(푥/푠)on푠 >0.  From any conic
representation of푡≥푓(푥)we can reach a representation of푡≥푠푓(푥/푠)by substituting
all constants푐with their homogenized counterpart푠푐.
Perspective of log-sum-exp
## Let푥
## 1
## ,...,푥
## 푛
∈R. Then we can model the perspective of the log-sum-exp constraint
## 푡≥푠log
## (︀
## ∑︀
## 푛
## 푖=1
## 푒
## 푥
## 푖
## /푠
## )︀
by applying rule Sec. 13.1.1 on constraint (13.19):
## ∑︀
## 푛
## 푖=1
## 푢
## 푖
## ≤푠,
## (푢
## 푖
## ,푠,푥
## 푖
## −푡)∈퐾
exp
## , 푖= 1,...,푛
## (13.20)
13.1.2 Traditional quadratic models
Optimization problems involving quadratic functions often appear in practice. In this
section we show how to convert the traditionally QO or QCQO problems into conic
optimization form, because most of the time the solution of these conic models is com-
putationally more efficient.
Quadratic optimization
The standard form of a quadratic optimization (QO) problem is the following:
minimize
## 1
## 2
x
## T
## Qx+c
## T
x
subject toAx=b,
x≥0.
## (13.21)
The matrixQ∈R
## 푛×푛
must be symmetric positive semidefinite, otherwise the objective
function would not be convex.
Assuming the factorizationQ=GG
## T
withG∈R
## 푛×푘
, we can reformulate the problem
(13.21) as a conic problem by applying the method described in Sec. 13.1.1:
minimize푡+c
## T
x
subject toAx=b,
x≥0,
## (푡,1,G
## T
x)∈ 풬
## 푘+2
r
## .
## (13.22)
## 119

Quadratically constrained quadratic optimization
Consider the quadratically constrained quadratic optimization (QCQO) problem of the
form
minimize
## 1
## 2
x
## T
## Q
## 0
x+c
## T
## 0
x+푎
## 0
subject to
## 1
## 2
x
## T
## Q
## 푖
x+c
## T
## 푖
x+푎
## 푖
## ≤0,  푖= 1,...,푚.
## (13.23)
The matricesQ
## 푖
## ∈R
## 푛×푛
,푖=  0,...,푚must all be symmetric positive semidefinite,
otherwise the optimization problem would not be convex.
Assuming the factorizationQ
## 푖
## =G
## 푖
## G
## T
## 푖
withG
## 푖
## ∈R
## 푛×푘
## 푖
, we can reformulate the
problem (13.23) as a conic problem by applying the method described in Sec. 13.1.1 for
both the objective and the constraints:
minimize푡
## 0
## +c
## T
## 0
x+푎
## 0
subject to푡
## 푖
## +c
## T
## 푖
x+푎
## 푖
## ≤0,푖= 1,...,푚,
## (푡
## 푖
## ,1,G
## T
## 푖
x)∈ 풬
## 푘
## 푖
## +2
r
## , 푖= 0,...,푚.
## (13.24)
Practical benefits of conic models
The key step in the model conversion is to transform quadratic termsx
## T
Qxusing the
factorizationQ=GG
## T
, whereG∈R
## 푛×푘
. Assuming푘≪푛, it results in the following
benefits:
•The storage requirement푛푘ofGcan be much lower than the storage requirement
## 푛
## 2
/2ofQ.
•The amount of work to evaluatex
## T
Qxis proportional to푛
## 2
whereas the work to
evaluate‖G
## T
x‖
## 2
## 2
is proportional to푛푘only.
•No need to numerically validate positive semidefiniteness of the matrixQ. This
is otherwise difficult owing to the presence of rounding errors that can makeQ
indefinite.
•Duality theory is much simpler for conic quadratic optimization.
In summary, the conic equivalents are not only as easy to solve as the original QP or
QCQP problems, but in most cases also need less space and solution time.
13.2 Mixed-integer models
Mixed integer optimization (MIO) is an extension of convex optimization, which intro-
duces variables taking values only in the set of integers or in some subset of integers. This
allows for solving a much wider range of optimization problems in addition to the ones
convex optimization already covers. However, these problems are no longer convex. Han-
dling of integer variables make the optimization NP-hard and needs specific algorithms,
thus the solution of MIO problems is much slower. In many practical cases we cannot
expect to find the optimal solution in reasonable time, and only near-optimal solutions
will be available.
## 120

A general mixed integer optimization problem has the following form:
maximizec
## T
x
subject toAx+b∈ 풦,
## 푥
## 푖
## ∈Z,  푖∈ℐ.
## (13.25)
where풦is a cone andℐ ⊆ {1,...,푛}contains the indices of integer variables. We can
model any finite range for the integer variable푥
## 푖
by simply adding the extra constraint
## 푎
## 푖
## ≤푥
## 푖
## ≤푏
## 푖
## .
13.2.1 Selection of integer constraints
In the following we will list the integer constraints appearing in financial context in this
book and show how to model them.
## Switch
In some practical cases we might wish to impose conditions on parts of our optimization
model. For example, allowing nonzero value for a variable only in presence of a condition.
We can model such situations usingbinary variables(orindicator variables), which can
only take0or1values. The following set of constraints only allow푥to be positive when
the indicator variable푦is equal to1:
## 푥≤푀푦,
## 푦∈ {0,1}.
## (13.26)
The number푀here is not related to the optimization problem, but it is necessary to
form such a switchable constraint. If푦= 0, then the upper limit of푥is0. If푦= 1, then
the upper limit of푥is푀. This modeling technique is calledbig-M. The choice of푀
can affect the solution performance, but a nice feature of it is that the problem cannot
accidentally become infeasible.
If we have a vector variablexthen the switch will look like:
x≤M∘y,
y∈ {0,1}
## 푛
## ,
## (13.27)
where∘denotes the elementwise product. We accounted for a possibly different big-M
value for each coordinate.
Semi-continuous variable
A slight extension of Sec. 13.2.1 is to model semi-continuous variables, i. e. when푥∈
{0}∪[푎,푏], where0< 푎≤푏. We can model this by
## 푎푦≤푥≤푏푦,  푦∈{0,1}.
## (13.28)
## 121

## Cardinality
We might need to limit the number of nonzeros in a vectorxto some number퐾 < 푛.
We can do this with the help of an indicator vectoryof length푛, which indicates|x|̸=0
(see Sec. 13.2.1). First we add a big-M boundM∘yto the absolute value, and model it
based on Sec. 13.1.1. Then we limit the cardinality ofxby limiting the cardinality ofy:
x≤M∘y,
x≥ −M∘y,
## 1
## T
y≤퐾,
y∈ {0,1}
## 푛
## .
## (13.29)
Positive and negative part
We introduced the positive part푥
## +
and negative part푥
## −
of a variable푥in Sec. 13.1.1.
We noted that we need a way to ensure only푥
## +
or푥
## −
will be positive in the optimal
solution and not both. One such way is to use binary variables:
## 푥=푥
## +
## −푥
## −
## ,
## 푥
## +
## ≤푀푦,
## 푥
## −
## ≤푀(1−푦),
## 푥
## +
## , 푥
## −
## ≥0,
## 푦∈  {0,1}.
## (13.30)
Here the binary variable푦allows the positive (negative) part to become nonzero exactly
when the negative (positive) part is zero.
Sometimes we need to handle separately the case when both the positive and the
negative part is fixed to be zero. Then we need to introduce two binary variables푦
## +
and
## 푦
## −
, and include the constraint푦
## +
## +푦
## −
≤1to prevent both variables from being1:
## 푥=푥
## +
## −푥
## −
## ,
## 푥
## +
## ≤푀푦
## +
## ,
## 푥
## −
## ≤푀푦
## −
## ,
## 푥
## +
## , 푥
## −
## ≥0,
## 푦
## +
## +푦
## −
## ≤1,
## 푦
## +
## , 푦
## −
## ∈ {0,1}.
## (13.31)
13.3 Quadratic cones and riskless solution
In Sec. 6 we consider portfolio optimization problems with risk-free security. In this case
there is a difference in the computation of the efficient frontier, if we model using the
quadratic cone instead of the rotated quadratic cone. Namely, the optimization problem
will not have solutions that are a mix of the risk-free security and risky securities. Instead,
it will only have either the 100% risk-free solution, or a portfolio of only risky securities.
Along the derivation below we will see that the same behavior applies to problems not
having a risk-free security but havingx=0as a feasible solution.
Consider the following simple model:
maximize휇
## T
x+푟
f
## 푥
f
## −
## ̃
## 훿
## √
x
## T
## Σx
subject to1
## T
x+푥
f
## =   1,
x,푥
f
## ≥0,
## (13.32)
## 122

where푟
f
is the risk-free rate and푥
f
is the allocation to the risk-free asset.
We can transform this problem using푥
f
## = 1−1
## T
x, such that we are only left with
the variablex:
maximize(휇−푟
f
## 1)
## T
x+푟
f
## −
## ̃
## 훿
## √
x
## T
## Σx
subject to1
## T
x≤1,
x≥0.
## (13.33)
The feasible region in this form is a probability simplex. The solutionx=0means that
everything is allocated to the risk-free security, and the hyperplane1
## T
x= 1has all the
feasible solutions purely involving risky assets.
Let us denote the objective function value byobj(x). Then the directional derivative
of the objective along the directionu>0,||u||= 1will be
## 휕
u
obj(x) = (휇−푟
f
## 1)
## T
u−
## ̃
## 훿
x
## T
## Σu
## √
x
## T
## Σx
## .
This does not depend on the norm ofx, meaning that휕
u
obj(푐u)will be constant in푐:
## 휕
u
obj(푐u) = (휇−푟
f
## 1)
## T
u−
## ̃
## 훿
## √
u
## T
## Σu.
Thus the objective is linear along the 1-dimensional slice betweenx=0and anyx>0,
meaning that the optimal solution is eitherx=0or somex>0satisfying1
## T
x= 1.
Furthermore, along every 1-dimensional slice represented by a directionu, there is a
## ̃
## 훿threshold
## ̃
## 훿
u
## =
## (휇−푟
f
## 1)
## T
u
## √
u
## T
## Su
## .
This is the Sharpe ratio of all portfolios of the form푐u. If
## ̃
## 훿 >
## ̃
## 훿
u
then휕
u
obj(u)turns
negative.
In general, the larger we set
## ̃
훿, the fewer directionsuwill exist for which
## ̃
## 훿 <
## ̃
## 훿
u
, i.
e.,휕
u
obj(u)>0, and the optimal solution is a combination of risky assets. The largest
## ̃
훿for which we still have such a direction is
## ̃
## 훿
## *
= max
u
## ̃
## 훿
u
, the maximal Sharpe ratio.
The corresponding optimal portfolio is the one having the smallest risk while consisting
purely of risky assets. For
## ̃
## 훿 >
## ̃
## 훿
## *
we have휕
u
obj(u)<0in all directions, meaning that
the optimal solution will always bex=0, the 100% risk-free portfolio.
13.4 Monte Carlo Optimization Selection (MCOS)
We can use the following procedure to compare the accuracy of different portfolio opti-
mization methods.
- Inputs of the procedure are the estimated mean return휇and estimated covariance
Σ. Treat this pair of inputs as true values.
- Compute the optimal asset allocationxfor the original input pair(휇,Σ).
## 3. Repeat퐾
sim
times:
- Do parametric bootstrap resampling, i. e., draw a new푁×푇return data
sampleR
## 푘
and derive a simulated pair(휇
## 푘
## ,Σ
## 푘
## ).
## 123

- De-noise the covariance matrixΣ
## 푘
using the method in Sec. 4.2.2.
- Compute the optimal portfoliox
## 푘
using the optimization method(s) that we
wish to analyze.
- To estimate the error for each security in the optimal portfolio, compute the stan-
dard deviation of the difference vectorsx
## 푘
−x. Then by taking the mean we get a
single number estimating the error of the optimization method.
Regarding the final step, we can also measure the average decay in performance by
any of the following:
•the mean difference in expected outcomes:
## 1
## 퐾
sim
## ∑︀
## 푘
## (x
## 푘
## −x)
## T
## 휇
•the mean difference in variance:
## 1
## 퐾
sim
## ∑︀
## 푘
## (x
## 푘
## −x)
## T
## Σ(x
## 푘
## −w)
•the mean difference in Sharpe ratio or other metric computed from the above statis-
tics.
## 124

## Chapter 14
Notation and definitions
Here we list some of the notations used in this book.
14.1 Financial notations
•푁: Number of securities in the security universe considered.
## •푝
## 0,푖
: The known price of security푖at the beginning of the investment period.
## •p
## 0
: The known vector of security prices at the beginning of the investment period.
## •푃
## ℎ,푖
: The random price of security푖at the end of the investment period.
## •푃
## ℎ
: The random vector of security prices at the end of the investment period.
## •푅
## 푖
: The random rate of return of security푖.
•푅: The random vector of security returns.
•r: The known vector of security returns.
•R: The sample return data matrix consisting of security return samples as columns.
## •휇
## 푖
: The expected rate of return of security푖.
•휇: The vector of expected security returns.
•Σ: The covariance matrix of security returns.
## •푥
## 푖
: The fraction of funds invested into security푖.
•x: Portfolio vector.
## •x
## 0
: Initial portfolio vector at the beginning of the investment period.
## •
## ̃
x: The change in the portfolio vector compared tox
## 0
## .
## •푥
f
: The fraction of funds invested into the risk-free security.
## •푥
f
## 0
: The fraction of initial funds invested into the risk-free security.
## • ̃푥
f
: The change in the risk-free investment compared to푥
f
## 0
## .
## 125

## •푅
x
: Portfolio return computed from portfoliox.
## •R
x
: Sample portfolio return computed from data matrixRand portfoliox.
## •휇
x
: Expected portfolio return computed from portfoliox.
## •휎
x
: Expected portfolio variance computed from portfoliox.
•휇: Estimate of expected security return vector휇.
•Σ: Estimate of security return covariance matrixΣ.
•푇: Number of data samples or scenarios.
•ℎ: Time period of investment.
•휏: Time period of estimation.
14.2 Mathematical notations
## •x
## T
: Transpose of vectorx. Vectors are all column vectors, so their transpose is
always a row vector.
•E(푅): Expected value of푅.
•Var(푅): Variance of푅.
•Cov(푅
## 푖
## ,푅
## 푗
): Covariance of푅
## 푖
and푅
## 푗
## .
•1: Vector of ones.
•ℱ: Feasible region generated by a set of constraints.
## •R
## 푛
: Set of푛-dimensional real vectors.
## •Z
## 푛
: Set of푛-dimensional integer vectors.
•⟨a,b⟩: Inner product of vectorsaandb. Sometimes used instead of notationa
## T
b.
•diag(S): Vector formed by taking the main diagonal of matrixS.
•Diag(x): Diagonal matrix with vectorxin the main diagonal.
•Diag(S): Diagonal matrix formed by taking the main diagonal of matrixS.
•ℱ: Part of the feasible set of an optimization problem. Indicates that the problem
can be extended with further constraints.
•푒: Euler’s number.
## 126

## 14.3 Abbreviations
•MVO: Mean–variance optimization
•LO: Linear optimization
•QO: Quadratic optimization
•QCQO: Quadratically constrained quadratic optimization
•SOCO: Second-order cone optimization
•SDO: Semidefinite optimization
## 127

## Bibliography
[AJ12]A. Ahmadi-Javid. Entropic value-at-risk:  a new coherent risk mea-
sure.Journal  of  Optimization  Theory  and  Applications,  12  2012.
doi:10.1007/s10957-011-9968-2.
[AZ10]D. Avramov and G. Zhou. Bayesian portfolio analysis.Annual Review of
## Financial Economics, 2(1):25–47, 2010.
[BN01]J. Bai and S. Ng. Determining the number of factors in approximate factor
models.Econometrica, 01 2001. doi:10.1111/1468-0262.00273.
[BS11]J. Bai and S. Shi. Estimating high dimensional covariance matrices and
its applications.Annals of Economics and Finance, 12:199–215, 11 2011.
[BGP12]D. Bertsimas, V. Gupta, and I. Paschalidis. Inverse optimization:  a
new perspective on the black-litterman model.Operations Research,
60:1389–1403, 12 2012. doi:10.2307/23323707.
[BBD+17]S. Boyd, E. Busseti, S. Diamond, R. N. Kahn, K. Koh, P. Nys-
trup, and J. Speth. Multi-period trading via convex optimization. 2017.
arXiv:1705.00109.
[Bra10]M. W. Brandt. Chapter 5 - portfolio choice problems. InHandbook of
Financial Econometrics: Tools and Techniques, volume 1 of Handbooks
in Finance, pages 269–336. North-Holland, San Diego, 2010.
[CY16]J.  Chen  and  M.  Yuan.  Efficient  portfolio  selection  in  a  large
market.Journal  of  Financial  Econometrics,  14:496–524,  06  2016.
doi:10.1093/jjfinec/nbw003.
[Con95]G. Connor. The three types of factor models:  a comparison of their
explanatory power.Financial Analysts Journal,  51:42–46,  05 1995.
doi:10.2469/faj.v51.n3.1904.
[CM13]G. Coqueret and V. Milhau. Estimating covariance matrices for portfolio
optimization. 12 2013. EDHEC Risk Institute.
[CJPT18]G.  Cornuéjols,  J.  Peña,  and  R.  Tütüncü.Optimization  Meth-
ods  in  Finance.  Cambridge  University  Press,  2  edition,  2018.
doi:10.1017/9781107297340.
[CK20]Giorgio Costa and Roy H. Kwon. Generalized risk parity portfolio opti-
mization: an admm approach.J. of Global Optimization, 78(1):207–238,
sep 2020.
## 128

[dP19]M. López de Prado. A robust estimator of the efficient frontier.SSRN
Electronic Journal, 01 2019. doi:10.2139/ssrn.3469961.
[dPL19]M. López de Prado and M. Lewis. Detection of false investment strategies
using unsupervised learning methods.Quantitative Finance, 19:1–11, 07
- doi:10.1080/14697688.2019.1622311.
[DGNU09]V. Demiguel, L. Garlappi, F. Nogales, and R. Uppal. A generalized
approach to portfolio optimization:  improving performance by con-
straining portfolio norms.Management Science, 55:798–812, 05 2009.
doi:10.2139/ssrn.1004707.
[Dod12]J. Dodson. Why is it so hard to estimate expected returns? 2012. Uni-
versity of Minnesota, School of Mathematics. URL: https://www-users.
math.umn.edu/~dodso013/docs/dodson2012-lambda.pdf.
[EM75]B. Efron and C. Morris. Data analysis using stein's estimator and its gen-
eralizations.Journal of The American Statistical Association, 70:311–319,
06 1975. doi:10.1080/01621459.1975.10479864.
[EM76]B. Efron and C. Morris. Families of minimax estimators of the mean
of a multivariate normal distribution.The Annals of Statistics, 01 1976.
doi:10.1214/aos/1176343344.
[FS02]Hans Foellmer and Alexander Schied. Convex measures of risk and
trading  constraints.Finance  and  Stochastics,  6:429–447,  09  2002.
doi:10.1007/s007800200072.
[GI03]Donald Goldfarb and Garud Iyengar. Robust portfolio selection problems.
Math. Oper. Res., 28:1–38, 02 2003. doi:10.1287/moor.28.1.1.14260.
[GK00]Richard C. Grinold and Ronald N. Kahn.Active portfolio management.
McGraw-Hill, New York, 2 edition, 2000.
[Har91]W.V. Harlow. Asset allocation in a downside-risk framework.Financial
Analysts Journal, 47(5):28–40, 1991. doi:10.2469/faj.v47.n5.28.
[JM03]R. Jagannathan and T. Ma. Risk reduction in large portfolios: why im-
posing the wrong constraint helps.Journal of Finance, 58:1651–1684, 08
- doi:10.1111/1540-6261.00580.
[Jor86]P. Jorion. Bayes-stein estimation for portfolio analysis.Journal of Finan-
cial and Quantitative Analysis, 21:279–292, 09 1986. doi:10.2307/2331042.
[Jor04]P. Jorion. Portfolio optimization with tracking-error constraints.Financial
Analysts Journal, 01 2004. doi:10.2469/faj.v59.n5.2565.
[Kak16]Z. Kakushadze. Shrinkage = factor model.Journal of Asset Management,
17:, 03 2016. doi:10.1057/jam.2015.40.
[KS13]R. Karels and M. Sun. Active portfolio construction when risk and alpha
factors are misaligned. In C. S. Wehn, C. Hoppe, and G. N. Gregoriou, ed-
itors,Rethinking Valuation and Pricing Models, pages 399–410. Academic
Press, 12 2013. doi:10.1016/B978-0-12-415875-7.00024-5.
## 129

[KY91]Hiroshi Konno and Hiroaki Yamazaki. Mean-absolute deviation portfolio
optimization model and its applications to tokyo stock market.Manage-
ment Science, 37(5):519–531, 1991.
[Lau01]G. J. Lauprête.Portfolio risk minimization under departures from normal-
ity. Ph.D. Thesis, Massachusetts Institute of Technology, Sloan School of
Management, Operations Research Center., 2001. URL: http://dspace.
mit.edu/handle/1721.1/7582.
[LW03a]O. Ledoit and M. Wolf. Honey, i shrunk the sample covariance matrix.
The Journal of Portfolio Management, 07 2003. doi:10.2139/ssrn.433840.
[LW03b]O. Ledoit and M. Wolf. Improved estimation of the covariance matrix of
stock returns with an application to portfolio selection.Journal of Em-
pirical Finance, 10(5):603–621, 2003. doi:https://doi.org/10.1016/S0927-
## 5398(03)00007-0.
[LW04]O.  Ledoit  and  M.  Wolf.  A  well-conditioned  estimator  for  large-
dimensional covariance matrices.J. Multivariate Anal., 88(2):365–411,
- doi:https://doi.org/10.1016/S0047-259X(03)00096-4.
[LW20]O.  Ledoit  and  M.  Wolf.  Analytical  nonlinear  shrinkage  of
large-dimensional  covariance  matrices.The  Annals  of  Statistics,
48(5):3043–3065, 2020. doi:10.1214/19-AOS1921.
[LC98]E. L. Lehmann and G. Casella.Theory of Point Estimation. Springer,
New York, NY, 2 edition, 1998. doi:https://doi.org/10.1007/b98854.
[LMFB07]M. S. Lobo, M. Fazel, and S. Boyd. Portfolio optimization with linear and
fixed transaction costs.Annals of Operations Research, 152:341–365, 03
- doi:10.1007/s10479-006-0145-1.
[LB22]E. Luxenberg and S. Boyd. Portfolio construction with gaussian mixture
returns and exponential utility via convex optimization. 2022. URL: https:
//arxiv.org/abs/2205.04563, doi:10.48550/ARXIV.2205.04563.
[MWOS15]    R. Mansini, W. Ogryczak, and M. G. Speranza.Linear and Mixed Integer
Programming for Portfolio Optimization. Springer International Publish-
ing, 1 edition, 2015. doi:10.1007/978-3-319-18482-1.
[Meu05]A. Meucci.Risk and Asset Allocation. Springer-Verlag Berlin Heidelberg,
1 edition, 2005. doi:10.1007/978-3-540-27904-4.
[Meu10a]A. Meucci. Quant nugget 2: linear vs. compounded returns – common
pitfalls in portfolio management.GARP Risk Professional, pages 49–51,
04 2010. URL: https://ssrn.com/abstract=1586656.
[Meu10b]A. Meucci. Quant nugget 4:  annualization and general projection of
skewness, kurtosis and all summary statistics.GARP Risk Professional
- "The Quant Classroom", pages 59–63, 08 2010. URL: https://ssrn.com/
abstract=1635484.
## 130

[Meu10c]A. Meucci. Quant nugget 5: return calculations for leveraged securities and
portfolios.GARP Risk Professional, pages 40–43, 10 2010. URL: https:
## //ssrn.com/abstract=1675067.
[Meu11]A. Meucci.'the prayer'ten-step checklist for advanced risk and portfolio
management.SSRN, 02 2011. URL: https://ssrn.com/abstract=1753788.
[MM08]Richard Michaud and Robert Michaud.Efficient Asset Management: A
Practical Guide to Stock Portfolio Optimization and Asset Allocation 2nd
Edition. Oxford University Press, 2 edition, 01 2008.
[Pal20]D. P. Palomar. Risk parity portfolio. 2020. Lecture notes, The Hong Kong
University of Science and Technology.
[Ric99]J. A. Richards. An introduction to james–stein estimation. 11 1999. M.I.T.
EECS Area Exam Report.
[RU00]R. Rockafellar and S. Uryasev. Optimization of conditional value-at-risk.
Journal of risk, 2:21–42, 01 2000.
[RU02]R. T. Rockafellar and S. P. Uryasev. Conditional value-at-risk for general
loss distributions.Journal of Banking & Finance, 26(7):1443–1471, 2002.
doi:https://doi.org/10.1016/S0378-4266(02)00271-6.
[RUZ06]R. T. Rockafellar, S. P. Uryasev, and M. Zabarankin. Generalized devia-
tions in risk analysis.Finance and Stochastics, 10:51–74, 2006.
[RSTF20]D. Rosadi, E. Setiawan, M. Templ, and P. Filzmoser. Robust covari-
ance estimators for mean-variance portfolio optimization with trans-
action  lots.Operations  Research  Perspectives,  7:100154,  06  2020.
doi:10.1016/j.orp.2020.100154.
[RWZ99]M. Rudolf, H.-J. Wolter, and H. Zimmermann. A linear model for tracking
error minimization.Journal of Banking & Finance, 23(1):85–103, 1999.
doi:https://doi.org/10.1016/S0378-4266(98)00076-4.
[SHAD13]Thomas Schmelzer, Raphael Hauser, Erling Andersen, and Joachim Dahl.
Regression techniques for portfolio optimisation using mosek. 2013. URL:
https://arxiv.org/abs/1310.3397.
[The71]H. Theil.Principles of Econometrics. John Wiley and Sons, 1 edition, 06
## 1971.
[TLD+11]B. Tóth,  Y. Lemperiere,  C. Deremble,  J. Lataillade,  J. Kockelko-
ren, and J.-P. Bouchaud. Anomalous price impact and the critical na-
ture of liquidity in financial markets.Physical Review X, 05 2011.
doi:10.2139/ssrn.1836508.
[VD09]F.   J.   Nogales   V.   DeMiguel.   Portfolio   selection   with   ro-
bust  estimation.Operations  Research,   57(3):560–577,   02  2009.
doi:https://doi.org/10.1287/opre.1080.0566.
## 131

[WZ07]R. Welsch and X. Zhou. Application of robust statistics to asset allocation
models.REVSTAT, 5:97–114, 03 2007.
[WO11]M. Woodside-Oriakhi.Portfolio Optimisation with Transaction Cost. PhD
thesis, School of Information Systems, Computing and Mathematics,
## Brunel University, 01 2011.
[MOSEKApS24] MOSEK ApS.MOSEK Modeling Cookbook. MOSEK ApS, Fruebjergvej
3, Boks 16, 2100 Copenhagen O, 2024. Last revised April 2024. URL:
https://docs.mosek.com/modeling-cookbook/index.html.
## 132