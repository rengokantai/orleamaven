####orleamaven
#####3
######3  
```
name,description,url,licenses>license>name+comment,organization>name+url, developers>developer>name+email
```
######4 custom:
```
build>sourceDirectory+directory
```
######5 pom inheritance

######6 package
```
mvn package
```
If a profile assigned, use
```
mvn -Pprofname package
```
use
```
mvn clean
```
to delete generated package  

set a var in environment path:  
PACKAGE_ENV = PROD
```
<activation>
    <property>
        <name>env.PACKAGE_ENV</name>
        <value>PROD</value>
    </property>
</activation>
```