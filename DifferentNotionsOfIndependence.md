# Different Notions of Independence for Ensembles of Noisy judges

Algebraic evaluators do not use probability distributions so their notion of
independence is different than the one utilized by evaluators that use them.
The notion of independence most commonly used in the AI literature is defined
in terms of the expectation of distributions - an infinite sample viewpoint.
For algebraic evaluators we have to use sample defined quantities.

The sample defined error correlations defined below should be familiar to
readers that understand independence of distributions. It is a standard
observation in papers discussing distributions to note that "we only have
a finite sample estimate of ..." That is, any expression using expectations
over infinite samples can be approximated by a sum over a finite one.

This observation is almost reflexive and indicative of how the statistics of
infinite samples frames the problems it tries to solve. A sample and any
quantity derived from it is viewed as a possibly unreliable witness for the
infinite population it represents. Therefore, a finite sample estimate will
not be equal to the expectation of a statistic in general.

The algebra of finite decision samples detailed in this submission takes a
different approach. Every sample derived quantity is **exactly** equal to an
algebraic expression involving known and unknown sample staistics. It is this
strict equality that allows us to derive general results such as the universal
surface for n classifiers and the core theorem.

A few simple examples illustrate how algebraic evaluators differ from
distribution based approaches in their treatment of error indepedence. Imagine
an iid process that produces a finite sample of decisions for n judges. That
sample may have non-zero error correlations between the ensemble members. The
reader can easily try this using the notebook with the core theorem. The
calculations in that notebook simulate an ensemble of error independent judges.
As the sample size of the evaluation test decreases, the sample error
correlations increase as expected. Likewise, a non-independent process that
generates the judges' decisions, may, on occasion, produce finite samples that
have zero correlation.

## Sample Defined Error Correlations for an Ensemble of Binary Classifiers

$$
\Gamma = \frac{1}{{D_{\ell}}} \sum_{d \in D_{\ell}} \
\prod_{i=1}^{m} (1_{\ell_{i,d},\ell} - P_{i,\ell})
$$
