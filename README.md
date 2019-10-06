# AI-Platform-Notebook-Using-Custom-Container
Example of using AI platform notebook - custom container from scratch.

This following example refers to AI-Platform-Notebook for using a custom container from scratch and based on https://github.com/jupyter/docker-stacks/tree/master/base-notebook.

Following Google Cloud docs about using custom continer[1], <b>the recommended way to create a custom container it's derivative container</b> but in some cases, we can't use that approach. 

In order to be compatible with AI Platform Notebooks, changes were made in the jupyter_notebook_confing.py, and new the Dockerfile-root is the new one that includes the all necessary changes.

Now, all that we need to care about is to build a new image from the "Dockerfile-root" push it to the DockerHub or to the GCR.

Create a new Notebook from the Custom container.

