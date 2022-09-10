# Evaluating Samples is not Learning Distributions

Probability and measure theory are two powerful technologies we use to construct
and understand the vast majority of AI algorithms and systems. With them we
construct "doctors" - algorithms and processes that encode the learning processes
and data that made them. Building good doctors is essential to creating safe and
fair AI systems. Understandably, this has lead to a lot of work done on learning
theory to guarantee AI performance SLAs (Service Level Agreements). And a lot of
recent work has gone into learning theory under out-of-distribution conditions --
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
of Plato and his [Ship of Fools Allegory](https://en.wikipedia.org/wiki/Ship_of_fools).
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
