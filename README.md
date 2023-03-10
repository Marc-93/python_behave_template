# Test framework documentation

## Test architecture

The framework is designed using POM (Page Object Model) as a pattern structure.

The selected code language is python (v3.9 due dependencies with some libraries used).

The test runner framework is behave.

The test scenarios are defined using Gherkin due it is designed to facilitate the understanding of test scenarios 
between all team members.

## Technical details:

* **config runners:** config files with test run launchers for pycharm professional.

* **Setup:** requirement file, it allows to install all the libraries to execute the test suite.
     * Clone the repository in any local path
     * Execute the following command: $ pip install -r <your_path>/requirements.txt
     * Install allure with brew: $ brew install allure

* **src:**
     * allure: folder to storage the test reports. 
     * frontend: UI test cases.
     * services: common python utils to be reused.

## Reporting tools:

* [Qase](https://app.qase.io/project/): Test management and repository tool to define all scenarios (manual and automated).
* **Allure reporter**: Tool to view the test results and logs in a pretty html report, integrated with jenkins CI/CD builds.


## Test execution
* behave -D platform=web -D headless=false -k -f allure_behave.formatter:AllureFormatter -o ./src/allure ./src/frontend/functionality
