From 1 to 16, provides steps for creation of project from git hub and maven. You can skip this and directly jump to 17
1. Create an account on https://github.com/
2. Create new repository eCommerceCommandLine
3. Download gitbash set up and install https://git-scm.com/downloads (Git bash provides command prompt to execute git command)
4. Open gitbash
5. Go to location where you want to create your project - cd d://ashwini_work//projects
6. Open your repository on github - https://github.com/ashwinitaware17/eCommerceCommandLine
7. Open code -> HTTPS -> copy path of your file
8. Execute command in git bash -  git clone https://github.com/ashwinitaware17/eCommerceCommandLine.git (This will download your remote repo from github server to your local machine). 
9. Execute ls -lrt command to verify if project is downloaded
user@LAPTOP-V7CQOK7N MINGW64 /d/ashwini_work/projects
$ ls -lrt
total 0

drwxr-xr-x 1 user 197121 0 Aug 20 10:47 eCommerceCommandLine/

10. Install maven  to your machine https://maven.apache.org/install.html
Add maven bin directory to windows environment variable - Example - C:\Program Files\apache-maven-3.6.2\bin

11. Verify if maven is installed correctly.
$ mvn --version
Apache Maven 3.6.2 (40f52333136460af0dc0d7232c0dc0bcf0d9e117; 2019-08-27T20:36:16+05:30)
Maven home: C:\Program Files\apache-maven-3.6.2
Java version: 1.8.0_231, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk1.8.0_231\jre
Default locale: en_IN, platform encoding: Cp1252
OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"

12. Go to the directory - cd d://ashwini_work//projects/eCommerceCommandLine
13. Execute command - 
mvn archetype:generate -DgroupId=com.ashwini.projects -DartifactId=eCommerceCommandLine -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
(This will create new directory with name eCommerceCommandLine and containing src files)
https://toolsqa.com/maven/create-new-maven-project/
14. Copy src files and pom.xml to outside
15. Delete newly created directory - eCommerceCommandLine
16. Now your directory structure should be like this - 
vikas@LAPTOP-V7CQOK7N MINGW64 /d/ashwini_work/projects/eCommerceCommandLine (main)
$ ls -lrt
total 3
-rw-r--r-- 1 vikas 197121  22 Aug 20 10:47 README.md
-rw-r--r-- 1 vikas 197121 331 Aug 20 10:47 design.md
-rw-r--r-- 1 vikas 197121 691 Aug 20 10:57 pom.xml
drwxr-xr-x 1 vikas 197121   0 Aug 20 10:57 src/

17. If you have not followed steps from 1 to 16, download project zip from https://github.com/ashwinitaware17/eCommerceCommandLine
Unzip it and open it in eclipse.
18. 
