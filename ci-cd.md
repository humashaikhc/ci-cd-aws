# CI CD Jenkins -> AWS


## Demo

- CI
-The video shows the changes made in both branches and the build triggered in jenkins for ci project and cd project.

![cicd](https://user-images.githubusercontent.com/117640150/214650900-d5907bc4-cbbb-4999-8793-d91b04e9ba5f.gif)

- CD


---

## How have you use Jenkins to add Continuous integration with this project?(build and test)
- Gave Jenkins access to github repo using jenkins public key and adding deploy key in github repo.
- Building triggers to test when something is pushed on github.
- Running shell commands to run tests.

### How did you allow Jenkins access to the Github repo?
-Added Jenkins public key in our deploy keys on github -Then added jenkins private key in the ci project on Jenkins.

### How did you get the Github repo to trigger the build?
-Added a new webhook with jenkins URL link(IP address)/github-webhook/

---

## How have you use Jenkins to add Continuous delivery with this project?(focusing on deployment/delivery)
- Gave Jenkins access to EC2 instance ssh key.(AWS key)
- Trigger only when ci comes out stable and all tests pass and execute the shell commands
- shell commands include the script to run the deployment and add software and dependencies.(setup environment)

### How did you allow Jenkins access to the EC2 instance?
- Downloaded the EC2 instance ssh key and used it in jenkins cd project at ssh agent to allow access.

### How did you get the CI project to trigger the CD build?
- We made a new cd project in jenkins and added it in post-build actions on our ci project.
- Build other projects in ci project to trigger only if the build is stable.

###The final output of the landing page after changes

---![ONLY THE PAGE](https://user-images.githubusercontent.com/117640150/214648462-0faa293c-271c-4e57-a904-1df293c3a50f.gif)
