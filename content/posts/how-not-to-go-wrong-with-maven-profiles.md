---
title: "How not go wrong with Maven Profiles"
draft: false
---

While [maven's build profiles](https://maven.apache.org/guides/introduction/introduction-to-profiles.html) make life easy to deploy in different environments,
I had the misfortune of configuring it wrong today. 

I had a `my-artifactory` profile set up in `settings.xml` of the build agent with the credentials required to upload an asset. 
Also set up the central repo there to point to our instance of nexus. I had also set `my-artifactory` to be the default profile. 
This worked quite fine when reading and writing to our nexus. 

I had another repo that did a `mvn deploy -Pgithub`. This repo had the distributionManagement set in it's pom.xml file, 
where a profile for github and my-artifactory were defined. 
Recently `mvn deploy -Pmy-artifactory was added and that's when things started going wrong. 

Now as settings.xml sets `my-artifactory` to be active by default, my pom profile `my-artifactory` and `github` along with setting.xml's `my-artifactory` had become active.
And now, instead of deploying to github it started deploying to the distributionManagement set in pom's `my-artifactory`. 
Ah, I should have seen this coming. 

Well, it was fixed by changing the progile used in settings.xml! Lesson learnt.

I also learnt that using this can help you figure out what active profiles are applied:
```
mvn help:active-profiles -Pgithub
```

And this can help you figure out the effective pom for the profile applied
```
mvn help:effective-pom -Pgithub
```
