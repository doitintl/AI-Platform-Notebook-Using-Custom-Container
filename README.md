# AI-Platform-Notebook-Using-Custom-Container
Example of using AI platform notebook - custom container from scratch.

This following example refers to AI-Platform-Notebook for using a custom container from scratch and based on https://github.com/jupyter/docker-stacks/tree/master/base-notebook.

Following Google Cloud docs about using custom continer, <b>the recommended way to create a custom container it's derivative container</b> but in some cases, we can't use that approach. 

In order to be compatible with AI Platform Notebooks, changes were made in the jupyter_notebook_confing.py, and new the Dockerfile-root is the new one that includes the all necessary changes.

The next step is to create an image from the <b>Dockerfile-root</b> and push it to the GCR.

Run the following command:
```
1. docker build -f Dockerfile-root -t gcr.io/<PROJECT-ID>/<IMAGENAME>:<TAG> .

2. gcloud auth configure-docker

3. docker push gcr.io/<PROJECT-ID>/<IMAGENAME>:<TAG>

``` 
At this point, we have a new container in the GCR, and we can create new Notebook using this image.

To create a new Notebook using the new image please follow up Google instructions https://cloud.google.com/ai-platform/notebooks/docs/custom-container#create_an_instance_using_a_custom_container


