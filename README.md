# Spring Boot

## lombok
**what if `lombok` is not working**

Make sure to both dependencies added
  ```
  compileOnly 'org.projectlombok:lombok'
  annotationProcessor 'org.projectlombok:lombok'
  ```
## Mapstruct
**mapstruct is not working on all fields**

It happens when mapstruct used along with lombok. Solution is to make sure we have `lombok` annotationProcessor should come first and then `mapstruct`. It looks silly, but it works.

  ```
  dependencies {
    implementation 'org.mapstruct:mapstruct:1.5.5.Final'
    compileOnly 'org.projectlombok:lombok'
    annotationProcessor 'org.projectlombok:lombok'
	  annotationProcessor 'org.mapstruct:mapstruct-processor:1.5.5.Final'
    testImplementation 'org.mockito:mockito-junit-jupiter'
  }
  ```
