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

# Maven Lifecycles

Maven has three default lifecycles:

- *Build*: Manages the entire lifecycle for building the project. 
- *Clean*: Manages the lifecycle of cleaning up the target folder. 
- *Site*: Manages the lifecycle of creating a website with information about the project. 

## Build Lifecycle

- This manages the entire lifecycle for building a project.
- The phases range from *validate* to *deploy*.
- In programming and test automation courses, we'll only use the first three phases. 
- When we run a specific phase, Maven automatically runs all the previous phases. 

*Phases*:
- **Validate**: Validates that the Maven structure and files are correct. 
- **Compile**: Compiles all *.java* files into *.class* files. 
- **Test**: Execute our tests (located in the *java/tests* folder).

## Clean Lifecycle

- Manages the lifecycle of deleting the target folder. 
- As its name suggest, we can create customizable actions befores and after deleting the target folder. 
- We'll mostly use it to delete the target folder before recompiling the project.
- Just like the build lifecycle, if we run a phase, all the previoud ones are automatically executed.

*Phases*:
- **Pre-clean**: Runs the specified actions before the clean phase. 
- **Clean**: Deletes the target folder (compiled files).
- **Post-clean**: Rung the specified actions after the clan phase. 

## Site Lifecycle

- Manages the creation of a website with specific information about our project. 
- We'll mostly use it for generating reports.
- Just like the default lifecycle, if we run a phase, all the previous ones are automatically executed.

*Phases*:
- **Pre-site**: Runs the specified actions before the site phase.
- **Site**: Generates the files for the website with the respective documentation.
- **Post-site**: Runs the specified actions after the site phase.
- **Site-deploy**: Deploys the website created during the site phase. 


### Running a Phase of a lifecycle

*In the root of the project*:

To run a phase of a lifecycle: 
```bash
    ./mvnw <phase> --> ./mvnw clean
```

To run a phase from one lifecycle and then a phase from another lifecycle:
```bash
    ./mvnw <phase1> <phase2> --> ./mvnw clean compile
```

To run a phase from one lifecycle, then a phase from another lifecycle, and finally execute the project: 
```bash
    ./mvnw <phase1> <phase2> exec:java --> ./mvnw clean compile exec:java
```

# Passing Parameters Through the Terminal

- We can pass information from the terminal to our programs using the following at the end of our commands: 
``` bash
    ./mvnw compile exec:java -DparameterName="value"
```

- We can then read this information in our programs with: **System.getProperty("parameterName")**

Example: 

``` java
    public static void main(String[] args) {
        final var name1 = System.getProperty("name1");
        final var name2 = System.getProperty("name2");

        System.out.printf("""
                name 1: %s 
                name 2: %s
                """,convertUppercase(name1),convertUppercase(name2));
    }

    public static String convertUppercase(String name){
        return name.toUpperCase();
    }
```

# Reading Envirtonment Variables with Maven

- To read environment variables, simply use: **System.getenv("VARIABLE_NAME")**
- For example, to display the value of JAVA_HOME, use: **System.getenv("JAVA_HOME")**

# Dependencies

- Maven dependencies are external libraries created by third parties that help enrich and simplify tasks with our project.
- Some well-know dependencies include: TestNG, Selenium, Appium, etc.
- The project's dependencies are specified in the *pom.xml* file.
- By specifying dependencies, we can ensure a common version for everyone working on the project.

## Composition of a Dependency

- **groupId**: The identifier of the company/group/person that created the library.
- **artifactId**: The name of the library.
- **version**: The current version of the installed library.    
- **scope**: Specifies whether the dependency is for source doce or for tests. This is optional. 

## Installing Dependencies

1. Search for 'Maven repository' on Google.
2. Look for the name of the dependency you need. 
3. Select the latest version (avoid beta versions).
4. Make sure the 'Maven' tab is selected, then copy the code block.
5. Go to the *pom.xml* file and paste the copied block inside the *\< dependencies \>* tag.

## Where Are Dependencies Installed? 

- These are stored locally in the *.m2* folder in the user's root directory. 
- If we go to *.m2/repository* and list the files, we can se the installed dependencies. 
- The first time dependencies are installed, it will take longer because Maven first looks locally, and if the don't exist, it will download them.

# Plugins 

- Plugins are software artifacts used to execute any Maven task.
- Many plugins come by default and don't need to be installed, especially those used in lifecycles (like clean, compile, exec), but we can change their default configuration in the *pom.xml* if needed.
- If a plugin is not included by default, it must be specified in the *pom.xml*.
- Plugins are generally classified into two main types: 
    - Build: Used in the build lifecycle.
    - Reporting: Used in the site lifecycle.
- Some of the most well-know plugins include: 
    - compile (mentioned in the build lifecycle).
    - clean (mentioned in the corresponding lifecycle).
    - exec (executes code).
    - surefire (runs unit tests).

## Composition of a Plugin

- **groupId**: The identifier of the company/group/person who created the plugin. 
- **artifactId**: The name of the plugin.
- **version**: The current version of the installed plugin.
- **configuration**: Configuration options for the plugin (optional).
- **dependencies**: Dependencies that can be specified for a plugin (optional).

## Installing Plugins

- Depending on the type: 
    - Build: Inside the *build* tag in the *pom.xml*.
    - Reports: Inside the *reporting* tag in the *pom.xml*.
- Most of the time, we'll install build plugins.
- If the *plugins* tag doesn's exist, we need to create it manually.
- There is no fixed step for installing plugins, as it will depend on the plugin's documentation. 
- When installing plugins, the necessary steps for modifying the *pom.xml* will be specified at the appropriate time.