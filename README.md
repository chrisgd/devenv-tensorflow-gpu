# devenv-tensorflow-gpu
Base project that sets up a tensorflow with GPU enabled dev container for VSCode. 
This can just be used as a starting point for a tensorflow project or added to one
to enable GPU support for machine learning.

Based on details from:
*  https://www.tensorflow.org/install/docker, and
*  https://hub.docker.com/r/tensorflow/tensorflow/

You can pretty much just drop this into your top-level folder for VSCode. You need:
-  Docker
-  CUDA drivers on your host platform

After that, you can reopen your repository and it should prompt you to open the dev
environment.
