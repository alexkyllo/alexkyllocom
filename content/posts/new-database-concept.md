---
title: "Thoughts on a New Analysis Database Concept"
date: 2020-04-12T17:27:47-07:00
draft: true
---


Data scientists & analysts have to work with a wide variety of
technologies that support the business process
of collecting, storing, accessing, and analyzing data.
The typical business data analysis workflow currently faces several serious,
systematic challenges that can be addressed by improvements
to the design of data collection and analysis systems.

One of these challenges is that sharing datasets for analysis is still
overly difficult. The typical mechanism for sharing data internally within a
company is to grant analysts direct access to a SQL database server.
Because these databases couple storage and computation resources,
this results in resource contention issues and
suffers from poor scalability in the number of users that can be served and
the quantity of data that can be served to them.
Shared database servers are overutilized by expensive and unpredictable
ad-hoc queries and recurring jobs that import and export large batches,
and they suffer poor performance as a result. The tight coupling of the data
access language to the physical storage schema of the database also makes
it difficult to evolve the system without breaking systems that depend on it.
Analytical use cases involve combining data generated
by separate systems, which often requires movement
of batches of data across servers.
Most databases products lack awareness of these extract-transform-load (ETL)
processes, so a whole suite of job scheduling and
monitoring tools must be deployed to manage the ETL. This
introduces a graph of dependencies among datasets, where an outage or change
in an upstream data system can cause cascading failures downstream.
The maintenance burden of an analytical database makes many engineering teams
reluctant to share their data internally, and the quantity and quality of
data available for analysis within the enterprise suffers as a result.

Data lake systems based on distributed storage such as Hadoop can alleviate
part of the problem by separating compute nodes from storage nodes and
enabling horizontal scaling via use of the MapReduce pattern.
These systems can be more expensive to deploy and manage.
They are oriented toward periodic batch processing workloads and their
latency characteristics make them mostly unsuitable for the kind of ad-hoc,
interactive data exploration that analysts often need to conduct.
They also introduce many new domain-specific languages that require
time investment to learn. These systems
are maturing and growing in popularity, however, and may soon replace
relational databases as the centerpiece of data analysis systems architecture
in most enterprises.

A separate challenge is the wide disparity in the semantics of query languages
that execute within a database, and programming languages used to analyze
data once extracted from the database.
The analyst must first make a time investment in writing a
SQL query to project, filter, and aggregate a subset of data, executing the
query, and downloading the result set to a file. Then, they may write an
analysis script in another programming language to read the file into memory
and perform further processing. When project requirements change, the analyst
may need to rework the query, rerun the extraction process, and alter the
analysis script. Without discipline and tool support, the reproducibility of
the analysis and validity of its results are jeopardized.
There is opportunity for technologies that shift or blur the boundary between
query and programming languages, to ease this transition and enable
a more iterative approach to querying and analyzing data.

Another issue that burdens data analysis is the scarcity of
metadata and documentation for datasets.
The data formats that are commonly found in databases
and data lakes are useful for analysis because their tabular structure
facilitates relational algebra and linear algebra operations. But these
formats lack semantic metadata
describing the meaning and provenance of the data. There are
knowledge management systems on the market that address the
need for searchable catalogues of shared dataset documentation and
lineage traceability, but a lack of
accepted open standards for the format of such metadata.
Data cataloguing systems are also flawed when they focus on post hoc
reconstruction of knowledge about a shared dataset,
rather than enabling the encoding of that knowledge
at the time the dataset is designed, by the developer who understands it
and its surrounding context.

Data governance and knowledge management systems are also facing a major test
driven by consumer and regulatory responses to social media and advertising
technologies.
The proliferation of analysis databases and files throughout the enterprise
is a risk factor in security, privacy, and ethics compliance areas
and the need to audit and service these datasets calls
for centralized governance. Several major cybersecurity breaches in recent
history have come from analysis datasets left on unsecured network storage.
Consumer data privacy regulations such as the EU GDPR have established
strict rules around the retention and usage of personally identifiable
information about users, and industry is struggling to develop and deploy
systems capable of ensuring compliance. Effectively servicing audits and
protecting data subject rights requires structured documentation and metadata
on the subject, nature, and provenance of all data shared within
the organization.

With the recent growth in industry interest in machine learning and artificial
intelligence applications, bias in models has become another important
ethical issue. Models intended to categorize people and predict social outcomes
can inadvertently reinforce those outcomes, and the naive approach
of excluding known
sensitive variables such as race or gender, is unsuccessful because models can
learn latent variables from other correlated inputs. To address this requires
education and technology support for bias-aware modeling approaches.

The industry-wide challenges posed by these rapidly evolving
requirements present significant new opportunities for research and
development of data analysis systems with features that support the efficient,
reliable, and ethical collection, sharing, and modeling of data
at enterprise scale.


