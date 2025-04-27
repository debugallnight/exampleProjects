# IBM BAMOE 9 project with SpringBoot 3

## Prerequisite
This is IBM BAMOE 9 example project. 

For more information on this, please refer to the followings:  

https://www.ibm.com/support/pages/ibm-business-automation-manager-open-editions-92-download-document

https://quay.io/organization/bamoe  

https://www.ibm.com/docs/en/ibamoe/9.2.x?topic=scenarios-decisions-rules-services-spring-boot

https://github.com/blulas/bamoe-maven#


## Build and Run
Assuming you have resolved the maven repository, please run the following:  

- JDK 17  
- Maven 3.8x (either 3.8.7 and 3.8.4) :  Unfortunately you can't build it as it is because the maven dependencies are no longer provided in Maven central.  Please see above references


```
mvn -U clean install
```

And 
```
java -Dserver.port=9090 -jar target/demo.jar 
```

## Test out the Insurance dmn

Using postman or any api client
```
POST http://localhost:9090/Insurance
{
    "Age": 24,
    "had previous incidents": false
}
```
And response will be  
```
200 OK
{
    "had previous incidents": false,
    "Insurance Total Price": 2000,
    "Age": 24
}
```