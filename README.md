# Flex Meta-Storms

![Version](https://img.shields.io/badge/Version-1.0%20-brightgreen)
![Release date](https://img.shields.io/badge/Released%20date-Sept.%2021%2C%202022-brightgreen)



# Contents

- [Introduction](#introduction)
- [System Requirement and dependency](#system-requirement-and-dependency)
- [Installation guide](#installation-guide)
- [Usage](#usage)
- [Example dataset](#example-dataset)
- [Tools in this package](#tools-in-this-package)
- [Supplementary](#supplementary)

  

# Introduction

Flex Meta-Storms (FMS) can mine potential relationships generated by a small subset of microbes in community samples, elucidating beta diversity with greater sensitivity and flexibility, thereby contributing to a deeper understanding of microbe-prime host interactions effect. It takes the exact markers in a community sample as input, and with the help of precomputed relationships between microbes from a reference database, finds approximate markers for biomarkers, and performs weighted calculations.FMS is available as a standalone package and is also integrated into Parallel-Meta Suite for use.

# System Requirement and dependency

## Hardware Requirements

Flex Meta-Storms only requires a standard computer with sufficient RAM to support the operations defined by a user. For typical users, this would be a computer with about 2 GB of RAM. For optimal performance, we recommend a computer with the following specs:

  RAM: 8+ GB  
  CPU: 4+ cores, 3.3+ GHz/core

## Software Requirements

OpenMP library is the C/C++ parallel computing library. Most Linux releases have OpenMP already been installed in the system. In Mac OS X, to install the compiler that supports OpenMP, we recommend using the Homebrew package manager:
```
brew install gcc
```

# Installation guide

## Automatic Installation (recommended)

At present, Flex Meta-Storms provides a fully automatic installer for easy installation.

**a. Download the package**

```
git clone https://github.com/qdu-bioinfo/flex-meta-storms.git	
```

**b. Install by installer**
```
cd flex-meta-storms
source install.sh
```

The package should take less than 1 minute to install on a computer with the specifications recommended above.

The example dataset could be found at ???example??? folder. Check the ???example/Readme??? for details about the demo run.

## Manual Installation

If the automatic installer fails, Flex Meta-Storms can still be installed manually.

**a. Download the package**
```
git clone https://github.com/qdu-bioinfo/flex-meta-storms.git	
```

**b. Configure the environment variables (the default environment variable configuration file is ???~/.bashrc???)**
```
export FlexMetaStorms=Path to Flex Meta-Storms
export PATH=???$PATH:$FlexMetaStorms/bin/???
source ~/.bashrc
```
**c. Compile the source code**

```
cd flex-meta-storms
make
```
# Usage
**a.  Calculate exact markers distance**
- User installed as a package
```
FMS-comp-taxa -T samples.Abd -M samples.xls -K -o samples.dist
```
The output file ???samples.dist??? is the pairwise distance matrix. 

- User installed as a PMS plugin
```
PM-comp-taxa-local -T samples.Abd -M samples.xls -K -o samples.dist
```
The output file ???samples.dist??? is the pairwise distance matrix. 

**b. Calculate Flex Meta-Storms distance**
- User installed as a package
```
FMS-comp-taxa -T samples.Abd -M samples.xls -L -o samples.dist
```
The output file ???samples.dist??? is the pairwise distance matrix. 

- User installed as a PMS plugin
```
PM-comp-taxa-local -T samples.Abd -M samples.xls -L -o samples.dist
```
The output file ???samples.dist??? is the pairwise distance matrix. 

# Example dataset
Here, we provide a demo dataset (Real dataset I) in the "examples" folder with real species information for 88 individuals. In this package, "sample.abd" is the relative abundance at the OTU level, and "samples.xls" are the exact markers of the samples generated using the built-in script PM_Marker_test.R.
To run the demo, you can either:
```
cd example
sh Readme
```
or type the following command to calculate the FMS distance:
- User installed as a package
```
FMS-comp-taxa -T samples.Abd -M samples.xls -L -o samples.dist
```
The output file ???samples.dist??? is the pairwise distance matrix. 

- User installed as a PMS plugin
```
PM-comp-taxa-local -T samples.Abd -M samples.xls -L -o samples.dist
```

This demo run should take less than 1 minute on a recommended computer.

# Tools in this package
**a. FMS-comp-taxa or PM-comp-taxa-local**

Calculate Exact markers distance or Flex Meta-Storms distance between samples. Run:
```
FMS-comp-taxa -h 
or
PM-comp-taxa-local -h
```
for detailed parameters.

**b. Global-comp-taxa or PM-comp-taxa**

It Calculate the global distance between samples. Run:
```
Global-comp-taxa -h
or
PM-comp-taxa -h
```
for detailed parameters.


# Supplementary

[Real Dataset 1](http://) Contains 88 autism samples inferred from 16S rRNA genes by Parallel Meta-Suite.

[Real Dataset 2](http://) Contains 104 colorectal cancer samples inferred from 16S rRNA genes by Parallel Meta-Suite.





