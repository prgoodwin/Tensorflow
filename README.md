# Getting Started

This will guide you through how to pull the docker container for TensorFlow with Python 3 and Jupyter Notebooks on Windows.  


# Prerequisites

We assume you have docker desktop installed.  

# Creating a Directory to Mount

Docker simplifies the process of getting software running on your machine by providing a virtual computing environment.  However, we want to save our work locally which requires mounting a local directory to our container.

First, create a directory in which to save your notebooks. 

```
mkdir my_jupyter_notebooks
```

# Running your docker 
Next we need to install and run our container.  This may take a little while the first time.  

```
 docker run -it -p 8889:8888 -v ./my_jupyter_notebooks:/tf tensorflow/tensorflow:latest-py3-jupyter
```

When the container starts, you should see a screen with with a bunch of information about your Jupyter server.  All of the urls that you see should have a token that you will need.  Copy it to your clipboard.


In a webbrowser, navigate to 'localhost:8889'  and enter your token in the password.  

This brings you to the tensorflow tutorials section.

Congratulations!  You've successfully started your Docker Container.

# Other Useful Tricks

Other commands...

## Finding your container's IP Address

```
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name_or_id
```

