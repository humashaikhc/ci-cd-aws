# CI CD Jenkins -> AWS


## Demo

- CI

-The gif below depicts the changes made in a readme.md file and the changes pushed to feature-branch.
-The CI in Jenkins was triggered that run all the tests and had a successful build.

![readme-opt](https://user-images.githubusercontent.com/117640150/214801706-cb69821d-d6d3-44a2-8020-397ee08ce9c4.gif)

-The changes made in readme.md was added in the main branch along with the feature-branch. The gif shows both the CI and CD build successfull in Jenkins.

![cicd](https://user-images.githubusercontent.com/117640150/214650900-d5907bc4-cbbb-4999-8793-d91b04e9ba5f.gif)

- CD
-The gif shows changes made in index.html to display on the page. 
-After the push the build in Jenkins was triggered along with showing the changes on the page at the end.

![aws-opt](https://user-images.githubusercontent.com/117640150/214801632-c95eb0ab-e9b1-4d03-ba81-684316f6772b.gif)

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
