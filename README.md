# IPython Notebook Buildpack

The `ipython-notebook-buildpack` is a [Cloud Foundry][] buildpack for exposing [IPython Notebook][] files.

## Usage
To use this buildpack specify the URI of the repository when pushing an IPython Notebook file (or directory of files) to Cloud Foundry.

    cf push --buildpack https://github.com/gopivotal/ipython-notebook-buildpack.git

As the IPython notebook uses Websockets you must access it on Cloud Foundry using port 4443, e.g. https://<app-subdomain>.cfapps.io:4443


## Notebook Dependencies
The buildpack supports dependencies declaration using a `requirements.txt` file located in the root of the directory being pushed to Cloud Foundry.


[Cloud Foundry]: http://www.cloudfoundry.com
[IPython Notebook]: http://ipython.org/notebook.html
