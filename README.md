# Qodana JVM Community

**Qodana** is a code quality monitoring platform that allows you to evaluate the integrity of code you own, contract, or purchase. It brings into your CI/CD pipelines all the smart features you love in the JetBrains IDEs plus continues adding project-level checks like clone detection and license audit.

Qodana JVM Community is based on IntelliJ IDEA Community and provides static analysis for Java and Kotlin for Server Side projects.

**Table of Contents**

<!-- toc -->

- [Qodana JVM Community](#qodana-jvm-community)
  - [Usage](#usage)
  - [Output Results](#output-results)
  - [License Summary](#license-summary)

<!-- tocstop -->


## Usage

* `project-dir` - Project folder to inspect (default `${{ github.workspace }}`)
* `results-dir` - Save results to folder (default `${{ github.workspace }}/qodana`)
* `cache-dir` - Save cache to folder (default `/home/runner/work/_temp/_github_home/qodana-cache`)
* `inspected-dir` - Directory to be inspected. If not specified, the whole project is inspected by default
* `baseline` - Run in baseline mode. Provide the path to an exisitng SARIF report to be used in the baseline state calculation
* `baseline-include-absent` - Include in the output report the results from the baseline run that are absent in the current run (default `false`)
* `fail-threshold` - Set the number of problems that will serve as a quality gate. If this number is reached, the inspection run is terminated
* `save-html-report` - Generate HTML report (default `false`)
* `profile-name` - Name of a profile defined in project
* `profile-path` - Absolute path to the profile file
* `gradle-settings-path` - Provide path to gradle.properties file (for example: `/your/custom/path/gradle.properties`)
* `additional-volumes` - Additional volumes to mount to qodana docker image
* `additional-env-variables` - Additional environment variables to pass to qodana docker image

```yaml
- uses: JetBrains/qodana-jvm-community-action@v1.1.1
```

All action's inputs are optional. 
```yaml
- uses: JetBrains/qodana-jvm-community-action@v1.1.1
  with:
      fail-threshold: 10
```

## Output Results

An example of the Qodana command-line summary output:
```
---- Qodana - Code Inspection ----

2 problem(s) with Critical severity
 - Category(ies): General

1 problem(s) with Moderate severity
 - Category(ies): Code style

---- Problems reported: 3 ----
```
 
## License Summary

By using Qodana, you agree to the [JetBrains privacy policy](https://www.jetbrains.com/company/privacy.html).
