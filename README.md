# GitHub Open Authentication addon
This addon allows users to sign in eXo Platform using their GitHub accounts.

# 1. Github web new app settings
![git_dev1](https://user-images.githubusercontent.com/1423939/43135120-98bdc6c0-8f44-11e8-9662-c5fd8b96c8a7.PNG)


![git_dev2](https://user-images.githubusercontent.com/1423939/43135121-98e55c76-8f44-11e8-8657-11a3738eca42.PNG)



# 2. Upload local.json file to this docker command

   a)inside container server: 
   docker exec -it 049f2e3739c1 bash
   
   b)copy file from desktop to server:   
   docker cp  "C:\Users\Istiaq Khan\Desktop\local.json" 049f2e3739c1:/opt/exo/addons/local.json
   
   local.json file code below
   http://www.mediafire.com/file/ddmnpm3i3o0k808/local.json/file
   
    [
       {
         "id": "github-oauth",

         "version": "1.0.x-SNAPSHOT",

         "name": "My Github-oauth",

         "description": "Example of my add-on",

         "downloadUrl": "file:///tmp/github-oauth-1.0.x-SNAPSHOT.zip",

         "vendor": "eXo platform",

         "license": "LGPLv3",

         "supportedDistributions": ["community","enterprise"],

         "supportedApplicationServers": ["tomcat","jboss"]
       }
    ]
    
    

# 3. upload "github-oauth-1.0.x-SNAPSHOT.zip"  file to server "tmp" folder
   
![addon_install_cmd1](https://user-images.githubusercontent.com/1423939/43135040-57898e32-8f44-11e8-8d1a-07ba562a13c8.PNG)



# 4. install addon go to /opt/exo
   then enter this command
   ./addon install github-oauth:1.0.x-SNAPSHOT
   
   ![addon_install_cmd3](https://user-images.githubusercontent.com/1423939/43135411-9ea7a064-8f45-11e8-85c5-e2eb6b55e7eb.PNG)
   
   
# 5. copy "exo.properties" file from  server to desktop :  
   docker cp   049f2e3739c1:/etc/exo/exo.properties "C:\Users\Istiaq Khan\Desktop\exo.properties"
   
   add this lines of code & again upload it to server
   
   
   exo.oauth.github.enabled=true    
   exo.oauth.github.clientId=87cdc0996b3b08e6846e
   exo.oauth.github.clientSecret=d1cd2885d3efe729d1e9451c3adebd14db5673c9
   
   sample exo.properties file look like this
   http://www.mediafire.com/file/m2dr1x8i8f4bbca/exo.properties/file


# 6. restart exo server

# 7. compiled code sample
     http://www.mediafire.com/file/oyoxnrhcyd1rx3x/github_oauth_working.zip/file








