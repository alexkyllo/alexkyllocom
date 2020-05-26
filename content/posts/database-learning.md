---
title: "Database Learning Resources"
date: 2020-05-09T11:04:29-07:00
draft: false
---

Over the last few years working in analytics and data science, I've developed a
strong interest in the internal workings of database engines, particularly
distributed database for analytical workloads. Here I'm going to build a list of
computer science concepts and learning resources that I am finding helpful in
building understanding of how these systems work and how to implement them.

# File I/O Concepts

- [On Disk I/O](https://medium.com/databasss/on-disk-io-part-1-flavours-of-io-8e1ace1de017)
a series of blog posts by Alex Petrov, explaining the different methods of
file I/O in Linux (buffered, direct, memory-mapped, asynchronous, vectored)
and their use cases in the context of database applications, as well as on-disk
data structures (SSTables, B+ Trees, Log-Structured Merge Trees)

## Probabilistic Data Structures

- [Bloom Filter](https://www.jasondavies.com/bloomfilter/) A hash bitmap for
probabilistic answers to set membership queries (true/false with no false negatives)
- [HyperLogLog](http://algo.inria.fr/flajolet/Publications/FlFuGaMe07.pdf) A hash based
algorithm for fast approximate cardinality (distinct count) estimation
- [Count Min Sketch](https://redislabs.com/blog/count-min-sketch-the-art-and-science-of-estimating-stuff/)
an approximate frequency table similar to a counting Bloom filter

# On-Disk Data Structures

- [LSM Tree Paper](http://paperhub.s3.amazonaws.com/18e91eb4db2114a06ea614f0384f2784.pdf)
Log Structured Merge Trees--trees of immutable sorted runs of on-disk data that are periodically
merged using external merge sort
- [Google BigTable Paper](https://static.googleusercontent.com/media/research.google.com/en//archive/bigtable-osdi06.pdf) Application of LSM Trees

# Distributed Consensus Algorithms

- [The Raft Consensus Algorithm](https://raft.github.io/)
- [Implementing Raft by Eli Bendersky](https://eli.thegreenplace.net/2020/implementing-raft-part-0-introduction/)

# Comprehensive Database Concept Books

- [Database System Concepts](https://www.db-book.com/db7/index.html)
- [Database Internals](https://learning.oreilly.com/library/view/database-internals/9781492040330/)
- [Designing Data Intensive Applications](https://learning.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/)

# Open Courses

- [CMU 15-445 Database Systems](https://15445.courses.cs.cmu.edu/fall2019/)
covers basics of on-disk database system implementation
- [CMU 15-721 Advanced Database Systems](https://15721.courses.cs.cmu.edu/spring2020/)
covers advanced topics in in-memory database implementation, with emphasis on concurrency
control and optimizations.
