## T4G JUnit Testing Framework

The T4G team (An Nguyen, Jeremy Zhang, Margaret Lanphere) has developed a testing framework to execute JUnit tests for Java assignments. We will utilize Github classroom to distribute students starter code along with using Github as the platform to execute tests. This webpage will demonstrate the significance of each portion of the framework and a tutorial regarding to setup.

### Breakdown
Every assignment will utilize two repositories to provide the starter files and testing framework. Please use those repositories as a base for working on your next upcoming assignment.
- [junit-demo-starter](https://github.com/PisanA/junit-demo-starter) ("starter repository"): This repository contains all the files provided to students as a starter code. The beauty of this layout allows all Java files to be distributed at root level. Students do not need to dig into folders to find their needed files.
  - [.github/workflows/testreport.yml](https://github.com/PisanA/junit-demo-starter/blob/master/.github/workflows/testreport.yml): Updating the `parent_repo` environment variable sets the location where the JUnit tests are located.
- [junit-demo-tests](https://github.com/PisanA/junit-demo-tests) ("tests repository"): This repository contains the testing framework toe execute Junit tests on student repositories. 
  - [src/main/java](https://github.com/PisanA/junit-demo-tests/tree/master/src/main/java): Where solution files are held. Can help with developing the assignment to determine if the assignment solution will pass the given JUnit tests.
  - [src/test/java](https://github.com/PisanA/junit-demo-tests/tree/master/src/test/java): Contains the JUnit test that will run on the assignment. Please name all your JUnit tests to end with `Test` in the class names. Such as `MainTest.java`, or `StudentTest.java`, etc.
    - [MainTest.java](https://github.com/PisanA/junit-demo-tests/blob/master/src/test/java/MainTest.java): Please see this annotated file to learn more about writing JUnit tests to capture scanner input, printing, and more.

### Token setup
Because we are working with private testing repositories, Github actions will need to clone the tests repository to execute the tests. As such we need to save our Github access token into a `TOKEN` organization secret. This is a one time setup and will only be required each time the token expires.
1. Create a [personal access token](https://github.com/settings/tokens) with the scope **repo** for full control of private repositories.
2. Visit the [orginzation settings](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-an-organization), secrets page.
3. Create a new orgization secret with the name `TOKEN` and the value copied from step 1. Repository access is Private repositories.

