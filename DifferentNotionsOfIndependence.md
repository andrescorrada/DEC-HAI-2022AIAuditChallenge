# Different Notions of Independence for Ensembles of Noisy Judges

Algebraic evaluators do not use probability distributions so their notion of
independence is different than the one used by evaluators that use them.
The notion of independence most commonly used in the AI literature is defined
in terms of the expectation of distributions - an infinite sample viewpoint.
For algebraic evaluators we have to use sample defined quantities.

The sample defined error correlations defined below should be familiar to
readers that understand independence of distributions. It is a standard
observation in papers discussing distributions to note that 'we only have
a finite sample estimate of...'. That is, any expression using expectations
over infinite samples can be approximated by a sum over a finite one.

This observation is almost reflexive and indicative of how the statistics of
infinite samples frames the problems it tries to solve. A sample and any
quantity derived from it is viewed as a possibly unreliable witness for the
infinite population it represents. Therefore, a finite sample estimate will
not be equal to the expectation of a statistic in general.

The algebra of finite decision samples detailed in this submission takes a
different approach. Every sample derived quantity is **exactly** equal to an
algebraic expression involving known and unknown sample statistics. It is this
strict equality that allows us to derive general results such as the universal
surface for n classifiers and the core theorem.

A few simple examples illustrate how algebraic evaluators differ from
distribution-based approaches in their treatment of error indepedence. Imagine
an iid process that produces a finite sample of decisions for n judges. That
sample may have non-zero error correlations between the ensemble members. The
reader can easily try this using the notebook with the core theorem. The
calculations in that notebook simulate an ensemble of error-independent judges.
As the sample size of the evaluation test decreases, the sample error
correlations increase as expected. Likewise, a non-independent process that
generates the judges' decisions may, on occasion, produce finite samples that
have zero correlation.

## Sample Defined Error Correlations for an Ensemble of Binary Classifiers

The definition of error correlation for binary classifiers is as follows,

$$ \Gamma_{\ell ;1,2 \ldots m} = \frac{1}{{D_{\ell}}} \sum_{d \in D_{\ell}} \prod_{i=1}^{m} (1_{\ell_{i,d},\ell} - P_{i,\ell}). $$

The indicator functions $1_{\ell_{i,d},\ell}$ are $1$ when classifier $i$
decided correctly on the label of item $d$, and $0$ otherwise. Note, that like
the accuracy of the classifiers on the sample or the prevalence of either label,
these correlations are also integer ratios. Those integer ratios for the 2-way
and 3-way correlations between classifiers in a trio can be seen throughout the
Mathematica notebooks.

These error correlations are notable because they allow us to write down a set
of polynomials that exactly describe any arbitrarily correlated ensemble of
binary classifiers. These are horrendously complicated polynomials. They are
an application of the *method of moments* to the decisions of noisy judges.

This is where the power of finite samples comes in. These error correlations,
along with the label accuracies and prevalences, are all that is needed. It is
a finite-sized universe that describes all possible evaluations of binary
classifiers. There are no unknown unknowns in algebraic evaluation of binary
classifiers. That advantage should be leveraged in AI audits.

### The number of known unknowns

Most of the submission is confined to discussions of the $2n +1$ dimensional
space defined by one label prevalence and the label accuracies of the $n$ binary
classifiers. Along with the error correlations above, we can now measure how big
the known unknown space of evaluating arbitrarily correlated binary classifiers
is. We have the $2n + 1$ space without error correlations. To that we must add,
for each label,  the ${n \choose 2}$ 2-way error correlations, the
${n \choose 3}$ 3-way error  correlations and so on all the way to the n-way
error correlations. Adding up all those contributions we get a final size for
the dimension of the known unknown space needed to evaluate binary classifiers:
$$2^{n+1} -1.$$

This finite dimensional space will be eventually understood. Data Engines
currently works with algebraic evaluators that use 2-way correlations. One can
view this as an error correction methodology. To understand 2-way correlations,
we need at least three classifiers, to understand 3-way, four classifiers and so
on. Good engineering will consist of developing ensembles that are not
necessarily accurate but independent in their errors. Just like other
techonlogy, the operating point will be around understood regimes where only a
few of the m-way correlation values need to be measured.

## The Notion of Error Independence for Algebraic evaluators

We can finally define what being **independent** means for a finite sample of
the decisions of an ensemble of noisy judges. It means that all the m-way error
correlations defined above are zero.
