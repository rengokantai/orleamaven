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
######7 Generating Projects
```
mvn archetype:generate
```
groupId: me.yd
artifactId: orlea


#####4
######2
pull dependency to local
```
mvn dependency:copy-dependencies
```

install junit,ctrl shift T, or tweak settings in intellij  
[Import maven dependencies automatically](http://stackoverflow.com/questions/11454822/import-maven-dependencies-in-intellij-idea)

######4
```
mvn help:effective-pom
```
change config: mvnhome/conf/

add a remote repo:
```
        <profile>
            <id>spring_remote</id>
            <repositories>
                <repository>
                    <id>spring</id>
                    <name></name>
                    <url>http://repo.spring.io/release/</url>
                </repository>
            </repositories>
        </profile>
```

######5 scope

like this:
```
<scope>test</scope>
```
will only be available in ```mvn test```  
If we change scope to `compile` then  
```
mvn -X compile
```
we can see junit.

######6 exclusions
```
exclusions>exclusion>groupId+artifactId
```