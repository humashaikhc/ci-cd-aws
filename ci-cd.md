# CI CD Jenkins -> AWS

Give a brief overview of the project.

## Demo

Research how you can create Gifs from screen recordings, demo the following:

- CI
  - Make a change to the project on your feature branch -> push changes to repo
  - Show pipeline running in Jenkins -> Show main branch has been updated

- CD
  - Make a change to the project on your feature branch -> push changes to repo
  - Show pipeline running in Jenkins -> Show ci pipeline triggers build pipeline
  - Show updated instance

_Feel free to add more to the points above_

---

## How have you use Jenkins to add Continuous integration with this project?(build and test)
-Gave Jenkins access to github repo using jenkins public key and adding deploy key in github repo.
-Building triggers to test when something is pushed on github.
-Running shell commands to run tests.

### How did you allow Jenkins access to the Github repo?
-Added Jenkins public key in our deploy keys on github -Then added jenkins private key in the ci project on Jenkins.

### How did you get the Github repo to trigger the build?
-Added a new webhook with jenkins URL link(IP address)/github-webhook/

---

## How have you use Jenkins to add Continuous delivery with this project?(focusing on deployment/delivery)
-Gave Jenkins access to EC2 instance ssh key.(AWS key)
-Trigger only when ci comes out stable and all tests pass and execute the shell commands
-shell commands include the script to run the deployment and add software and dependencies.(setup environment)

### How did you allow Jenkins access to the EC2 instance?
-Downloaded the EC2 instance ssh key and used it in jenkins cd project at ssh agent to allow access.

### How did you get the CI project to trigger the CD build?
-We made a new cd project in jenkins and added it in post-build actions on our ci project.
-Build other projects in ci project to trigger only if the build is stable.

---