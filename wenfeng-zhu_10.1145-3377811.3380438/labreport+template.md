# Lab Report on Research Artifact

* Date of examination: 26.12.2021
* Start time: 13:30
* End time: 15:30
* * * 
* Date of examination: 27.12.2021
* Start time: 20:30
* End time: 22:00
* * *
* Date of examination: 02.01.2022
* Start time: 8:30
* End time: 9:00
* * *
* Date of examination: 04.01.2022
* Start time: 13:30
* End time: 14:00

## Metadata

* Paper DOI (necessary):  10.1145/3377811.3380438
* Artifact DOI (optional): 
* Badges achieved in regular artifact evaluation: Artifacts Available v1.1, Artifacts Evaluated – Reusable v1.1  
* Time (in minutes) needed to read the paper: 45 min

## Availability

* [x] Artifact is archived in a public archive with a long-term retention policy(zenodo)
* [ ] Artifact is available on a different website
* [ ] Artifact is available in the version that was submitted to artifact evaluation
* [ ] Artifact is available in the version that passed artifact evaluation
* [ ] Artifact is available in a public version control system
* [ ] Artifact is available in a self-contained form (container, VM)
* Time (in minutes) needed for the check: 15 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions. The following are just examples! You can skip any of them or add any additional ones that make sense for the links we provided you. -->
* Artifact can be downloaded from zenodo.


### Observations

<!-- Note all observations (negative, neutral, or positive) made -->
#### Negative
* There is no link that points to the zenodo archive in the version that was submitted to artifact evaluation.

## Artifact Type

<!-- Please indicate the artifact type. Multiple selection possible. -->

* [x] Code
* [x] Dataset
* [ ] Automated proof
* [ ] Manual proof
* [ ] Other (please specify)
* Time (in minutes) needed for the check: 5 min

### Checks performed
<!-- Note all checks you performed here to answer the above questions -->
* Confirm the steps of the experiment according to the instruction file, i.e., README file.



### Observations
#### Positive
* The artifact provides all intermediate files for the entire experimental process. That allows users who want to reproduce the experiment can start the experiment from any step.
* Users have great freedom to reproduce the experiment and can use their own data sources at any step in between.
* The artifact contains the source code of the tools used in the experiment.
* The artifact provides two alternatives to set up the environment of the experiment, **Docker-base** and **Setup on your own system**.
* When users do not want to install the packages by themselves, the artifact provides the android platforms compressed files from ```android-platform-10``` to ```android-platform-28``` that as the support of artifact.
* In the folder ```DroidMacroBench``` comprises 12 of the 200 most downloaded real-world apps from the Google Playstore, a set of heap-snapshots for this apps as used in the experiments and a labeled list of findings of the FlowDroid analyzer (located in ```DroidMacroBench/groundTruth.csv```).
* With ```DroidMacroBench_heap_dumps.zip``` , the authors deliver a zip file with the heap snapshots that extracted from the DroidMacroBench apps.
* The authors also provided the result from their experiment that located in folder ```Results```.
* The specifical processes of the experiment located in the folder ```evaluation-scripts```.

## Functional

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [x] Artifact is considered functional
* [ ] Artifact is NOT considered functional
* [ ] Artifact is considered partially functional 

* Time (in minutes) needed for the check: 60 min

### Checks performed

<!-- Note all checks you performed here to answer the above questions -->
* [x] Documented -- This artifact has an extremely detailed README file as a guide to the experimental environment setup, the file structure and function descriptions, and the experimental steps in great detail.
* [x] Consistent-- The experiments supported by this artifact, as well as the results of the included experiments performed by the authors, are strong support for the paper.
* [x] Complete:-- The artifact contains a complete environment setup, as well as experimental steps. Directly available intermediate files and specific customization steps are provided for each customizable step.
* [x] Exercisable-- A script file for each step of the experiment is provided, along with instructions to help the user start from any step in between.
### Observations
<!-- Note all observations (negative, neutral, or positive) made -->

## Reusable

<!-- Venues before 2017 did not have the ACM badges. Therefore, the calls for artifacts usually do not contain explicit criteria for functional/reusable. In this case, please use the definitions and criteria from the ACM artifact evaluation/badging website. -->

* [x] Artifact is considered reusable
* [ ] Artifact is NOT considered reusable
* [ ] Artifact is considered partially reusable
* Time (in minutes) needed for the check: 30+40 min

### Checks performed

* Read the documentation of the artifact
* Steps to verify its functionality
* Since this artifact provides the intermediate files used by the authors in their experiments, as well as instructions to users on how to use their own data sources, for each step of the experiment, the experiment needs to be repeated for the data provided by the authors as well as the data from the users to verify the customizability claimed by the authors.

<!-- Note all checks you performed here to answer the above questions -->

### Observations(27.12.2021)

<!-- Note all observations (negative, neutral, or positive) made -->
#### Negative
* The artifact provided two ways of set-up, in which the docker-based environment settings are no longer available. Another set-up has some issues cased by update of ADK.
1. During the building of Docker Image, it always threw an error when the calling of sdkmanager:
```
 > [ 5/13] RUN for ((i = 10 ; i <= 28 ; i++ )); do sdkmanager "platforms;android-$i"; done:
#8 0.505 Exception in thread "main" java.lang.NoClassDefFoundError: javax/xml/bind/annotation/XmlSchema
#8 0.506        at com.android.repository.api.SchemaModule$SchemaModuleVersion.<init>(SchemaModule.java:156)
#8 0.506        at com.android.repository.api.SchemaModule.<init>(SchemaModule.java:75)
#8 0.506        at com.android.sdklib.repository.AndroidSdkHandler.<clinit>(AndroidSdkHandler.java:81)
#8 0.506        at com.android.sdklib.tool.sdkmanager.SdkManagerCli.main(SdkManagerCli.java:73)
#8 0.506        at com.android.sdklib.tool.sdkmanager.SdkManagerCli.main(SdkManagerCli.java:48)
#8 0.506 Caused by: java.lang.ClassNotFoundException: javax.xml.bind.annotation.XmlSchema
#8 0.506        at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:581)
#8 0.506        at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:178)
#8 0.506        at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:522)
#8 0.506        ... 5 more
```
* Through research, the error was caused by an overly high level of JDK. The authors state that the experiment was conducted with JDK-8. But the basic docker image used in dockerfile, ```runmymind/docker-android-sdk:ubuntu-standalone```. According to the update history of this image, the version of OpenJDK in this image was upgraded from jdk-8 to jdk-11 on August 3, 2021. This causes an error in the sdkmanager call.

2. During the process of setting up the environment manually according to the guide, there was an error in the setting of one of the ADK environment variables.
* Starting from Android SDK Command-line Tools 1.0.0 (6200805), in contrast to Android SDK 26.1.1 (4333796), the tools directory hierarchy has been changed. And the behavior has changed again since the build 6858069 (Android SDK Command-line Tools 3.0). After unzipping the package, the top-most directory you'll get is ```cmdline-tools```.
* The user needs to manually set an intermediate directory ```/tools``` at the lower level of ```/cmdline-tools``` and And put all files inside ```/cmdline-tools``` under ```/tools```.
* Wrapping ```tools``` directory inside ```cmdline-tools``` directory would make it work, and help you get rid of the annoying ```--sdk_root``` argument.
* According to the new directory structure, the environment variables and PATH should be set as follows:
```
$ANDROID_SDK_ROOT =  the top-level directory of unpacked cmdline-tools
$ANDROID_HOME =  the top-level directory of unpacked cmdline-tools
## ANDROID_SDK_ROOT is the name of the environment variable recommended for the current ADK, and ANDROID_HOME is the name used in the code of this experiment.
PATH=$PATH:$ANDROID_SDK_ROOT/cmdline-tools/latest/bin:$ANDROID_SDK_ROOT/cmdline-tools/tools/bin
```

### Observations(02.01.2022)
* The experiment was conducted on a remote server with 100GB of RAM provided by Stefan, on Ubuntu 20.04.
* According to the authors' description, 200 Android applications were analyzed in the original experiment, which ran for several days. In contrast, the 12 example applications provided by the authors were chosen as samples for this experiment.
* At the end of the previous experiment, the analysis script ```runEvaluation.sh``` was mounted in the backend of the remote computer via Tmux.
#### Negative
* The results were finally accepted on 02.01.2022, and it was found that only 5 of the 12 applications were successfully used in the experiment, and they were **Wish, Outlook, SkyDrive, Spotify and UC-brower**.
* For the rest of the applications, according to the logs, the problem was in the Unpacking stage, and since these apk files were provided by the author, it was not possible to determine if the failure was due to corrupt apk files or other reasons.
#### Positive
* Although the experimental sample was again reduced from 12 to 5, some of the conclusions drawn from the experiment were still able to fit the conclusions in the paper. And the overall artifacts all showed good executability.
* The final result of experiment can be found in ```evaluation-scripts/analysisLog.csv```, It contains all the necessary data covered by the paper.
* The artifact also provides instructions on the subset of the experiments even not run the experiments at all:
1. change the used heuristics to, for example, only use ```snapshot_filter.FirstOnly()``` in line 22 of ```evaluation-scripts/evaluation.py``` to only run the experiments on one snapshot per app.
2. run a single manual experiment with a setup of your choice 
3. do not run the experiments at all and have a look at the results directly. See Experimental Results in ```Result``` folder.
* After verification, it is known that these operations can significantly reduce the experiments of the experiment and obtain the corresponding partial experimental results.
* Overall, this artifact presents excellent reusability and has extremely detailed step-by-step instructions that provide users with a wealth of options for use. It is also very convenient for the evaluator since the experiment can be intervened or customized from any step.

## Result reproducibility with the artifact

<!-- Please start with results that the artifact documentation claims to be reproducible. If no such claims can be found, please note this in the observations. After that, please check which results/conclusion are supported by the artifact and which ones are not (irrespective of the results in the paper actually match your observations with the artifact). In the last step, please check which of the supported results/conclusions match. -->

* [ ] Results from the paper are fully supported by the artifact (i.e., it should in theory be possible to reproduce all results from the paper)
* [x] Results from the paper are partially supported by the artifact
* [ ] Results from the paper are not supported by the artifact
* [ ] Results that are supported by the artifact could be fully reproduced
* [ ] Results that are supported by the artifact could be partially reproduced
* [ ] Results from the paper could not be reproduced
* Time (in minutes) needed for the check: 20 min

### Checks performed
* Run the experiment to get the csv file ```analysisLog.csv``` containing the necessary data.
* Compare the data results ```all_results.csv``` used for the paper, which in the ```Result``` folder.

<!-- Note all checks you performed here to answer the above questions -->

### Observations
* Due to the lack of in-depth knowledge of taint analysis, I was able to judge the experimental results simply from the data comparison.

#### Positive
* Although the data obtained from this experiment is a subset of the full experimental data (5/200), the data obtained from the successfully run application presents the same data as the thesis data.
* For the source data of the paper, the authors also provided a visualization based on the Jupyther Notebook file, which was not "formally" visualized in this experiment due to the consistency derived from the direct comparison of the data.


<!-- Note all observations (negative, neutral, or positive) made -->
<!-- In case of partial result reproduction, please state what did and did not work -->






