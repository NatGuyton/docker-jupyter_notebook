## Jupyter Notebook

Quick and dirty implementation of Jupyter Notebook running atop miniconda.

This is set up for you to mount your notebooks from your docker host for persistance.  After it's up and running, check the container log for the login URI path and token, though you'll need to alter the hostname in the URL to fit your host.

#### Run example:

```
docker run -d \
	--name jupyter_notebook \
	-p 8888:8888 \
	-v /docker/notebooks:/opt/notebooks \
	guyton/jupyter_notebook
```

#### Log example:
```
[root]# docker logs jupyter_notebook
[I 17:28:39.613 NotebookApp] Writing notebook server cookie secret to /root/.local/share/jupyter/runtime/notebook_cookie_secret
[W 17:28:40.220 NotebookApp] WARNING: The notebook server is listening on all IP addresses and not using encryption. This is not recommended.
[I 17:28:40.236 NotebookApp] Serving notebooks from local directory: /opt/notebooks
[I 17:28:40.236 NotebookApp] 0 active kernels
[I 17:28:40.236 NotebookApp] The Jupyter Notebook is running at:
[I 17:28:40.236 NotebookApp] http://f1b39867adb4:8888/?token=48d65370f985bb7ac93c8ea2f59d6711b6d5bb5b378cb454
[I 17:28:40.236 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 17:28:40.237 NotebookApp] 
    
    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://f1b39867adb4:8888/?token=48d65370f985bb7ac93c8ea2f59d6711b6d5bb5b378cb454&token=48d65370f985bb7ac93c8ea2f59d6711b6d5bb5b378cb454
```
