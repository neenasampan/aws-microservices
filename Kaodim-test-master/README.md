# Kaodim-test
this repository is built to solve an interview question from Kaodim

I Chose to scale up a sample ruby app using Code Pipeline through which we can hold entire CI/CD pipeline.

We need to connect the pipeline in various stages. Stage1 will be integration with Codecommit (we can integrate other popular version control tools as well)
then we need to connect to code build where the build happens (basically execution of cloudformation template).
Ideally we execute the changeset but for now I just executed the stack directly.


Step1 : create codecommit repository.
Step2 : Push the code in this repository to codecommit repo (we can also integrate this repo but we will need ssh keys to clone my repo)
Step3 : Create Codepipeline (source stage as codecommit, build stage as code build, deploy stage as cloudformation)
the moment we push the code to the codecommit repository we get the codepipeline started and cloudformation will deploy it.
