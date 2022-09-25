# IT5007 Tutorial Setup and Submission

* Download the docker image from https://luminus.nus.edu.sg/download/7acc0733-0ec2-4844-8c14-6b121aa0ec5c?name=docker_base_image.tar
* Launch the Docker application
* Launch powershell (for Windows) or terminal (for Mac) inside the directory with the downloaded image file, and import the image as follows
```
docker load -i docker_base_image.tar
```
* For Windows, launch a container from this image using
```
docker run -p 127.0.0.1:3000:3000/tcp --name tutorial3 -dit it5007_tutorial:t3 bash
```
* For Mac, use the following command with the extra '--platform linux/amd64' flag
```
docker run -p 127.0.0.1:3000:3000/tcp --platform linux/amd64 --name tutorial3 -dit it5007_tutorial:t3 bash
```
* Download the skeleton code for the tutorial, using ONE of the following methods:
  * Using Git Clone: 
    - Attach shell to container on VSCode.
    - ```cd /home```
    - $ ```git clone https://github.com/pkarthik88/IT5007 it5007```
  * Using Manual Download:
    * Manually download code from Github repository (https://github.com/pkarthik88/IT5007-Tutorial-3/) as a zip file. 
    * Copy the files over from your laptop to the tutorial3 docker container using the powershell command: 
    ```
    docker cp <path where the skeleton code is available> tutorial3:/home/it5007/
    ```
* Attach shell to the container on VSCode and work on your tutorial from /home/it5007/
```
cd /home/it5007/
```
* Once you are done with the changes to the code base, add node_modules to .gitignore, but ensure package.json reflects all packages you installed additionally.
* Make sure you commit your changes to the repository using the command:
  - $```git commit -am "answer to T3"```

## IT5007 Tutorial Submission
* Push the code to your PRIVATE github repository.
  * For this, create a private (empty) repository with Github or Bitbucket using their website. These websites usually ask if you want to add README or .gitignore files. DO NOT add these. Get a (https) link to the repository once created.
  * Navigate to /home/it5007. 
  * Run the following command: $```git remote add myrepository <https link to your git repository>```
  * To push the changes: 
     - When pushing a change to remote repository, you will be asked for your github username and password. Recently, github has replaced passwords with personal access tokens. To generate a personal access token, follow the instructions in this link: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token.
     - $```git push myrepository```
     - If you are coding in a branch use the following command instead: $```git push -u myrepository <mybranchname>```
  * For the submission, create a file with the following contents:
    - Share your private repository with the instructors and TAs. Github IDs: pkarthik88, aar809, ajayago, ukcw. Instructions on how to add collaborators: https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository.
    - Github repo link and branch name.
    - Steps to set up your application after cloning/downloading the repository (including steps to add more packages if needed)
    - How to launch your application
    - mention all features you have implemented.
