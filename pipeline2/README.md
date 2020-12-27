# _Configuration for Pipeline#2_
![Jenkins-Pipeline2](https://img.shields.io/badge/Jenkins--Pipeline-2-blue)

### _Process for Configuration of Second Pipeline_


* _Create a new Jenkins Pipeline named pipeline2 which will run on JenkinsWorker2 (labeled docker2 and to be run with the args '-u root' option). This one will run a containerized job using the centos:7 image to pull down code, set up the Python environment and execute the code, then archive any watermarked jpg files which are produced that end with the string watermarked.jpg._

* _Steps are given below_
  * _Install Required Dependencies:_
    ```bash 
       yum -y install python3 python3-pip zlib-devel gcc git
    ```
  * _Copy over artifacts produced from the pipeline using the following step command:_
    ```bash
       copyArtifacts(projectName: 'pipeline1', flatten: true)
    ```
  * _Clone the Source Code:_
    ```bash
       git clone https://github.com/samblake30/Photo-Watermark-pipeline.git
    ```
  * _Install modules required by code:_
    ```bash
       pip install -r Photo-Watermark-pipeline/python-labs/image_watermarker/requirements.txt
    ```
  * _Execute the code to test it:_
    ```bash
       python Photo-Watermark-pipeline/python-labs/image_watermarker/watermark.py
    ```
  * _Archive, in post block, any files ending in ***watermarked.jpg***. Optionally, also run a cleanup step in post block to delete any files ending in jpg as well the directory ***Photo-Watermark-pipeline***. Ensure the second pipeline uses the Copy Artifact plugin option (checked during Pipeline configuration) to copy artifacts over from ```pipeline1```, and have Build Trigger enabled to be executed whenever ```pipeline1``` job executes successfully (i.e. a stable build). ```2nd Pipeline``` must execute automatically. Verify success by checking that archives and are jpg files. You have the independence to decide how many stages to use for executing the steps in both pipelines._
       
