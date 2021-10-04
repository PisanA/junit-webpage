## T4G JUnit Testing Framework

The T4G team (An Nguyen, Jeremy Zhang, Margaret Lanphere, Ed Adshire) has developed a testing framework to execute JUnit tests for Java assignments. We will utilize Github classroom to distribute students starter code along with using Github as the platform to execute tests. This webpage will demonstrate the significance of each portion of the framework and a tutorial regarding to setup.

### Breakdown
Every assignment will utilize two repositories to provide the starter files and testing framework. Please use those repositories as a base for working on your next upcoming assignment.
- [junit-demo-starter](https://github.com/PisanA/junit-demo-starter) (**Public** "starter repository"): This repository contains all the files provided to students as a starter code. The beauty of this layout allows all Java files to be distributed at root level. Students do not need to dig into folders to find their needed files.
  - [.github/workflows/testreport.yml](https://github.com/PisanA/junit-demo-starter/blob/master/.github/workflows/testreport.yml): Updating the `parent_repo` environment variable sets the location where the JUnit tests are located.
- [junit-demo-tests](https://github.com/PisanA/junit-demo-tests) (**Private** "tests repository"): This repository contains the testing framework toe execute Junit tests on student repositories. 
  - [src/main/java](https://github.com/PisanA/junit-demo-tests/tree/master/src/main/java): Where solution files are held. Can help with developing the assignment to determine if the assignment solution will pass the given JUnit tests.
  - [src/test/java](https://github.com/PisanA/junit-demo-tests/tree/master/src/test/java): Contains the JUnit test that will run on the assignment. Please name all your JUnit tests to end with `Test` in the class names. Such as `MainTest.java`, or `StudentTest.java`, etc.
    - [MainTest.java](https://github.com/PisanA/junit-demo-tests/blob/master/src/test/java/MainTest.java): Please see this annotated file to learn more about writing JUnit tests to capture scanner input, printing, and more.

### Token setup
Because we are working with private testing repositories, Github actions will need to clone the tests repository to execute the tests. As such we need to save our Github access token into a `TOKEN` organization secret. This is a one time setup and will only be required each time the token expires.
1. Create a [personal access token](https://github.com/settings/tokens) with the scope **repo** for full control of private repositories.
2. Visit the [orginzation settings](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-an-organization), secrets page.
3. Create a new orgization secret with the name `TOKEN` and the value copied from step 1. Repository access is Private repositories.

### Github Classroom Setup
Once the setup process is complete, we would want to start distributing the assignments to students. We will use Github classroom as a method to distribute starter code. 
- Create an assignment on [Github Classroom](https://classroom.github.com/). Students do not need admin access to their repository.
- The starter repository will be pointed at the public starter repository as mentioned in the breakdown above.

### Checking Feedback
Each commit generates a workflow that contains all feedback. The feedback can be found in Actions ![image](https://user-images.githubusercontent.com/54456351/135796086-f489bbbb-76c9-401e-80ae-94fe5e799482.png)

#### Actions
Once you're ready to test them, edit the template files and they will be tested using GitHub Actions. 

You'll get 3 kinds of feedback:

1. Checkstyle feedback on code style mistakes in the Google Java Style
2. Misspell report on detected misspellings in your code and comments
3. Unit tests by JUnit, testing if your functions are performing as expected

This is the action page: <br>
![image](https://user-images.githubusercontent.com/54456351/119814197-fc2f4a80-be9e-11eb-86ad-00f6c5b5d238.png) <br>
The workflow are your commissions from newest to latest. <br>
Click on the one that you want to see the report. <br><br>
The yellow circle means the workflow is in progress, and you have to wait until it changes the status.<br>
![image](https://user-images.githubusercontent.com/54456351/119813577-51b72780-be9e-11eb-8449-c84e2850f125.png) <br><br>

The red circle means the workflow is failed. You can see your details in the reports inside it.<br>
![image](https://user-images.githubusercontent.com/54456351/119813655-65628e00-be9e-11eb-8c27-8b42a9e71304.png) <br><br>

The green circle means the workflow is passed, but you should check the reports to check your code style is good enough and any misspell occurs.<br>
![image](https://user-images.githubusercontent.com/54456351/119813818-95119600-be9e-11eb-82e5-d247541062cb.png) <br><br>

#### CheckStyle
Click on the left sidebar on "checkstyle" to view the Checkstyle report. <br>
![image](https://user-images.githubusercontent.com/54456351/129306692-6959b6b7-308c-452e-aa44-64fd21ee95de.png) <br>
If you have any compilation errors, CheckStyle report will not be generated. Please view the JUnit Report and debug all errors first.

##### For more detatils on the CheckStyle warning, you can view this website: <a href="https://pisana.github.io/checkstyle-webpage/">checkstyle-webpage</a>
The website contains the most common Checkstyle warnings with detailed examples. 
For more information about other warnings, please view <a href="https://checkstyle.sourceforge.io/styleguides/google-java-style-20180523/javaguide.html">Google Java Style Guide</a> <br>

<br><br>
#### Misspell
Click "misspell" to view found mispellings.
![image](https://user-images.githubusercontent.com/54456351/129307048-27f9297e-b80c-4e16-b430-9923917aa2a3.png)

#### JUnit Report
Scroll to the bottom and download the artifact to view your detailed test report. <br>
Click "Compile-Run-Report" to download the report. 
It is a zipped folder that will contain a test report and/or a build text file.  

![image](https://user-images.githubusercontent.com/54456351/129307490-b6f27859-9ea2-4b68-8712-9b211b827322.png) <br>

You will get the following information in report.txt:
1. Compilation status to check for compilation errors
2. Total score of the your current work
3. Failed/Passed test cases with hints

#### What my report.txt is very short with no score? 
This means that there was an error when trying to run tests on your program. Your report.txt file may show some error messages 
that were produced when trying to run our tests. Check to see if your code compiles in your IDE or on the commandline before reuploading.
For more clues to the issue, look in the build.txt file in the zipped folder. 

#### What if there's no error messages in my report.txt?
Look in the build.txt file to see build and compilation errors. Some programs can compile but fail to run in unit testing. 
It may be failing due to tests being run on parts of the program that you have not implemented yet. 
