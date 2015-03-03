#Plan and Target
- to finish first iteration before 8th March
- to review it before 15th March

**25 Feb 2015 (12-18)**
##Sample and Population (样本与总体)
总体是要研究对象的全体，样本是从总体中抽取出来的一部分。有的时候我们很难研究总体所有的对象，比如，测试全国人民的身高。所以我们通过对样本的研究而达到对总体的认识。

假设Population有N个对象，sample中有n个对象
###Mean

- Population mean

$$\mu=\cfrac{\sum_{i=1}^{N}x_i}{N}$$

- Sample Mean

$$\overline{X}=\cfrac{\sum_{i=1}^{n}}{n}{x_i}$$

###Variance
对于两组数据，有的时候Mean相近，但是他们非常不同，比如，如下两组Populations,
[2,2,3,3] and [0,0,5,5]，他们的Mean是相同的$$\mu_1=\mu_2$$, 但是Variance非常不一样

- Population Variance

$$\sigma^2 = \cfrac{\sum_{i=1}^{N}(x_i-\mu)^2}{N}$$

- Sample Variance

$$S^2=\cfrac{\sum_{i=1}^n{(x_i-\overline{X})^2}}{n}$$

上边的公式有的时候低估了Variance, 所以大部分时候采用下边的公式计算Variance

$$S^2=S_{n-1}^2=\cfrac{\sum_{i=1}^n{(x_i-\overline{X})^2}}{n-1}$$

###Standed Deviation

$$\sigma=\sqrt{\sigma^2}$$

$$S=\sqrt{S^2}$$

###Other:
variance可以采用下班的公式来计算
$$\sigma^2=\cfrac{\sum_{i=1}^{N}(x_i-\mu)^2}{N}
\\=\cfrac{\sum_{i=1}^{N}(x_i^2-2x_i\mu+\mu^2)}{N}
\\=\cfrac{\sum_{i=1}^{N}x_i^2}{N}-2\cfrac{\sum_{i=1}^{N}x_i\mu}{N}+\cfrac{\sum_{i=1}^{N}\mu^2}{N}
\\=\cfrac{\sum_{i=1}^{N}x_i^2}{N}-2\cfrac{\mu\sum_{i=1}^{N}x_i}{N}+\cfrac{\mu^2\sum_{i=1}^{N}1}{N}
\\=\cfrac{\sum_{i=1}^{N}x_i^2}{N}-2\mu^2+\mu^2
\\=\cfrac{\sum_{i=1}^{N}x_i^2}{N}-\mu^2$$



##Random Variable(随机变量)

随机变量类似一个函数，把随机过程映射到数值。比如，下边的例子把下雨和不下雨映射为数值。从而可以量化随机试验。

$$X=\begin{cases} 0 \quad \text{Not Raining} \\1 \quad \text{Raining} \end{cases}$$

有两种类型的随机变量: Discrete, Continuous

continues Random variable example: 
X = Exact amount of raning in inches tomorrow

##Probability Distribution and Density function(分布与密度函数)

在定义了随机变量后，对离散的随机变量，可以有随机变量的分布，比如

X = # of facing up on a fair dice

|X|1|2|3|4|5|6|
|---|---|---|---|---|---|---|
|P(X)|1/6|1/6|1/6|1/6|1/6|1/6|


$$P(X=6) = \cfrac{1}{6}$$

对于连续的随机变量，可以有密度函数


##Expectation(期望)
可以用来计算无穷数量总体的均值,期望值也就是该随机变量总体的均值

Suppose random variable X can take value $$x_1$$ with probability $$p_1$$, value $$x_2$$ with probability $$p_2$$, and so on, up to value $$x_k$$ with probability $$p_k$$, Then the **expectation** of this random variable X is defined as $$E[X]=x_1p_1+x_2p_2+...+x_kp_k$$

在我们有了随机变量X,以及其分布或者密度函数，那么就可以根据公式计算期望。根据大数定理，期望也可以通过观察得到。

**26 Feb 2015 (1) (19-27)**
##Binormal Distributions(二项分布)

X= # of heads after 5 flips

$$P(X=0)=P(TTTTT)=(1/2)^5=\cfrac{1}{32}$$
$$P(X=1)=P(HTTTT)+P(THTTT)+P(TTHTT)+P(TTTHT)+P(TTTTH)=\cfrac{5}{32}$$
$$P(X=2)=P(HHTTT)+P(HTHTT)+...+P(HTTTH)+...=\cfrac{10}{32}$$

这里可以想像成从五个位置选择两个，可以看成是一个有序的重复抽样 (从n＝5中选择m＝2)，可能有$$n\times(n-1)\times...\times(n-m+1)$$个结果，也就是$$\cfrac{n!}{(m+1)!}=\cfrac{5!}{3!}$$种可能，但是位置一和位置二不同的可能性有$$2!$$,但是实际上在二项分布中，他们是相同的，比如都是H,所以要除以$$2!$$

$$P(X=2)=\cfrac{5!}{2!3!}\times\cfrac{1}{32}=\cfrac{10}{32}$$

In general
$$P(X=m)=\cfrac{5!}{m!(5-m)!}\times\cfrac{1}{32}$$

在上一个例子种，投一次硬币为正反面的概率相同，都为0.5，但是如果不同呢，在下边举例说明
X=# of shots I makes when take 10 shots (n=5) with $$p_{Make}=0.3$$
$$P(X=0)=0.7\times0.7\times0.7\times0.7\times0.7=0.7^5$$
$$P(X=1)=MNNNN+NMNNN+...NNNNM=5\times0.3\times0.7^4$$
$$p(X=2)=MMNNN+MNMNN+...=\cfrac{5!}{2!(5-2)!}\times0.3^2\times0.7^3$$

In general, 试验n次，发生m次的概率
$$P(X=m)=\cfrac{n!}{m!(n-m)!}p^m(1-p)^{n-m}$$


###Expectation of Binormal Distributions
X=# of successes with probability P after n trials

$$E(X) = n.p $$ 


##Possion Distribution
$$\lim\limits_{x\to\infty} (1+\cfrac{a}{x})^x = e^a$$

令$$\cfrac{1}{n}=\cfrac{a}{x}$$ then $$x=na$$ 

then $$\lim\limits_{x\to\infty} (1+\cfrac{a}{x})^x = \lim\limits_{n\to\infty} (1+\cfrac{1}{n})^{na}=(\lim\limits_{n\to\infty} (1+\cfrac{1}{n})^{n})^a=e^a$$

$$\cfrac{x!}{(x-k)!}=x(x-1)(x-2)...(x-k+1)$$

X=#of cars per hour
这是一个Possion分布，Possion是一个二项分布去极限的情况，假设这一个小时可以划分为n个相等的时间段，比如一秒，n趋于无穷大的时候，没个划分就相当于一个时刻，那么问题就转化成在n个划分上，其中有m个划分有车辆通过的分布

$$P(X=m)=\lim\limits_{n\to\infty}\cfrac{n!}{m!(n-m!)}p^m(1-p)^{n-m}$$

$$E(X)=\lambda$$ 很容易可以通过观察得到
对于二项分布 $$E(X)=np$$ 所以可以得到$$p=\cfrac{\lambda}{n}$$,代入到Possion分布的公式

$$P(X=m)=\lim\limits_{n\to\infty}\cfrac{n!}{m!(n-m!)}(\cfrac{\lambda}{n})^m(1-\cfrac{\lambda}{n})^{n-m}$$

取极限后可以得到
$$P(X=m)=\cfrac{\lambda^m}{m!}e^{-\lambda}$$

##the Law of Large Number (大数定理)
大数定理告诉我们在样本的数量足够大的时候，样本均值接近期望值，也就是总体的均值

For example, X= # of heads after 100 tosses of fair coin

E(X) = 100*0.5 = 50

所以这里一次试验指的是抛100次硬币，得到正面的数量

重复这个试验n次，那么样本的均值就是
$$\overline{X_n}=\cfrac{55+65+45+...+x_n}{n}$$

当n趋于无穷大的时候，样本均值$$\overline{X_n}应该趋于50。

**26 Feb 2015 (28-34) TODO**
##Normal(Gaussian) Distribution(正态分布)

$$P(X=x)=\cfrac{1}{\sigma\sqrt{2\pi}}e^{-\cfrac{1}{2}(\cfrac{x-\mu}{\sigma})^2}$$


###z-score

**27 Feb 2015 (35-46) TODO**
##Central Limit Theorem (中心极限定理)

随着每一个样本size的增加，样本均值的分布趋于正态分布，

比如，我们有一个随机变量X, 无论这个随机变量的分布P(X)是什么分布，假设这个分布的variance为$$\sigma$$在这个分布上做多次的抽样，每次抽样的个数设置为n (n=4), 每个抽样的平均值组成的分布随着n变大，趋于正态分布。

比如第一个样本均值分布(Sample size of n=4) 

$$S_1 = [1,1,3,6]$$ $$\overline{X_1}=2.75$$

$$S_2 = [3,4,3,1]$$ $$\overline{X_2}=2.75$$

$$S_3 = [1,1,6,6]$$ $$\overline{X_3}=3.5$$

...

$$S_{1000} = [...]$$


第二个样本均值分布(Sample size of n=8)

$$S_1 = [1,1,3,6,7,8,4,9]$$ $$\overline{X_1}=...$$

$$S_2 = [3,4,3,1,3,4,5,6]$$ $$\overline{X_2}=...$$

$$S_3 = [1,1,6,6,3,4,5,5]$$ $$\overline{X_3}=...$$

...

$$S_{1000} = [...]$$

由第二个样本均值组成的分布更趋于正态分布,并且样本均值分布的方差


$$\sigma_{\overline{X}}^2=\cfrac{\sigma^2}{n}$$


###Sample Distribution of the sample mean

onlinestatbook.com

##Confidence Interval(置信区间)

In a local teaching district a technology grant is available to teachers in order to install a cluster of four computers in their classrooms. From the 6250 teachers in the district. 250 were randomly selected and asked if they felt that computers where an essential teaching tool for their classroom. Of those selected 142 teachers felt that computers were an essential teaching tool.

1. Calculate a 99% confidence interval for the proportion of teachers who felt that computers are an essential teaching tool.

计算机是否是必须的教具这是一个Bernoulli分布，可以定义随机变量X

$$X=\begin{cases} 0 \quad \text{Not Essential} \\1 \quad \text{Essential} \end{cases}$$

假设是必须的概率为$$p$$, 那么不是的概率为$$1-p$$, 那么其分布如下表

|-|Not Essential|Essential|
|---|---|---|
|X|0|1|
|p(X)|1-p|p|



随机变量的期望为 $$\mu=p$$

根据中心极限定理，任何概率分布的抽样均值的分布是一个正态分布，在每次抽样的样本数量$$n$$足够大的时候(一般情况$$n\gt30$$)。 这次试验，抽样$$n=250$$, 所以起抽样均值的分布可以看成是一个正态分布. $$\mu_{\overline{X}}=\mu=p$$, $$\sigma_{\overline{X}}^2=\cfrac{\sigma^2}{n}$$, 但是我们现在不知道随机变量X的Variance($$\sigma^2$$), 在这里用这次抽样的Variance ($$S^2$$) 来替代 $$\sigma^2$$

$$\overline{X}=\cfrac{1\times(250-142)+1\times142}{250}=0.568$$

$$S^2=\cfrac{(0-0.568)^2\times(250-142)+(1-0.568)^2\times142}{250-1}=0.24636$$

$$\sigma\approx\hat{\sigma}=\sqrt{S^2}=0.496\approx0.5$$

所以对样本均值分布 $$\sigma_{\overline{X}}=\cfrac{\sigma}{\sqrt{n}}\approx\cfrac{0.5}{250}=0.002$$


2. How could the survey be changed to narrow the confidence interval but to maintain the 99% confidence interval?




###Small sample size confidence interval

对于样本size很小的时候，要采用t分布来代替正态分布，也就是说样本均值的分布是服从t分布

7 Patients' blood pressures have been measured after having been given a new drug for 3 months. They had blood pressure increases of 1.5, 2.9, 0.9, 3.9, 3.2, 2.1 and 1.9. Construct a 95% confidence interval for the true expected blood pressure increase for all patients in a population

##Bernoulli Distribution (伯努力分布)


这里的样本均值相当于来自样本均值分布的抽样

So when we get our sample mean we are sampling from the sampling distribution of the sample mean



**28 Feb 2015 (47-61) TODO**

##
A neurologist is testing the effect of a drug on response time by injecting 100 rats with a unit dose of the drug, subjecting each to neurological stimulus(刺激), and recording its response time. The neurologist knows that the mean response time for rats not injected with the drug is 1.2 seconds. The mean of the 100 injected rats' response time is 1.05 seconds with a sample standard deviation of 0.5 seconds. Do u think that the drug has an effect on reponse time?

$$H_0$$:Drug has no effect $$\mu=1.2s$$ (even with drug)

$$H_1$$:Drug has effect $$\mu not =1.2s$$ (even with drug)

Assume that null h is true, 

Z-statistic and t-statistic
n>30 and n is smaller

t-test
The mean emission of all engines of a new design needs to be below 20 ppm if the design is to meet new emission requierments. Ten engines are manufactured fro testing purposes, and the esmission level of each is determined. The emission data is 15.6 16.2 22.5 20.5 16.4 19.4 16.6 17.9 12.7 13.9

Does the data supply sufficient evidence to conclude that this type of engine meets the new standard? Assume we are willing to risk a Type I error with Probability = 0.01

t统计量的置信区间
95% confidence interval

95% and (n-1)=9 fredomm



##??
We want to test the hypothesis that more than 30% of U.S. households have internet access (with a significance level of 5%). We collect a sample of 150 households and find that 57 have access.

H0: p; les than or equals 30%
H1: P greater than 30%

Assume Ho is True,

##均值之差的置信区间
We are trying to test wheather a new, low-fat diet actually helps obese pople lose weight. 100 randomly assigned obese people are assigned to group 1 and put on the low fat diet. Another 100 randomly assigned obese (陪胖的，过重的) people are assigned to group 2 and put on a diet (日常饮食) of approximately the same amount of food, but not as low in fat. After 4 months, the mean weight loss was 9.31 lbs. for group 1 (s=4.67) and 7.40 lbs. (s=4.04) for group 2.





