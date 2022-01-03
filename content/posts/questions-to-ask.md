---
title: "Questions to ask to keep your data science projects on track"
date: 2022-01-02T22:16:24-08:00
draft: false
---

Data science projects fail a lot. It's highly speculative work, so as a data
scientist, some crucial career skills are knowing how to assess the viability of
a project, when to cut your losses, and why things didn't work out, so that you
can learn from it and adjust your approach. I've put together a list of
questions to ask at each stage in a project's lifecycle, to help you avoid
wasting your precious time on projects that are not going to make it.

I'm assuming the general sort of projects that I have experience with: small
business data science projects (think one to a few people over one to a few
months), which we can roughly break down into a generic five-phase lifecycle:

1. Scoping
2. Analysis
3. Development
4. Validation
5. Release

This is not a prescriptive procedure but a rubric to help you assess progress
and viability. If you're not sure how to move your project forward or whether
it's even worth investing further time into, the answers to these questions may
help you decide the best next steps.

## Scoping

Have discussions with the proposed project's customers and write a one-pager
that answers the following questions:

- What is the business decision or problem motivating the project?
- Which type of deliverable (presentation, static report, dashboard etc.) is
  most appropriate?
- Who will use the deliverables?
- How will they use the deliverables to achieve business impact?
- Have the necessary data been collected, or can they be collected in time to
  analyze them and act upon the analysis?
- When the project is done, how and when will we know whether it was successful?
- Who will agree to review my work for quality?
- Where and when will I present or distribute my work to its intended users?

Review this document with a peer or your manager first if possible, and then
with the customer, to align their expectations. Revise it as needed to achieve
agreement, but don't force it if the case isn't compelling or you can't get
clarity.

Many, if not most, data science project ideas should be terminated at this stage
for reasons such as there isn't a clear problem-solution fit, there is no
decisionmaker who can act upon the findings, or the desired data doesn't exist
and can't be collected in time.

Beware of project ideas that constitute a post-hoc analysis to justify a
decision that's already been made or a program that's already launched. These
sorts of projects are not actionable, tend to get political, and are subject to
[outcome
bias](https://towardsdatascience.com/focus-on-decisions-not-outcomes-bf6e99cf5e4f),
where a decision is evaluated using information that was unknowable to the
decisionmaker at the time.

Also beware of the "solution in search of a problem," where you pick the kind of
model you want to develop first and then try to find data, use cases and users
for it. This mode of work is common in data science teams and it doesn't work
well when your goal is to influence business decisions rather than to conduct
research.

## Analysis

This is the exploratory data analysis (EDA) phase. Locate and study the data
sources and determine their provenance. Start writing queries to profile and
extract the data. Start an R or Python script for plotting the data
distributions. Don't spend a lot of time on writing clean, maintainable code at
this point, it's likely to be throwaway work. Your goal here is to get familiar
with the data and identify its problems and limitations.

### Data provenance questions

- Where are the necessary data for this project located?
- How was the data collected? What, if any, sampling method was used?
- Who owns the data sources, what level of support do they offer, and
  how will we contact each other if there is a problem?
- How often will we need to refresh the data from the source, and is the source
  updated at least that often?

### Data profiling questions

- What is the user/customer ID grain?
- What is the time grain?
- What are the variables, their data types and business meanings?
- What should be the dependent variable? Is it present in the data? How is it
  distributed?
- What is the distribution of each ordinal and nominal categorical variable?
- What are the distributions and moments of each integer or real variable?
- What are the pairwise joint distributions and correlations among the variables?
- Which variables have missing data and what are the reasons for missingness?
  Missing data in business are usually missing not at random (MNAR), so what is
  the pattern?
- Can I tell if there are missing observations? Are they missing for certain
  classes or on certain dates?
- Do any variables have extreme outliers? Can I find out how they happen?
- Are the observations
  [IID](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables)?

Reasons to cancel a project at this phase would be discovering that the data are
inaccessible, unreliable, no longer maintained or supported, or are of
insufficient quantity, quality or completeness to produce a deliverable data
product that meets the goals of the project. If you're working on an otherwise
promising project and find a dealbreaker in the data, it behooves you to give
specific, actionable feedback to the customer and data owner so that they have
an opportunity to correct the problem for future work.

## Development

The development stage of the project is where you build your deliverable data
product--you write code, develop models, craft visualizations, and document your
findings. Unlike the EDA phase where your code can be throwaway scripts or
notebooks, here you'll want to start introducing some structure (and comments,
and documentation) to your project because it will allow you to change and
re-run steps without manual rework, and will also help your peers who need to
understand and review your work.

### Modeling tasks

For many of us, building a predictive or causal model is the fun part of data
science. But before jumping into modeling, ask yourself a few questions to
determine if it's really worth building a model at all:

- Is the model attempting to automate a human decision? How often does that
  human decision need to be made, how much labor does it require, and what is
  the human error rate?
- What is a simple heuristic baseline model for the task and how well does it
  perform?
- Does the improved performance of a more complex model justify the increase in
  complexity and resource-intensiveness and decrease in interpretability?
- How will the model outputs be consumed by a system, business process, or human
  decisionmaker?
- What is the cost of a false positive (or overestimation) relative to a false
  negative (or underestimation)?
- If the data is wholly or partially labeled, where do the labels come from? Can
  I detect any label noise?
- Could a model predict the label before the point in time when it is needed in
  the business process?
- What is the appropriate unit for random sampling or assignment?
- What validation or model selection strategy is appropriate?
- What biases and confounders could exist in the data and how will I control for
  them? (This is the paramount question for a causal model, but even for
  purely predictive models, biases can cause serious problems!)
- How will I assess model residuals to understand how the model fails, and
  compare these to the errors produced by the existing business process?
- Is there potential for unfair or disparate impact on human subjects? How can I
  address this?

The field of machine learning is littered with failed projects where a
predictive model sounded like a good idea, but the turned out not to be an
improvement over the existing process. For a timely example, see _Nature_'s
[meta-analysis of COVID-19 detection and prognostication
models](https://www.nature.com/articles/s42256-021-00307-0) that found none of
the 62 studies reviewed produced anything usable in practice.

### Visualization tasks

It's easy to create clutter and confuse your audience when presenting data in
plots. For each data visualization that will be included in a deck, report or
dashboard, consider whether and why the plot is necessary:

- Is the visual intended to:
  - show change in a metric or progress toward a goal over time
  - compare multiple groups by a metric
  - characterize the distribution of a metric within a group
  - compare distributions of a metric across two or more groups
  - depict a relationship between two or more variables
  - call attention to outliers
  - show the performance of a model
- Does the visual require interactivity? _Does it, though?_
- How often should the viewer look at the visual? (Once? Weekly? Monthly?)
- Would the plot be better as a table?

### Metrics tasks

For some data science projects, the primary deliverable is a metric, typically
visualized on some dashboard that's refreshed every hour, day, week or month. If
you are designing and implementing a new metric, consider:

- How does the metric relate to customer success or other business objectives?
- Is higher better or worse?
- Is there a goal or target?
- How is it flawed as a proxy of what you really want to measure?
- Is it being used to measure the performance of a person or team?
- How might it be "gamed" or introduce a perverse incentive or feedback loop?

You get what you measure (and reward), for better or for worse. A badly designed
metric can do much more damage than not measuring at all, so [Goodhart's
law](https://en.wikipedia.org/wiki/Goodhart%27s_law) and its many corollaries
should be in the front of your mind when designing metrics, especially those
that attempt to quantify the achievements of human workers, because the act of
measuring will cause their behavior to change in unintended ways.

### Presentation

For each slide or report section, ask yourself critical questions about why it
belongs and what purpose it serves. Your audience is giving you their precious
time and attention, so maximize the value they get in return.

- What is my finding? (Lead with the punchline)
- What is the evidence and how does it support the finding?
- What are the limitations of the evidence? What untestable assumptions did I
  have to make? (Savvy audiences will ask!)
- What is the business implication of the finding?
- What am I asking the viewer to do with this information?
- What are the obvious questions that a viewer would ask when they see this?

## Validation

Validation is a chance to check if you made the right thing and made the thing
right. Seek input from peers to determine if the deliverables need any quality
improvements, and from stakeholders as appropriate to determine if the
deliverables (still) meet the business need identified at the start of the
project. Do this throughout the project, particularly if it's on the larger side
or if you're working on something that makes sense to develop iteratively, but
you should always have some sort of quality gate before you "ship."

- Does the original business problem or need for the project deliverable still
  exist? What changed in the meantime?
- Are my code files source-controlled and my datasets backed up?
- Can I reproduce the deliverable from the raw data in one step? Do the
  quantitative results turn out the same after I re-run the entire process?
- Has a peer read over my queries, code and report to check them for errors?
- Have I shown a draft or pre-release version to a customer to validate
  that the deliverable meets their needs?

## Release

The release stage is where you deliver the presentation, publish the
paper, or deploy the model or dashboard to production.

For a production model or dashboard, someone will need to support it, so before
you deploy it, ask questions like:

- What are the ongoing maintenance responsibilities?
- What computing resources are required to operate in production?
- What monitoring and alerts are required?
- How will I track user adoption and engagement?

For a report or presentation:

- Did I successfully deliver my work to its intended consumer?
- If so, what were the decisions and follow-up actions?
- Did the stakeholder commit to taking any recommended action based on my work?
  Why or why not?

Finally, it's a good idea to have a project retrospective discussion or written
report that summarizes, without blaming any individuals or teams, what went
right, what went wrong, and what lessons were learned that could be applied to
future work.

While I've attempted to make this guide sufficiently general to apply to a broad
swath of business data science projects, every project is a little different, so
ask the critical questions that make the most sense for your project. So long as
you start small, fail fast, and insist on actionable results, you should see an
improved return on your time investment in your projects.
