# Lab Report on Research Artifact

* Date of examination: 18.12.2021
* Start time: 08:30
* End time: 11:30
* * * 

## Metadata

* Paper DOI (necessary): 10.1145/3409001
* Artifact DOI (optional): 10.1145/3410235
* Badges achieved in regular artifact evaluation: Artifacts Available, Artifacts Evaluated-Functional  
* Time (in minutes) needed to read the paper: 40 min

## Availability

* [ ] Artifact is archived in a public archive with a long-term retention policy
* [x] Artifact is available on a different website (https://coq.inria.fr/)
* [x] Artifact is available in the version that was submitted to artifact evaluation
* [x] Artifact is available in the version that passed artifact evaluation
* [x] Artifact is available in a public version control system(GitHub)
* [x] Artifact is available in a self-contained form (container, VM)
* Time (in minutes) needed for the check: 10 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions. The following are just examples! You can skip any of them or add any additional ones that make sense for the links we provided you. -->
* Artifact can be downloaded directly in the version that was submitted to artifact evaluation.


### Observations

<!-- Note all observations (negative, neutral, or positive) made -->
#### Positive
* Artifact can also be downloaded through the homepage of COQ and its repository in GitHub and the different versions are available.
* In addition, a version that runs directly with the browser and a image that runs through a remote virtual machine are provided.
* And the artifact also provides different access methods and installation solutions for different operating systems (Windows, Linux, MacOS).

## Artifact Type

<!-- Please indicate the artifact type. Multiple selection possible. -->

* [ ] Code
* [ ] Dataset
* [x] Automated proof
* [ ] Manual proof
* [ ] Other (please specify)
* Time (in minutes) needed for the check: 5 min

### Checks performed
<!-- Note all checks you performed here to answer the above questions -->
*  Coq is an interactive theorem prover. This definition is mentioned in the homepage of the artifact and the README file.

### Observations

## Functional

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [x] Artifact is considered functional
* [ ] Artifact is NOT considered functional
* [ ] Artifact is considered partially functional 

* Time (in minutes) needed for the check: 60 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions -->
* [x] Documented -- There is a complete README file to introduce the set-up process, includes two ways, ***Manually compiled coq development** and **qemu image** based on remote VM. And explained the file structure of the compiled files.
* [x] Consistent-- The artifact is the main supporting tool of the paper.
* [x] Complete:-- The artifact contains all the detailed instructions, including the operating system and possible problems caused by the remote virtual machine connection, and Debugg instructions.
* [x] Exercisable-- According to the operation of the tutorial, the file structure described in the README file can be generated, where ```InterpExamples.v``` is Some examples of interpretations of λ-terms. And the compiled ```InterpExamples.vo``` file is successfully generated.

### Observations
<!-- Note all observations (negative, neutral, or positive) made -->
* Since I don't have a MacOS device, in addition to the manually compiled version and the remote image version directly included in the evaluation artifacts, I also tested the installation and compilation of coq under the Windows system. According to the guidelines, it can be successfully compiled under Windows.

## Reusable

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [x] Artifact is considered reusable
* [ ] Artifact is NOT considered reusable
* [ ] Artifact is considered partially reusable
* Time (in minutes) needed for the check: 30 min

### Checks performed

* Read the documentation of the artifact
* Steps to verify its functionality

<!-- Note all checks you performed here to answer the above questions -->

### Observations

<!-- Note all observations (negative, neutral, or positive) made -->
* For the usage of Coq, sufficient knowledge of computer semantics is required, because the input file of Coq needs to have a specific language specification. But according to the description of the reference manual on the website, coq can compile ```.v files``` through three commands: ```coqtop```, ```coqc```, ```coqchk```. And it is mentioned in manual, "**The compilation using coqc -vok foo.v checks that the file foo.v correctly compiles, including all its opaque proofs. If the compilation succeeds, then the output is a file called foo.vok, with empty contents. This file is only a placeholder indicating that foo.v has been successfully compiled. (This placeholder is useful for build systems such as make.)**"
* Since I don't have any knowledge of semantics, I cannot manually build a compilable file to verify the use of Coq. I can only judge the usability of coq through the compilation result of the ```InterpExamples.v``` file. It turns out that the ```InterpExamples.vo``` file and two empty files ```InterpExamples.vok``` and ```InterpExamples.vos``` were successfully produced.

## Result reproducibility with the artifact

<!-- Please start with results that the artifact documentation claims to be reproducible. If no such claims can be found, please note this in the observations. After that, please check which results/conclusion are supported by the artifact and which ones are not (irrespective of the results in the paper actually match your observations with the artifact). In the last step, please check which of the supported results/conclusions match. -->

* [ ] Results from the paper are fully supported by the artifact (i.e., it should in theory be possible to reproduce all results from the paper)
* [ ] Results from the paper are partially supported by the artifact
* [ ] Results from the paper are not supported by the artifact
* [ ] Results that are supported by the artifact could be fully reproduced
* [ ] Results that are supported by the artifact could be partially reproduced
* [ ] Results from the paper could not be reproduced
* [x] Results from the paper could not be judged
* Time (in minutes) needed for the check: 5 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions -->

### Observations
Since the conclusion of the paper is to illustrate the utility of Coq in the fields of semantics and theorem proving, I cannot evaluate its effect because I don't have any relevant knowledge. And the output form of Coq can only be related to whether it can run, there is no specific quantitative index to measure the function of Coq. Therefore, after confirming the usability of Coq, there are no definite conclusions about the results in the paper.

<!-- Note all observations (negative, neutral, or positive) made -->
<!-- In case of partial result reproduction, please state what did and did not work -->






