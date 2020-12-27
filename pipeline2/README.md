# _Configuration for Pipeline#2_
![Jenkins-Pipeline2](https://img.shields.io/badge/Jenkins--Pipeline-2-blue)

### _Process for Configuration of Second Pipeline_


* _Create a new Jenkins Pipeline named ```pipeline2``` which will run on JenkinsWorker2 (labeled `docker2` and to be run with the args ```'-u root'``` option). This pipeline will run a containerized job using the python:alpine image to pull down code, set up the Python environment and execute the code, then archive any JPG files that were downloaded._

* _Steps are given below_
  * _Install git inside container:_
    ```bash 
       apk add git
    ```
  * _Clone source code:_
    ```bash
       git clone https://github.com/samblake30/Photo-Watermark-pipeline.git
    ```
  * _Install modules required by code:_
    ```bash
       pip install -r Photo-Watermark-pipeline/python-labs/dog_pics_downloader/requirements.txt
    ```
  * _Execute the code to test it:_
    ```bash
       python Photo-Watermark-pipeline/python-labs/dog_pics_downloader/dog_pic_get_class.py
    ```
  * _Archive any files with the ***.jpg*** extension. Optionally, for bonus marks, also include success and cleanup (to delete folder ***Photo-Watermark-pipeline***) steps in the post block of the pipeline._
       
