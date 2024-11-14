# The importance of Maven

- We see that compiling and then running Java can be a bit tedious, even when encapsulated in a shell script.
- Maven helps us organize the entire lifecycle of our project thanks to its predefined **lifecycles**.
- We don't have a base structure for our project since we're putting everything into the *src* folder. 
- Maven provides a fixed structure for source code and for any unit or automated test we create.
- With the current structure, we can't easily add dependencies or version our project with Git for collaborative work.
- Maven makes it very easy to add dependencies through the *pom.xml* file and access dependencies hosted in the Maven respository.

# Maven

- It is a software tool that manages a Java project. 
- It simplifies the installation of dependencies and downloads them from a centralized repository.
- It provides a predefined structure for a Java project.

## Structure of a Java project

![Structure of a Java Project](/5%20Maven/Estructura%20de%20un%20proyecto%20de%20Maven.png)

## Project Object Model (POM) File

- Commonly known as the POM.
- It is an XML-formatted file.
- Used to specify project configurations.
- Its most common use is to list dependencies and plugins that will be used in the project. 
- Do not confuse with the *Page Object Model* (an automation desing pattern), which is also abrreviated as POM.

## Maven Wrapper

- The Maven Wrapper is a set of files installed in the project to ensure a common Maven version for all team members.
- Additionally, the wrapper provides versions for all operating systems (*.sh* for Linux/macOS and *.bat* for Windows).
- The Maven Wrapper is installed only by the person who creates the project, and all others use the wrapper when cloning the project. 

### Installation

- To install the Maven Wrapper, navigate to the root of the project in the terminal and enter the following command: 

```bash
    mvn wrapper
```

- Intalling the wrapper generates the *.mvn/wrapper* directory, along with the *mvnw* and *mvnw.cmd* files.
- The *mvnw* files are that will help us execute Maven commands using the wrapper.
- From now on, we will use the *wrapper* to run Maven commands.

# Running a Maven Project

## Get the Path of the Main Class

1. Navigate to the class containing your *main* method. 
2. Right-click on the class name.
3. Select *Copy/Paste Special*.
4. Choose *Copy Reference*. 

## Add the Path to *pom.xml*.

1. Open the *pom.xml* file. 
2. Locate the *\<properties\>* tag.
3. Create the tag *exec.MainClass* and paste de copied reference from the previous step. 
4. Finally, click the *Refresh* button in IntelliJ.

## Run the Project 

- Navigate to the root of the project and use the following commands: 

*To run only*:
``` bash
    ./mvnw exec:java
```

*To compile and run*:
``` bash
    ./mvnw compile exec:java
```