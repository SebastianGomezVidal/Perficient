## CHALLENGE
Using the following API Definition: 

https://petstore.swagger.io/#/

Create a collection with two requests:
1. Create a Pet, create tests to verify it was created successfully
2. Get a Pet, create tests to verify you're getting the expected pet
3. Place an order for the created Pet
4. Get the order created in step 3, and verify it has the expected data.
5. Automate it using newman

Hint: You will probably need to use environments to store some data that needs to be shared between requests.

Upload the solution to a repo, put in the README instructions about how to execute your code, share the solution as a response to this message :)

## THINGS YOU MIGHT NEED BEFORE STARTING
- node js
    [![Alt text](https://img.youtube.com/vi/AuCuHvgOeB/0.jpg)](https://www.youtube.com/watch?v=AuCuHvgOeB)
- postman

- newman

- newman reporter
'''
npm install -g newman-reporter-htmlextra
'''
- jenkins

## HOW TO RUN THIS POGRAM
1. Download The Challenge 1 Folder into a location inside your computer.
2. Open Jenkins and Configure a new Job.

![Alt text](pictures//new_job.png?raw=true "New Job")
3. Go into your newly created job and add the following lines under build:

    ```
        cd "Path to where your downloaded challenge 1 folder "
        "C:\Users\youruser\AppData\Roaming\npm\newman" run Swagger_Petstore.postman_collection.json -e QA_Testing  postman_environment.json -g workspace.postman_globals.json
        "C:\Users\youruser\AppData\Roaming\npm\newman" run Swagger_Petstore.postman_collection.json -e QA_Testing.postman_environment.json -g workspace.postman_globals.json -r htmlextra
    ```
![Alt text](pictures//job_config.png?raw=true "Job Config")

4. In order to see a proper rendering of postman report lines go to you jenkins folder and open with a text editor the jenkins.xml file, at line 39 before the word -jar add -Dfile.encoding=UTF8.

![Alt text](pictures//utf-8.png?raw=true "UTF-8")

5. Finally run your build.
![Alt text](pictures//built.png?raw=true "Built")

6. Go to the path of your local folder and inside the newman sub-folder with the help of a browser open the respective report.

![Alt text](pictures//report.png?raw=true "Report")



