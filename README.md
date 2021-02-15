
# Spring Boot application for adding and viewing person data

## Prerequisites
    1. Have JDK 11 installed in your machine and set JAVA_HOME path (in-memory database JSONDB is depending on JDK 11)
    
    2. Have Maven installed in your machine and verify Maven commands are working in CLI
    
    3. Have Docker installed in your machine and ensure Docker is running and you can execute Docker CLI commands

## Steps to setup the application and run

#### Clone the application code to your local directory
    https://github.com/raaki274/personclient.git

#### Create directory for saving collections into JSONDB an in-memory database
    1. Go to your home path $HOME in Linux and Mac and %HOMEPATH% in Windows machines
    
    2. Create a directory with name "jsondb"
    
    3. Note: JSONDB components used in the application will store the JSON collections under this location.
    
#### Build packaging and running the application locally
    1. Go to the root/parent directory of the application codebase where the pom.xml is available inside your GIT clone directory
    
    2. Run the following command to build-package your application
       > mvn package
       
    3. Once the build is successful, run the following Java command to run the application
       > java -jar ./target/personclient-0.0.1-SNAPSHOT.jar
       
    4. The web app will start running at - http://localhost:8060, check if it is started and running successfully
    
    5. Use any modern browsers (like Chrome) with latest updates to test the application using the URL
       http://localhost:8060/personclient/
    
    5. We are going to Dockerize the application in the next section, you can now stop the application by hitting Ctrl + C
    
#### Dockerizing the application
    1. Run the below command from the application's parent directory for building Docker image
        > docker build -t personclient-app .
    
    2. Run the below command for running the application image inside Docker container
        > docker run -p 8060:8060 personclient-app
    
    3. Application image will start and run at port number 8080 inside Docker container
    
    4. Use any modern browsers (like Chrome) with latest updates to test the application using the URL
       http://localhost:8060/personclient/

### Testing inputs
    Application has three main features, i. Add a person through form filling (First name is mandatory here), 
    ii. Upload a text file will have multiple person records, file must have totally five fields with comma seperated fields 
    and can have any number of records, and iii. View the person by person ID (which is First name) and view all records 
    in the Person collection. Find below the sample inputs,
    
   #### Sample input for form filling
        Fist name:        John
        Last name:        Kelleys
        Age:              36
        Favourite colour: White
   
   #### Sample flat file (.txt) record format
        #first_name,surname,age,nationality,favourite_colour
        John,Keynes,29,British,red
        Sarah,Robinson,54,,blue
        Rky,Balki,35,Globe,White
        MKaruna,Mvl,96,TN,Yellow
   
        Note: The field names hashed out above must be removed when uploading the file, make it as siple .txt file
   
   #### Find person input
        First name: John


### Thanks for your time spent exploring this, cheers!!
