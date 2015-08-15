solr-war
========

Solr WAR with logging libraries. This was originally a fork of https://github.com/finn-no/solr-war. 

Usage
-----

The binaries of this solr package are uploaded to bintray (see https://bintray.com/paulwellnerbou/maven/solr-war/1.0-solr-4.7.2-log4j2/),
so you can directly reference them in your pom.xml or build.gradle.

For Gradle:

```
	repositories {
        maven {
            url  "http://dl.bintray.com/paulwellnerbou/maven"
        }
    }
```

For Maven:

```
<repositories>
	<repository>
	  <snapshots>
         <enabled>false</enabled>
	  </snapshots>
	  <id>bintray-paulwellnerbou-maven</id>
	  <name>bintray</name>
	  <url>http://dl.bintray.com/paulwellnerbou/maven</url>
	</repository>
</repositories>
```

Building
--------

    ./gradlew clean build

The resulting WAR is in build/libs/.

Deploying artifact in your own maven repository
--------

The build.gradle uses gradle's publishing plugin ([http://www.gradle.org/docs/current/userguide/publishing_maven.html]). You will have to give the url
and credentials for your repository.

    ./gradlew publish -Prepo="http://nexus.example.com:8081/nexus/content/repositories/repo-name" -PpublishUser=user -PpublishPassword=password

Uploading to bintray
----

    gradle bintrayUpload -PpublishUser=<USER> -PpublishKey=<KEY>
