# Time-Constrained Regular Path Query on Streaming Graph

Time-constrained regular path queries (TC-RPQs) enrich streaming RPQs with explicit temporal constraints over the timestamps of edges on a match, including constraints that relate distinct occurrences of the same label across Kleene-star iterations. Existing streaming RPQ methods either cannot express such fine-grained temporal semantics or fall back to post-checking, which is costly under high update rates. We formalize TC-RPQs and compile each query into a constraint-injected DFA (CI-DFA) that integrates timestamp recording and constraint validation into automaton transitions via external registers. Guided by the CI-DFA, we develop an incremental evaluation framework that maintains only time-consistent partial matches in a Match-Store Digraph (MS-Digraph), enabling early pruning as the stream evolves. We further propose a containment-based compression that prunes dominated nodes without losing answers. Experiments on StackOverflow and YAGO3 streams demonstrate substantial throughput gains over post-checking baselines, while compression typically yields additional speedups and reduces maintained state size.

# License
This archive is free for use for academic and non-profit purposes, but if you use it, please reference it properly.

# Disclaimer
The code is provided without warranty of any kind. While we thoroughly tested all code bases on Ubuntu 20.04 LTS (Windows Subsystem of Linux), we do not guarantee that they are exempt from bugs, nor that they will work on other platforms. If you encounter any issues with the code, please feel free to propose them on the ISSUE page of this repo. We will do our best to address your concerns but do not promise to resolve all issues.

# Installation

## Prerequisite

All requirements for libraries are included in the pom.xml file. After importing the project, please first follow all required dependencies.

## Build & Run

This is a Java project. The Java version we used for testing is 8, however, we subjectively believe that it can run on relatively lower versions.

*If you have access to an IDE like IntelliJ IDEA*, just open the project and work with it and build it automatically, then run <font color=red>QueryOnLocal.java</font> in package “runtime”.

Note that we conducted experiments on the server by packaging the code into a jar package. The dependencies and information required to package the jar package are included in the pom.xml file.

*Other*, please see instructions below.

## Hints

1. All configurations are written in pom.xml. The information of the dataset has been given in the paper.
To complete your task, please read through and install all dependency files.

2. The project structure mainly contains 5 modules. The input package mainly handles file reading operations; the runtime package is the entry point for code running, which temporarily only contains a QueryOnLocal.java file; under the stree package, the data package contains the implementation of TRD ; The engine package handles the expansion and maintenance of TRD; the query package contains the implementation of DFA and NFA (which we will expand in the future); the util package contains various tool classes, including constants for environment parameter configuration, and classes for monitoring data.

3. For the parameters passed in when the code is running, please refer to the instructions in the <font color=red>runtime/QueryOnLocal.java</font> file.

4. For configuration during project running, please view <font color=red>stree/util/Constants.java</font>

## Datasets

The data sets (SO and Yago3) we used in the paper are free and open source for download.

Please see https://stackexchange.com/ and https://yago-knowledge.org/ to learn how to download and use them.

## Issue

If you have any problem, feel free to write your questions in ISSUE.
