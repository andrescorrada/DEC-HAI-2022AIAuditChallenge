# Evaluating Samples is not Learning Distributions

Probability and measure theory are two powerful technologies we use to construct
and understand the vast majority of AI algorithms and systems. With them we
construct "doctors" - algorithms and processes that encode the learning processes
and data that made them. Building good doctors is essential to creating safe and
fair AI systems. Understandably, this has lead to a lot of work done on learning
theory to guarantee AI performance SLAs (Service Level Agreements). And a lot of
recent work has gone into learning theory under out-of-distribution conditions -
you train on data created by one distribution of the task data, but the model
so trained is actually deployed in an environment best modeled with another
distribution.

If you have a hammer, everything looks like a nail. It has been our experience
talking to colleagues, and in Twitter threads, that evaluation of samples is
viewed with a probability distribution prism - it can **only** be done using
distributions. This assumption - "only intelligent evaluation" - is unstated
and actually pervades much work and discussion of the subject of AI safety.

It is understandable that this is so. The authority of noisy judges is a problem
considered by many traditions. In Ancient Greek Philosophy, we have the example
of Plato and his
[Ship of Fools Allegory](https://en.wikipedia.org/wiki/Ship_of_fools).
He is concerned that the democratic mob is going to be unable to recognize the
virtuous captain and thus lead to the eventual capsizing of the Ship of State.
Because, of course, unsaid by him and many that hold this same
assumption - only intelligent evaluation is possible. The core theorem of this
submission shows that this cannot be strictly true. Dumb evaluation is possible.

Our central thesis is that if Plato right, the path to safer, more auditable AI
is going to be based on building smarter and smarter systems. Not only is this a
successively harder task, but one that increases the possibility of creating
malicious AI agents in return for safety. If Plato is not right, if dumb
evaluators like the one we are presenting here are possible, we can circumvent
this intelligent turtles all the way up problem.

The combination of intelligent machines with dumb sensors is common in safety
engineering. Why is this not so for AI safety and auditing? Why must we only
have intelligent auditors? Can we not also have sensors and thermometers that
tell us when the AI systems are malfunctioning?

## The Differences Between Evaluating Finite Samples and Learning Distributions

Developing more algebraic evaluators increases our ability to monitor AI Systems
with different approaches. These are some of the advantages algebraic evaluators
have over distribution dependent ones:

1. **Finite known space versus an unknown one** Evaluation is a simpler task
than learning. One way that it is simpler is that all the necessary parameters
are known beforehand. They exist in a finite dimensional evaluation space. As
solutions are developed that can handle more complicated cases in that finite
space, they will be applicable in all future circumstances. The complete solutions
of the core theorem illustrates that. The evaluation is solved exactly in that
case. No future estimation of its output will ever be needed in the future.
2. **Algebraic evaluators alarm on their own failures** There is no universal
evaluator. Nor perfect ones. They all will fail. Algebraic evaluators are
inherently superior to ones based on distributions in this respect. They can
return complex or non-sensical real numbers. These are immediate alerts that
the evaluation has failed. This "in the box" behavior has barely started to be
used with notions like "certifiably correct" in robotics.
3. **Fast computation of estimates** Computing algebraic formulas is much
faster than carrying out computations with the EM or Monte Carlo methods.
The input into the algebraic evaluator is already data compressive. Whether
we are considering 1 million or 1 thousand decisions, evaluation with n
binary classifiers will always take $2^n$ integers. Ensembles of four or five
classifiers will be more than sufficient in many evaluation tasks. In that
case, we are talking about at most 32 integers!
4. **Universal results** The core theorem applies to any ensemble of binary
classifiers that are error independent on the sample. That is a very sparse
set of assumptions. The type of algorithms do not matter. There is no mention
of sample sizes, etc. Similarly, the $n+1$ surface containing the ground truth
values of any ensemble is also universal. It does not matter in what context
we compute this surface. The theorem's guarantee of including the ground truth
values is universal.
