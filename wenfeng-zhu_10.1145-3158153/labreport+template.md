# Lab Report on Research Artifact

* Date of examination: 08.01.2022
* Start time: 16:00
* End time: 22:00
* * * 

## Metadata

* Paper DOI (necessary): 10.1145/3158153
* Artifact DOI (optional): 
* Badges achieved in regular artifact evaluation: Artifacts Available, Artifacts Evaluated-Functional  
* Time (in minutes) needed to read the paper: 30 min

## Availability

* [ ] Artifact is archived in a public archive with a long-term retention policy
* [x] Artifact is available on a different website (http://fstar-lang.org/papers/monotonicity/)
* [ ] Artifact is available in the version that was submitted to artifact evaluation
* [ ] Artifact is available in the version that passed artifact evaluation
* [x] Artifact is available in a public version control system(GitHub)
* [ ] Artifact is available in a self-contained form (container, VM)
* Time (in minutes) needed for the check: 10 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions. The following are just examples! You can skip any of them or add any additional ones that make sense for the links we provided you. -->
* Download artifacts via GitHub
* Download artifacts via the main page of this topic's website


### Observations

<!-- Note all observations (negative, neutral, or positive) made -->
#### Neutral
* In the version of an artifact submitted for review, its attachment contains only a readme file whose contents point to the artifact's GitHub repository, from which the artifact can be downloaded.
#### Positive
* The GitHub repository contains README file that declared the version of the artifact used for evaluation. i.e. v0.9.5.0


## Artifact Type

<!-- Please indicate the artifact type. Multiple selection possible. -->

* [x] Code
* [ ] Dataset
* [ ] Automated proof
* [ ] Manual proof
* [x] Other (Binary package)
* Time (in minutes) needed for the check: 10 min

### Checks performed
<!-- Note all checks you performed here to answer the above questions -->
* Download the artifact and verify its type

### Observations
* In paper-related version: Release V0.9.5.0, its assets contain three binary packages and source code of the artifact.
* These binary packages support three operating systems: ```Darwin```, ```Linux```, ```Windows```.
* It is worth noting that in subsequent updates, the last alpha version ```v0.9.7.0```, is the last version to include the Darwin platform, and all subsequent releases contain binary packages for only two platforms, Linux and Windows.

## Functional

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [x] Artifact is considered functional
* [ ] Artifact is NOT considered functional
* [ ] Artifact is considered partially functional 

* Time (in minutes) needed for the check: 40 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions -->
* [x] Documented -- The README file in GitHub repository where the artifacts are located contains an introduction to the F* language, installation, tutorials, and various usage methods (online editors, binary packages)
* [x] Consistent-- The artifact contains files to support the paper's conclusions.
* [x] Complete:-- The artifacts contains runnable binary packages and source code. The dependencies for different platforms are also explained.
* [x] Exercisable-- For paper-related files can be verified and results obtained.

### Observations
<!-- Note all observations (negative, neutral, or positive) made -->
* The initial README file contains only links to GitHub, easy-to-use artifacts, and files to support the paper's conclusions:

    Section 2 of the paper

        ulib/FStar.Monotonic.Heap.fsti:
        Basic heap model interface with support for monotonic references
        ulib/FStar.Monotonic.Heap.fst:
        Implementation of the basic heap model interface
        ulib/FStar.Heap.fst:
        Plain heap model where all the references have trivial preorder
        ulib/FStar.ST.fst
        Implementation of the STATE effect using the heap model
        ulib/FStar.MRef.fst
        Utility functions for monotonic references
        examples/preorders/SnapshotST.fst
        An example of temporarily escaping the preorder
        ulib/FStar.Monotonic.HyperHeap.fst
        Region-based hyperheap model with support for monotonic references
        ulib/FStar.Monotonic.HyperStack.fst
        Region-based hyperstack model with support for monotonic references
        ulib/FStar.Monotonic.RRef.fst
        Utility functions for hyperstack monotonic references

    Section 3 of the paper

        examples/preorders/MonotonicArray.fst
        The monotonic array library
        examples/preorders/Protocol.fst
        The file transfer example

    Section 4 of the paper

        examples/preorders/Ariadne.fst
        Ariadne protocol example

* The INSTALL file in GitHub is a more detailed description of the installation and use of the artifacts.   

        1. The online editor
        2. OCaml package manager (OPAM version 2.0 or later)
           $ opam pin add fstar --dev-repo
        3. Binary package
        4. Docker image
* Since the artifact is in frequent iteration, the current master branch in GitHub represents the latest version. And the authors declared that:
    
      Every week or so we release F* binaries on GitHub (for Windows and Linux). This is a way to get F* quickly running on your machine, but if the build you use is old you might be missing out on new features and bug fixes. Please do not report bugs in old releases until making sure they still exist in the master branch (see OPAM package above and Building F* from sources below).

    So I mainly tested the functionality of F* (v2021.06.06) as the latest version, as well as the version associated with the paper (v0.9.5.0). The results are that both versions installed and passed the tests well. The binary package usability tests were performed by executing the relevant programs, such as ```micro benchmarks```, with the ```make``` command.

## Reusable

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [x] Artifact is considered reusable
* [ ] Artifact is NOT considered reusable
* [ ] Artifact is considered partially reusable
* Time (in minutes) needed for the check: 60 min

### Checks performed

* Read the documentation of the artifact
* Steps to verify its functionality

<!-- Note all checks you performed here to answer the above questions -->

### Observations
<!-- Note all observations (negative, neutral, or positive) made -->
* The review version of v0.9.5.0 itself does not contain full documentation, but because it is a version of F*, its GitHub repository contains extremely detailed instructions, including platform, installation and operation instructions, and file structure. This makes the artifact very reusable.
* The binary package runs fine on different platforms (Windows, Linux) and Docker images. The latest version can be installed directly through the ``OCaml package manager`` and used normally. Since I don't have a MacOS device, I didn't test the usability under MacOS platform. But according to the INSTALL file description, "On MacOS you will additionally need to install ``coreutils`` via ``Homebrew`` or ``Macports`` for the OPAM package of F* to work "


## Result reproducibility with the artifact

<!-- Please start with results that the artifact documentation claims to be reproducible. If no such claims can be found, please note this in the observations. After that, please check which results/conclusion are supported by the artifact and which ones are not (irrespective of the results in the paper actually match your observations with the artifact). In the last step, please check which of the supported results/conclusions match. -->

* [x] Results from the paper are fully supported by the artifact (i.e., it should in theory be possible to reproduce all results from the paper)
* [ ] Results from the paper are partially supported by the artifact
* [ ] Results from the paper are not supported by the artifact
* [ ] Results that are supported by the artifact could be fully reproduced
* [ ] Results that are supported by the artifact could be partially reproduced
* [ ] Results from the paper could not be reproduced
* [ ] Results from the paper could not be judged
* Time (in minutes) needed for the check: 5 min

### Checks performed

* Use command ``make`` in the directory ``examples/preorders`` to run the artifact, in this folder results verification file supporting section 3 and 4 was contained.
* Individual files in folder ```ulib``` was verified with command ```fstar <filename>```.

<!-- Note all checks you performed here to answer the above questions -->

### Observations


<!-- Note all observations (negative, neutral, or positive) made -->
<!-- In case of partial result reproduction, please state what did and did not work -->
* The author claims that the above commands can be used to verifie the examples. The final output indicates a successful verification.
* However, it must be noted that I cannot verify and evaluate the algorithm or the code itself as I have no knowledge in the related field.
* The running result:

    **Section 2 of the paper**

    ulib/FStar.Monotonic.Heap.fsti:

        ~/fstar/ulib$ fstar.exe FStar.Monotonic.Heap.fsti 
        Verified i'face (or impl+i'face): FStar.Monotonic.Heap (1346 milliseconds)
        All verification conditions discharged successfully
        
    ulib/FStar.Monotonic.Heap.fst:
        
        ~/fstar/ulib$ fstar.exe FStar.Monotonic.Heap.fst 
        Verified module: FStar.Monotonic.Heap (5145 milliseconds)
        All verification conditions discharged successfully
    
    ulib/FStar.Heap.fst:
        
        ~/fstar/ulib$ fstar.exe FStar.Heap.fst
        Verified module: FStar.Heap (264 milliseconds)
        All verification conditions discharged successfully
    
    ulib/FStar.ST.fst:
        
        ~/fstar/ulib$ fstar.exe FStar.ST.fst 
        Verified module: FStar.ST (703 milliseconds)
        All verification conditions discharged successfully
    
    ulib/FStar.MRef.fst:
        
        ~/fstar/ulib$ fstar.exe FStar.MRef.fst 
        Verified module: FStar.MRef (411 milliseconds)
        All verification conditions discharged successfully
    
    examples/preorders/SnapshotST.fst:
        
        /home/wenfeng/fstar/bin/fstar.exe  --use_hints --verify_module SnapshotST SnapshotST.fst
        Verified module: SnapshotST (592 milliseconds)
        All verification conditions discharged successfully

    ulib/FStar.Monotonic.HyperHeap.fst:
        
        ~/fstar/ulib$ fstar.exe FStar.Monotonic.HyperHeap.fst
        Verified module: FStar.Monotonic.HyperHeap (3269 milliseconds)
        All verification conditions discharged successfully
    
    **Section 3 of the paper**

    examples/preorders/MonotonicArray.fst

        /home/wenfeng/fstar/bin/fstar.exe  --use_hints --verify_module MonotonicArray MonotonicArray.fst
        Verified module: MonotonicArray (6666 milliseconds)
        All verification conditions discharged successfully
        
    examples/preorders/Protocol.fst
        
        home/wenfeng/fstar/bin/fstar.exe  --use_hints --verify_module Protocol Protocol.fst
        ./Protocol.fst(23,0-23,9) (Warning): Adding an implicit 'assume new' qualifier on byte
        Verified module: Protocol (13887 milliseconds)
        All verification conditions discharged successfully

    ulib/FStar.Monotonic.HyperStack.fst

        ~/fstar/ulib$ fstar.exe FStar.Monotonic.HyperStack.fst 
        WARNING: (98047,59): pattern does not contain all quantified variables.
        Verified module: FStar.Monotonic.HyperStack (6206 milliseconds)
        All verification conditions discharged successfully

    ulib/FStar.Monotonic.RRef.fst
    
        ~/fstar/ulib$ fstar.exe FStar.Monotonic.RRef.fst 
        WARNING: (87918,59): pattern does not contain all quantified variables.
        Verified module: FStar.Monotonic.RRef (1314 milliseconds)
        All verification conditions discharged successfully


    **Section 4 of the paper**

    examples/preorders/Ariadne.fst

        /home/wenfeng/fstar/bin/fstar.exe  --use_hints --verify_module Ariadne Ariadne.fst
        Verified module: Ariadne (4155 milliseconds)
        All verification conditions discharged successfully





