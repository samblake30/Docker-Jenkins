# _Configuration for Pipeline#1_

### _Process for Configuration of First Pipeline_


* _Create a new Jenkins Pipeline named ```pipeline1``` which will run on JenkinsWorker1 (labeled `docker1` and to be run with the args ```'-u root'``` option). This pipeline will run a containerized job using the python:alpine image to pull down code, set up the Python environment and execute the code, then archive any JPG files that were downloaded._

* _Steps are given below_
  * _Install git inside container:_
    ```bash 
       apk add git
    ```
  * _Clone source code:_
    ```bash
       git clone https://github.com/linuxacademy/content-pipelines-cje-labs.git
    ```
  * _Install modules required by code:_
    ```bash
       pip install -r content-pipelines-cje-labs/lab3_lab4/dog_pics_downloader/requirements.txt
    ```
  * _Execute the code to test it:_
    ```bash
       python content-pipelines-cje-labs/lab3_lab4/dog_pics_downloader/dog_pic_get_class.py
    ```
  * _Archive any files with the ***.jpg*** extension. Optionally, for bonus marks, also include success and cleanup (to delete folder ***content-pipelines-cje-labs***) steps in the post block of the pipeline._
       
       
