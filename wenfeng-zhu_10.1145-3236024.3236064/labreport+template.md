# Lab Report on Research Artifact

* Date of examination: 08.12.2021
* Start time: 15:30
* End time: 17:30
* * * 
* Date of examination: 09.12.2021
* Start time: 19:00
* End time: 20:00
* * *
* Date of examination: 16.12.2021
* Start time: 17:00
* End time: 18:00

## Metadata

* Paper DOI (necessary): 10.1145/3236024.3236064
* Artifact DOI (optional):
* Badges achieved in regular artifact evaluation: Artifacts Available, Artifacts Evaluated–Functional  
* Time (in minutes) needed to read the paper: 40 min

## Availability

* [x] Artifact is archived in a public archive with a long-term retention policy (Zenodo)
* [ ] Artifact is available on a different website (which one(s)?)
* [x] Artifact is available in the version that was submitted to artifact evaluation
* [x] Artifact is available in the version that passed artifact evaluation
* [ ] Artifact is available in a public version control system
* [ ] Artifact is available in a self-contained form (container, VM)
* Time (in minutes) needed for the check: 10 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions. The following are just examples! You can skip any of them or add any additional ones that make sense for the links we provided you. -->
1. Artifact is directly accessible from Zenodo link.

### Observations

<!-- Note all observations (negative, neutral, or positive) made -->


## Artifact Type

<!-- Please indicate the artifact type. Multiple selection possible. -->

* [x] Code
* [ ] Dataset
* [ ] Automated proof
* [ ] Manual proof
* [ ] Other (please specify)
* Time (in minutes) needed for the check: 20 min

### Checks performed
MT-ABC is built as an extension of the tool ABC (Automata-Based Model Counter) and uses much of the same underlying source code.
On its basis, a new extended library glog is introduced.
<!-- Note all checks you performed here to answer the above questions -->

### Observations
#### Positive
* It contains a Easy(Automated) Setup, automatically execute the set-up operation by executing the ```install-build-deps.py``` file in the ```build``` folder. And comes with Step-by-Step (Semi-automated) Setup as an alternative.
#### Negative
* Since the current version of glog no longer uses the ```configure.ac``` file to perform compilation and installation, Easy (Automated) Setup is no longer applicable in the current environment.

## Functional

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [x] Artifact is considered functional
* [ ] Artifact is NOT considered functional
* [ ] Artifact is considered partially functional 

* Time (in minutes) needed for the check: 40 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions -->
* [x] Documented -- There is a complete README file to introduce the set-up process, dependency libraries and usage of the artifact.
* [x] Consistent-- Artifacts are served as the main supporting tool of the paper.
* [x] Complete:-- The artifact contains the description of all the dependent libraries required for the installation and specifies the file status after the installation is successful.
* [x] Exercisable-- After the artifact was installed, it is called as a library, and the smt2 file is analyzed in the form of executing commands.

### Observations
<!-- Note all observations (negative, neutral, or positive) made -->
#### Negative
* The use of artifacts seems to presuppose the user's knowledge of the domain of model counting. The output result of using the library is not explained, that is, which part of the output result can be used as a judgment to measure the performance of the MTABC library.

## Reusable

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [ ] Artifact is considered reusable
* [ ] Artifact is NOT considered reusable
* [x] Artifact is considered partially reusable
* Time (in minutes) needed for the check: 30 min

### Checks performed

* Read the documentation of the artifact
* Steps to verify its functionality

<!-- Note all checks you performed here to answer the above questions -->

### Observations

<!-- Note all observations (negative, neutral, or positive) made -->
* As mentioned in README file "**Latest MTABC compilation is tested with g++ 5.4.0 on Ubuntu 16.04**". MTABC is installed and run successfully under ubuntu 16.04 and g++ 5.4 version.
* Then try to install and run again under ubuntu20.04 and gcc 9.3, throwing the following error:
```
error: patch failed: src/demangle.h:71
error: src/demangle.h: patch does not apply
```
* After comparing the version of the dependency libraries that MTABC needs to install: **build-essential, autoconf, automake, libtool, intltool gcc** in both environments. The version of gcc was the only different.

## Result reproducibility with the artifact

<!-- Please start with results that the artifact documentation claims to be reproducible. If no such claims can be found, please note this in the observations. After that, please check which results/conclusion are supported by the artifact and which ones are not (irrespective of the results in the paper actually match your observations with the artifact). In the last step, please check which of the supported results/conclusions match. -->

* [ ] Results from the paper are fully supported by the artifact (i.e., it should in theory be possible to reproduce all results from the paper)
* [ ] Results from the paper are partially supported by the artifact
* [ ] Results from the paper are not supported by the artifact
* [ ] Results that are supported by the artifact could be fully reproduced
* [ ] Results that are supported by the artifact could be partially reproduced
* [x] Results from the paper could not be reproduced
* Time (in minutes) needed for the check: 30min

### Checks performed

<!-- Note all checks you performed here to answer the above questions -->
* The artifact only contains its own compilation and installation, and only contains the usage of the artifact, that is, the smt2 file is executed through commands, but it lacks the description of the output results and the input files to support the conclusion of the paper.

### Observations

<!-- Note all observations (negative, neutral, or positive) made -->
<!-- In case of partial result reproduction, please state what did and did not work -->
* Try to compare whether the various ```smt2``` files in the ```test``` folder in the artifact are the input files required by the paper, and finally concluded that because MT-ABC is built as an extension of the tool ABC (Automata-Based Model Counter) and uses much of the same underlying source code. The test folder contains the files used by ABC for testing, which can be executed by MTABC but has nothing to do with the input files required by the paper.
* Trying to read other solver-related papers mentioned in the paper, I still could not find relevant inputs to support the paper's conclusion.
* Finally, under the link to the artifact [ https://dl.acm.org/do/10.5281/zenodo.1420217/full/ ], I found a description of the data documentation I had missed earlier. "**While the artifact will produce the results from the paper, we did not provide the dataset with the artifact itself, as it is just the tool.**"
* The paper concludes that MTABC presents advantages in comparison with other existing solvers. However, other solvers need to be downloaded and called manually by the user. The workload of this section is beyond the scope of evaluation of this artifact and due to the lack of relevant input files. This part of the comparison can only be considered as non-executable.





