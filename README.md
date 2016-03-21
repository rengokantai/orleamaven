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

#####5
######2 lifecycle
default,clean site
```
mvn help:describe -Dcmd=clean
mvn help:describe -Dcmd=deploy
```
######3 important phases

compile, test-compile, test, package,install deploy

######4. plugins and goals
```
mvn compiler:compile
mvn help:describe -Dplugin=compiler
```

get compiler help goal's detail info
```
mvn compiler:help -Ddetail=true -Dgoal=compile
```

######5
list all props of compiler:compile
```
mvn help:describe -Dcmd=compiler:compile -Ddetail
```
Use it.
```
mvn compiler:compile -Dmaven.compiler.verbose=true
```
remove cached file:
```
git rm -r . --cached
```

######6 custom plugin
```
mvn archetype:create -DgroupId=me.yd -DartifactId=yd -DarchetypeArtifactId=maven-archetype-mojo -DarchetypeGroupId=org.apache.maven.archetypes
```
this will create a new foler named artifactId.

go to this repo, and
```
mvn install
```
to install this pulgin to local repo.  

If other repo want to install, 
```
mvn gpid:artid:touch
```
######7 continued.
Not finish.

##### cp6
######2 clean

######3 jar plugin
using package phase:
```
mvn package
```
or
```
mvn jar:jar -Djar.finalName=test -Djar.forceCreation=true
```

######4 javadoc
```
mvn javadoc:javadoc -Dheader=me.yd -Dfooter=YD
```
######5 deploy
```
mvn deploy
```