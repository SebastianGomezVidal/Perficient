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
- postman
- newman
- jenkins

## HOW TO RUN THIS POGRAM
1. Download The Challenge Folder into a location inside your computer.
2. Open Jenkins and Configure a new Job.
3. Go into your newly created job and add the follwoing lines under build:

    ```python
        cd "Path to where your downloaded challenge 1 folder is located at"
        "C:\Users\youruser\AppData\Roaming\npm\newman" run Swagger_Petstore.postman_collection.json -e QA_Testing  postman_environment.json -g workspace.postman_globals.json
        "C:\Users\youruser\AppData\Roaming\npm\newman" run Swagger_Petstore.postman_collection.json -e QA_Testing.postman_environment.json -g workspace.postman_globals.json -r htmlextra
    ```
4. In order to see a proper rendering of postman report lines go to you jenkins folder and open.
with a text editor your jenkins.xml, at line 39 before the word -jar add D.encoding=UTF8.
5. Finally run your build.