---
title: "Setting up a development environment with Ubuntu & intelliJ"
category: basics

---

# Setup Java workspace and dependencies
1. Install IntelliJ using instructions from the included Install-Linux-tar.txt
2. Install JDK & JRE with command: `sudo apt-get install default-jre default-jdk`
3. Open IntelliJ and click configure > project defaults > project structure
4. On project structure settings, create a new "Project SDK" and choose your JDK folder (should be one of the folders /usr/lib/jvm)
5. Clone the bitquest repository
6. Back on the welcome screen, choose open, select the folder where you cloned bitquest
7. Run the setupWorkspace task to download dependencies. You can use the IntelliJ gradle tool to do this. in view > tool windows > gradle and look for the other > setupWorkspace task in the gradle tool window. 
8. Run the shadowJar task to make the final JAR plugin. You should see a bitquest-2.0-all.jar in the build/libs folder

# Run the compiled Plugin in Minecraft
1. Install Docker and Docker compose
2. After running the shadowJar gradle task (see above) open a terminal and run `docker-compose up` to create a container with a test version of BitQuest. The container needs to be built just once, subsequent times will start much, much faster.
3. Connect to your local server in Minecraft by adding server `localhost`