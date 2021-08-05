# Methods-in-Quantitative-Statistical-Analysis

Methods in Quantitative Statistical Analysis, What is hypothesis testing?. Hypothesis testing is an act in statistics whereby an analyst tests an assumption regarding a population parameter.

Major four principles involved in a statistical test.

    Evolving a test statistic
    To know the sampling distribution of the test statistic
    Setting of hypotheses
    Decision rule or inference about the probable truth

In statistics most of the testing methods are comes under parametric hypothesis and Nonparametric hypothesis.

Parametric Hypothesis

In a parametric hypothesis, A statistical hypothesis is an assertion about a parameter of a population.

For example, the life of an electric bulb is 3000 hours ie, µ=3000 hours. Two bulb manufacturing processes produce bulbs of the same average life etc. ie, µ1=µ2.

According to R A Fisher, any hypothesis tested for its possible rejection is called a Null Hypothesis.

Population parameter or parameters which provides an alternate to null hypothesis within the range of pertinent values of the parameters and it is denoted as H1.

Let us understand what are the different types of methods of testing under parametric hypothesis.

The names of Methods in Quantitative Statistical Analysis are

    Likelihood ratio test
    Student’s t-test
    Normal deviate test or Z test
    Chi-square test
    F-test
    Bayes test
    Sequential probability ratio test (SPRT)

Likelihood ratio test

In the likelihood ratio test, we consider the likelihood functions under H0 and under the entire parametric space.

Λ(x)=L(x/ θ0)/L(x/ θ)

The value of Λ(x) lies between 0 and 1.
Students t-Test

Student t  is the deviation of the estimated mean from its population mean expressed in terms of standard error.

We can test H0:µ= µ0 vs H1: µ≠ µ0,

H0:µ= µ0 vs H1: µ> µ0

or µ< µ0, the test statistic remains the same.

The only difference in the test procedure is that the critical value of t is only on one side.

In R you can calculate the same based on the below syntax.

t.test(x, y,
       alternative = c("two.sided", "less", "greater"),
       mu = 0, paired = FALSE, var.equal = FALSE,
       conf.level = 0.95)

Normal Deviate test

A test of H0: µ= µ0 of a normal population N(µ, σ2) against an alternative hypothesis H1 can be tested by normal deviate test provide the population variance σ2 is known or the sample drawn is large say >30.

When the sample size is large enough, it is supposed that the sample variance is almost equal to the population variance. Usually, I is denoted as Z.

Z= (x̅- µ0)/( σ/sqrt(n))

In R you can used below mentioned code for Z test

z.test(x, y = NULL, alternative = "two.sided", mu = 0, sigma.x = NULL,
  sigma.y = NULL, conf.level = 0.95)

What is the minimum number of experimental units required in study?
Chi-square test

A Chi-square test is performed which measures the discrepancy between the observed frequencies and theoretically determined frequencies from the assumed distribution for the same event.

If the discrepancy is not large, it is considered that our assumption about the distribution of the variables is correct, otherwise not.

chisq.test(x, y = NULL, correct = TRUE,
           p = rep(1/length(x), length(x)), rescale.p = FALSE,
           simulate.p.value = FALSE, B = 2000)

once you created the data frame as a table structure simply use following code

data("mtcars")
table(mtcars$carb, mtcars$cyl)
chisq.test(mtcars$carb, mtcars$cyl)

If the cell frequencies are less than 5 you can try for fisher’s exact test.
F-test

Analysis of variance is a device to split the total variance of an experiment or trial into component variances responsible for contributing towards total variance.

Analysis of variance utilizes the F test.

Each component variance is tested against error variance.

F is the ratio between sample variances and within-sample variance.

F=Between sample variances/Within sample variances
Bayes test

Suppose that we need to decide between two hypotheses H0 and H1. In the Bayesian setting, we assume that we know prior probabilities of H0 and H1.

That is, we know P(H0)=p0 and P(H1)=p1, where p0+p1=1.


Sequential Probability ratio test (SPRT)

In the case of tests based on fixed sample size, It is generally not possible to determine the optimum sample sizes so that no extra observations are recorded except those necessitated to reach a decision.

Sometimes the sample is too small to arrive a proper decision. To overcome this problem, in 1947 Wald innovated the probability ratio test.

In this test procedure, a decision about H0 is taken after each successive observation.

That is in SPRT, sample size n is a random variable. So investigator can come up with three decision criteria namely,

Reject H0, Accept H0, or Continue sampling. And the process is continuing until taken a decision either to reject or to accept Ho.
