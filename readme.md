JENKINS AS PIPELINE
===================

1. First we are going to create a repo on github to save our project

2. Install Jenkins (dekstop or in container) and go to manage plugins and install 'Blue Ocean'

3. Activate Blue Ocen for left menu and create new pipeline, choose Github as repository for code

4. Go to Settings -> developer settings on Github and create an access token and paste it in Jenkins when ask for it. then choose the repository

5. Create some dummy stages with steps of type 'print message' and save it. It will as you to save pipeline in the github repository.

6. Pipeline will run and then if you go to github you will see the Jenkinsfile automatically created!!

Declarative pipeline
--------------------

This is a recent add to Jenkins where there is a more simplified and optimize sintax on top of the Pipeline. It is written inside a Jenkins file. 

you can see more in the Jenkins page [here](https://www.jenkins.io/doc/book/pipeline/syntax/#:~:text=The%20basic%20statements%20and%20expressions,be%20on%20its%20own%20line.)

 Creating files and archiving them
---------------------------------

You can create a log file for instance and save it within your pipeline.

1. Go to any step, let's say test and create a new stage with any any of type 'write file to the workspace'

2. choose any name and also some text

3. Then create a new stage called 'Artifacts' of type 'archiveartifacts' and put the name of the file you created above. Then when you build, in the 'Artifacts' tab you will be able to see your file in there.