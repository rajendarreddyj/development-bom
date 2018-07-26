# development-pom
[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://raw.githubusercontent.com/rajendarreddyj/development-pom/master/LICENSE)
parent pom for all projects


This repository has parent pom for all projects for this organization.

To Install pom.xml to maven-repo

`mvn install:install-file -DgroupId=com.rajendarreddyj -DartifactId=development-pom -Dversion=1.0 -Dpackaging=pom -Dfile=/apps/sourceCode/git/rajendarreddyj/development-pom/pom.xml -DlocalRepositoryPath=/apps/sourceCode/git/rajendarreddyj/maven-repo`

This mojo performs byte code analysis to determine missing or unused dependencies. This goal is meant to be launched from the command line. It will fork the build and execute test-compile so there are class files to analyze. If you want to bind analyze in your pom, use the dependency:analyze-only mojo instead.

`mvn dependency:analyze`

Below for just detecting projects that override the dependencyManagement directly. Set ignoreDirect to false to detect these otherwise normal conditions.

`mvn dependency:analyze-dep-mgt`

This mojo is used to view the dependency hierarchy of the project currently being built. It will output the resolved tree of dependencies that the Maven build process actually uses.

`mvn dependency:tree`

This mojo will set New version for parent pom.

`mvn versions:set -DnewVersion=1.0`

This mojo will update version in child modules.

`mvn versions:update-child-modules`

This mojo displays all dependencies that have newer versions available.
 
`mvn versions:display-dependency-updates`

This mojo displays all plugins that have newer versions available.

`mvn versions:display-plugin-updates`

This mojo displays properties that are linked to artifact versions and have updates available.

`mvn versions:display-property-updates`

This mojo will update your dependencies to the latest available versions

`mvn versions:use-latest-versions`

This mojo will update your dependecies specified in property values

`mvn versions:update-properties`

To create PMD report

`mvn -Dmaven.test.failure.ignore=true pmd:pmd`

To open findbugs gui

`mvn -Dmaven.test.failure.ignore=true findbugs:gui`

To create findbugs report

`mvn -Dmaven.test.failure.ignore=true findbugs:findbugs` 

To run sonarqube analysis

`mvn -Dmaven.test.failure.ignore=true clean verify sonar:sonar`

To generate checkstyle report as standalone

`mvn -Dmaven.test.failure.ignore=true checkstyle:checkstyle`

To run cobertura code coverage analysis to report to coveralls -- requires coveralls token

`mvn -Dmaven.test.failure.ignore=true clean test cobertura:cobertura coveralls:report`

To create a maven wrapper go in the main folder of the project and run this command:

`mvn -N io.takari:maven:wrapper`

To create a maven wrapper with specific the version of Maven:

`mvn -N io.takari:maven:wrapper -Dmaven=3.5.2`