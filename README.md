# Heroku Anaconda Buildpack

`heroku-buildpack-conda` is a heroku and cloudfoundry builpack to deploy python using [continuum](https://www.continuum.io/)s anaconda. Latest miniconda installer is used from [here](https://repo.continuum.io/miniconda/).

Be aware that this buildpack uses `-b` option from miniconda installer:

```
-b           run install in batch mode (without manual intervention),
             it is expected the license terms are agreed upon
```

You can find the [license terms](http://docs.continuum.io/anaconda/eula) in the anaconda documentation.

## Conda Version

Create a file named `conda_runtime.txt` containing the Miniconda version you wish to use as conda-runtime. Otherwise `Miniconda3-latest-Linux-x86_64.sh` (python 3.x) will be used.

Find different runtime versions here: http://repo.continuum.io/miniconda/

## Python version

If you want to use a special python version, you should set it in your environment.yml:

```
name: root
dependencies:
  - python=2.7
  - ...
```

## Environment

Additional packages are installed using an `environment.yml` file. The environment name is ignored.

Find an example [here](https://github.com/pl31/heroku-jupyter/blob/master/environment.yml).

## License
This buildpack is released under version 2.0 of the [Apache License](http://www.apache.org/licenses/LICENSE-2.0).
