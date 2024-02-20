# **Python Installation  
  
Installation Guidebook**

|                    |                |
| ------------------ | -------------- |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
|                    |                |
| **Creation date:** | 05.12.2023     |
| **Version 1.0:**   | 05.12.2023     |
| **Author:**        | Andrej Cepygin |

# **Table of contents**

[1. General 1](#general)

[2. Installation 2](#installation)

[3. Environments 4](#environments)

[4. Python 6](#python)

[5. Packages 7](#packages)

**Table of figures**

No table of figures entries found.

## General

### About the guidebook

This Guidebook goes through the steps necessary to install Python. For
Akkodis internal project we have preferred to use conda installations
from the official conda website. These are free and everyone is advised
to use the latest version from their official website.

## Installation

Conda environment allows us to manage multiple setups in one machine.
Especially when we must use a certain version of the libraries for a
project and a different version for another project, it makes our work
more manageable.

Firstly, we must install Anaconda with the installation setup from the
official anaconda website:

[Free Download | Anaconda](https://www.anaconda.com/download/)

![](media/image4.png)![](media/image5.png)In general, the installation
setup provides the standard settings needed to install anaconda on the
company windows machine.

![](media/image6.png)You can select your installation destination or
keep the already given by the installation setup.

![](media/image7.png)After the installation is finished, we open the
anaconda prompt from the start search.

You can verify if conda is properly installed and running by typing the
code:

###### ![](media/image8.png)conda --version

conda should display the number of the version you have installed.

Before you start you should update conda to the current version:

###### conda update conda

If a newer version is available, type y to update:

###### Proceed (\[y\]/n)? y

## Environments

Conda allows you to create separate environments containing files,
packages and their dependencies that will not interact with other
environments.

Conda’s default environment is named *base*, but we don’t want to put
programs in our base environment. To isolate our programs from each
other, we create a separate environment.

1.  Create a new environment and install a package in it.

> We will create a new environment called *my\_env* and install the
> *pandas* package:

conda create --name my\_env pandas

> ![](media/image9.png)conda checks which additional packages pandas
> will need, and asks if you want to proceed:

###### Proceed (\[y\]/n)? y

> Type “y” and press Enter to proceed.

2.  Activate the new environment.

> After we created a new environment, we can use it with:

###### ![](media/image10.png)conda activate my\_env

> Now any conda command will go to that environment until it is
> deactivated.

3.  See a list of all your environments.

> The command

###### conda info –-envs 

> provides a list of all your environments, the active environment is
> marked with an asterisk(\*).

![](media/image11.png)

4.  Change current environment back to the default (base).

> The command

###### conda activate 

> changes your current environment back to default (base), you can still
> repeat the

###### conda info -–envs 

> command.

Remember to deactivate the environment when you're done:

###### 

###### conda deactivate

This keeps your system environment clean and avoids conflicts between
different Python versions or packages.

## Python

When creating a new environment, conda installs the same Python version
you used when you downloaded and installed Anaconda. If you want to use
a different version of Python create a new environment and specify the
version of Python.

We create a new environment named “snow” that contains Python 3.9:

###### ![](media/image12.png)conda create –-name snow python=3.9

when conda asks, if you want to proceed, type “y” and press Enter.

After we activated the environment with:

###### conda activate snow

![](media/image13.png)we can verify that the environment has been added
and is active:

with

###### python –-version

![](media/image14.png)you can verify which Python version is used in
your current environment.

## Packages

In this section, you can check which packages you have installed, which
are available and look for a specific package to install it.

After you activated the environment, you want to search you can check if
a package you have not installed named “beautifulsoup4” is available
from Anaconda repository:

###### conda search beautifulsoup4

conda displays a list of packages with that name on the Anaconda
repository, so we know it is available.

![](media/image15.png)you can install this package into the current
environment:

###### conda install beautifulsoup4.

With

###### conda list

You can check if the newly installed package is in this environment.
