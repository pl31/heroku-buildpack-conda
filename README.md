# IPython Notebook Buildpack

The `ipython-notebook-buildpack` is a [Cloud Foundry][] buildpack for exposing [IPython Notebook][] files.

## Usage
To use this buildpack specify the URI of the repository when pushing an IPython Notebook file (or directory of files) to Cloud Foundry.

    cf push --buildpack https://github.com/ihuston/ipython-notebook-buildpack.git

As the IPython notebook uses Websockets you must access it on Cloud Foundry using port 4443, e.g. https://app-subdomain.cfapps.io:4443


## Notebook Dependencies
The buildpack supports dependencies declaration using a `requirements.txt` file located in the root of the directory being pushed to Cloud Foundry.

## Notebook Config
Additional notebook configuration can be specified using a file named `additional_notebook_config.py` in the root of the app directory.

In particular you can password protect your notebook server by creating a SHA1 hash of your password and adding this to the config file as follows:

    # Password to use for web authentication
    c = get_config()
    c.NotebookApp.password =
    u'sha1:85607904acb0:bd228c0989e8df2018d0777428b1bb974ba7d2c0'

See [the IPython documentation](http://ipython.org/ipython-doc/stable/notebook/public_server.html) for further
instructions and more configuration options for the server.

## License
This buildpack is released under version 2.0 of the [Apache License](http://www.apache.org/licenses/LICENSE-2.0).

[Cloud Foundry]: http://www.cloudfoundry.com
[IPython Notebook]: http://ipython.org/notebook.html
