solr-war
========

Solr WAR with logging libraries. This was originally a fork of https://github.com/finn-no/solr-war. 

Building
--------

    ./gradlew clean build

The resulting WAR is in build/libs/.

Deploying artifact in your own maven repository
--------

The build.gradle uses gradle's publishing plugin ([http://www.gradle.org/docs/current/userguide/publishing_maven.html]). You will have to give the url
and credentials for your repository.

    ./gradlew publish -Prepo="http://nexus.example.com:8081/nexus/content/repositories/repo-name" -PpublishUser=user -PpublishPassword=password

