# Cloudhub 2 Deployment Testing with Maven
Testing of deployment via Maven to demonstrate updating Mule application without changing the Mule runtime verison.
## Deploy initial version - Runtime 4.9.2
### 1. Updte POM file
- Set runtime property in POM file to 4.9.2
### 2. Deploy applicaiton to Exchange
    mvn clean deploy
### 3. Deploy to Cloudhub
    mvn deploy -DmuleDeploy
### 4. Test Application
    curl --localtion "https://<application url>/hello

    Hello Capilano!
### Check Version of Runtime 
- Check that version is set to 4.9.2 in Runtime Manager 
## Deploy updated version
### 1. Update POM File
- Set runtime property in POM file to 4.9
- Change Set Payload in Mule flow to validate application change, e.g. add suffix " - new version"
### 2. Deploy applicaiton to Exchange
    mvn clean deploy
### 3. Deploy to Cloudhub
    mvn deploy -DmuleDeploy
### 4. Test Application
    curl --localtion "https://<application url>/hello

    Hello Capilano! - new version
### Check Version of Runtime 
- Check that version is still set to 4.9.2 in Runtime Manager 
