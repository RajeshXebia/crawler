# Buildit crawler

Its a maven based java application, it uses Junit and mockito for unit testing. It uses slf4j simple for logging on console.

```
Prerequisites: Java 8, Maven, Git
```

```
To build the application: mvn clean install
```

```
To run the application: mvn exec:java -Dexec.args=[Valid URL enclosed in double quotes]
  e.g. mvn exec:java -Dexec.args="http://wiprodigital.com"
  
  It will create a file output.txt in project folder that will have the name of all subdomains
```
  
```
Important Files:
  App: contains main method
  ProcessController: Validates initial input and responsible for concurrency and thread control
  Crawler: A runnable and handles most of the application logic
  Util: Handles util functions, like taking a Url connection
  CrawlerRejectedExecutionHandler: rejected execution handler
```
  

```
This application has 32 unit test cases. Most of the classes are 100% covered with both negative and positive test cases.
To run the test cases: mvn test
```  
```
To select static resources in the crawler I have to add following
  doc.select("[src]");
  
To select external urls I have to change the consition in code where I do not select external. Following is the condition that needs to be removed.
  childUrl.startsWith(rootUrl)

```
