# Reproducibility of Scientific Results in Software Engineering Research
This repository is used to save the 5 lab reports for the master seminar "Reproducibility of Scientific Results in Software Engineering Research" of WS2021 in LMU. 
\
The goal of this seminar is to learn how to use and assess artifacts from software engineering and programming language research.
\
The main tasks are performing a reproduction study on a given set of already published artifacts.
- verify that published research artifacts are still available and usable,
- read the related publications,
- follow the documentation of the artifacts to reproduce the studies’ results, and
- report the findings.
## Assigned papers and artifacts 
The following are the papers that were experimented on. Detailed lab reports are located in each subfolder and are named by their DOI numbers.
* Nachshon Cohen, Michal Friedman, and James R. Larus. 2017. **Efficient logging in non-volatile memory by exploiting coherency protocols.** <i>Proc. ACM Program. Lang.</i> 1, OOPSLA, Article 67 (October 2017), 24 pages. DOI:https://doi.org/10.1145/3133891
* Abdulbaki Aydin, William Eiers, Lucas Bang, Tegan Brennan, Miroslav Gavrilov, Tevfik Bultan, and Fang Yu. 2018. **Parameterized model counting for string and numeric constraints.** In <i>Proceedings of the 2018 26th ACM Joint Meeting on European Software Engineering Conference and Symposium on the Foundations of Software Engineering</i> (<i>ESEC/FSE 2018</i>). Association for Computing Machinery, New York, NY, USA, 400–410. DOI:https://doi.org/10.1145/3236024.3236064
* Manuel Benz, Erik Krogh Kristensen, Linghui Luo, Nataniel P. Borges, Eric Bodden, and Andreas Zeller. 2020. **Heaps'n leaks: how heap snapshots improve Android taint analysis.** In <i>Proceedings of the ACM/IEEE 42nd International Conference on Software Engineering</i> (<i>ICSE '20</i>). Association for Computing Machinery, New York, NY, USA, 1061–1072. DOI:https://doi.org/10.1145/3377811.3380438
* Benoît Montagu and Thomas Jensen. 2020. **Stable relations and abstract interpretation of higher-order programs.** <i>Proc. ACM Program. Lang.</i> 4, ICFP, Article 119 (August 2020), 30 pages. DOI:https://doi.org/10.1145/3409001
* Danel Ahman, Cédric Fournet, Cătălin Hriţcu, Kenji Maillard, Aseem Rastogi, and Nikhil Swamy. 2017. **Recalling a witness: foundations and applications of monotonic state.** Proc. ACM Program. Lang. 2, POPL, Article 65 (January 2018), 30 pages. DOI:https://doi.org/10.1145/3158153

## Expectations
Before I started, my idea was to get a general idea of the different fileds of knowledge through the reproducibility of the artifacts or experiments. After all, these papers cover knowledge from different domains, such as hardware, algorithms, semantics, etc. And since, unlike academic papers from other disciplines, the SE domain is often based on some actual algorithm or software. This also makes its reproducibility much different. I hope to learn how to write a "real" SE paper based on artifacts.

## Differences across the assigned artifacts and Impact
At least in terms of the papers to which I was assigned, the artifacts in them I would broadly classify into two categories: experimental artifacts, and theoretical artifacts.
### Experimental artifacts
One very distinctive feature of these artifacts is that the entire experimental process is considered to be part of the artifact, and the paper involves, for example, an algorithm or software that serves as "tool support" for the artifact.  This type of artifact is the easiest to reproduce if accompanied by detailed guidance documentations, because it is based on a "step-by-step" process and has quantifiable or even visualized results, which makes it very easy to verify and use, and with calls to algorithms or source code integrated in some operational scripts.
### Theoretical artifacts
Theoretical artifacts are hard to reproduce the experiment. This is because most of their papers spend a lot of space on the relevant theoretical foundations. Their purpose is to illustrate the efficiency of a certain algorithm, library, or tool. However, such artifacts often do not have quantifiable metrics to illustrate their efficiency, or their efficiency needs some prior knowledge, such as semantics, to be judged. These artifacts basically do not contain data sets or input files for input. My guess is that as a "general-purpose" algorithm or tool, it would be inappropriate to use a specific input set to verify its validity. But this also makes it more difficult or impossible to perform reproducible experiments.

## Conclusions
* Even if you can successfully complete the experiment, the probability is that you will not be able to learn the relevant field of knowledge from it, because the level of these papers is not "novice tutorial level". Even for experimental artifacts, a large amount of prior knowledge is required to fully understand the knowledge and principles involved. Many papers on semantics contain much more theoretical knowledge.
* Reproducible experiments often do not require you to fully understand the content of the paper, but rather a general reading of the paper to figure out the purpose of the paper and the use of artifacts.
* Guidance documentation is extremely important for artifacts. This is because authors should not assume that the reviewer or reapplicator of the paper must have sufficient prior knowledge. From the experiments I have done, the lack of guidance documentation can lead to extremely slow progress because I cannot immediately understand the entire flow of the experiment.

## The Lessons
* Previously I thought artifact-based papers should spend a lot of time describing the details of their implementation. But this is not the case. Because this type of paper is not a "lab report", it needs more space to fill in the theoretical underpinnings and to verify success. More effort is spent on the so-called "relevant" parts.
* As I mentioned in the previous section, the importance of the guidance documentation. The guidance documentation should be seen as an interface to the artifact. And it is important to note that guidance documentations, such as README files, should have a uniform format specification. It is also important to include a directory structure and description of the artifacts in the guidance documentation, as the file structure will be useful for troubleshooting errors as they occur during the experiment.
* Sometimes artifacts fail not because of a problem with the artifact itself, but because of a significant change in the software or library on which they depend. From the point of view of verifying its reproducibility, we need to find the environment it needs to run in. But in terms of reusability, this is a great disadvantage for the artifact in a new development environment. This may require the authors to adapt the artifacts for the new development environment.
