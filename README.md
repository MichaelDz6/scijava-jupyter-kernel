# scijava-jupyter-kernel
[![Build Status](https://travis-ci.org/hadim/scijava-jupyter-kernel.svg?branch=master)](https://travis-ci.org/hadim/scijava-jupyter-kernel)

`scijava-jupyter-kernel` aims to be a Jupyter kernel that integrate well with ImageJ. See https://imagej.net/Jupyter for more details.

Under the hood `scijava-jupyter-kernel` uses the [Beaker base kernel](https://github.com/twosigma/beakerx/tree/master/kernel/base).

Languages supported are :

- Groovy
- Python
- BeanShell
- Clojure
- Java
- JavaScript
- R
- Ruby
- Scala

See here for more details : https://imagej.net/Scripting#Supported_languages

![Scijava Jupyter Kernel Installation](teaser.gif)

## Installation - Standalone

**Note : Only for Linux and OSX for now.**

- Install Anaconda[Anaconda](https://www.continuum.io/downloads)
- Do the following : 

```bash
conda config --add channels conda-forge
conda install scijava-jupyter-kernel
```

## Installation - ImageJ/Fiji

- Clone, compile and install Beakerx base kernel :

```bash
git clone https://github.com/twosigma/beakerx.git
cd beakerx/kernel/base/
gradle publishToMavenLocal
```

- Clone and compile `scijava-jupyter-kernel` :

```bash
git clone https://github.com/hadim/scijava-jupyter-kernel.git
cd scijava-jupyter-kernel
mvn -Dimagej.app.directory="PATH-TO-YOUR-IMAGEJ-REPO" install
```

- Start ImageJ/Fiji and launch `Analyze > Jupyter Kernel > Install Scijava Kernel`.
- Set the path to your Python binary.
- Choose a language (for example `jython` or `groovy`) or you can choose to install all the available languages.
- Choose a log level.

To try the kernel, launch `jupyter notebook` or `jupyter lab`. Your kernel should appear in the kernel list.

**Note** : To quickly test a kernel, use `jupyter console --kernel=scijava-python`.

## Python

We strongly suggest the use of the [Anaconda Python distribution](https://www.continuum.io/downloads) + the use of the [conda-forge channel](https://conda-forge.github.io/). That way, your Python and all your libs will be kept synced and updated.

## License

Under Apache 2.0 license. See [LICENSE](LICENSE).

## Authors

- Hadrien Mary <hadrien.mary@gmail.com>
