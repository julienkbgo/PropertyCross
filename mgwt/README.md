# mgwt PropertyCross

Visit the [mgwt page](http://propertycross.com/mgwt/) on the PropertyCross website for screenshots and code sharing metrics.

## Introduction

[Google Web Toolkit](https://developers.google.com/web-toolkit/)  (GWT) is an open source set of tools that allows developers to create web apps in Java. GWT compiles Java into an optimised JavaScript application. GWT is most often used for large-scale web applications, with the strongly typed nature of Java making it easier to maintain a large codebase.

[mgwt](http://www.m-gwt.com/) is an open source mobile widget framework build using GWT. mgwt provides a number of UI widgets, CSS styles and a PhoneGap API which make it easier to develop native-like applications using GWT.

The mgwt PropertyCross implementation is structured using the popular GWT ['Activities and Places'](https://developers.google.com/web-toolkit/doc/latest/DevGuideMvpActivitiesAndPlaces) pattern.

##Building the Application

* To build this project you'll first need [Maven](http://maven.apache.org/) installed.
* The tests for this project depend on a jar not found in maven central so you'll need to manually install it first by running -
`mgwt> mvn install:install-file -Dfile=lib/easy-gwt-mock.jar -DgroupId=com.propertycross.mgwt -DartifactId=easy-gwt-mock -Dversion=e15d9a93fd52 -Dpackaging=jar`
* Then run -
`mgwt> mvn clean install`

### Packaging Instructions

This project uses the [PhoneGap Build Maven Plugin](http://chrisprice.github.io/phonegap-build/phonegap-build-maven-plugin/). In order to package the project you need to active the build profile - `mgwt> mvn clean install -P phonegap-build`

### Developing with Eclipse

* Ensure you have the [Eclipse plugin](https://developers.google.com/web-toolkit/download) installed
* Create an 'empty' project pointing it at the directory with the mgwt code
* Configure => Convert to Maven Project ...
* Google => Web Toolkit Settings ... - Check the "Use Google Web Toolkit" checkbox

##Application Structure

 + `\lib` - contains a mocking framework for testing
 + `\src\main\java\` - the Java code for this app.
 + `\src\main\phonegap-build` - contains the PhoneGap build config.xml file.
 + `\src\main\web-app` - contains the HTML file that hosts the mgwt app, together with the CSS styling.
 + `\src\viewModels` - The view models that implement the PropertyCross logic.
 + `pom.xml` - The Maven POM file used to automate PhoneGap Build.
 + `stats-config.json` - Used by the PropertyCross build in order to compute code sharing metrics.

