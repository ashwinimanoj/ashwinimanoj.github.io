---
title: "Misadventures with Maven Build Profiles: A Hard Lesson Learned"
date: 2021-11-26T17:25:53+05:30
draft: false
tags: ['maven']
---

Maven's build profiles are a powerful tool for managing deployments across different environments. However, as I found out today, they can lead to unexpected behavior if not configured properly.

## The Setup

I had a profile `my-artifactory` configured in the settings.xml of my build agent, complete with the credentials required to upload artifacts. I also set the central repository to point to my organization's internal Nexus instance. I has also set `my-artifactory` to be the default profile.

This setup worked perfectly for reading from and writing to the internal Nexus repository.

## Where It Went Wrong

Things started getting tricky when I needed to deploy to another repository (managed exclusively by another team) that used `github` as the profile. 

`mvn deploy -Pgithub`

This project’s pom.xml included distributionManagement settings and defined profiles for both `github` and `my-artifactory`. This was when things started to unravel.

## Where It All Went Wrong

Since the `settings.xml` made `my-artifactory` the default active profile, both `my-artifactory` and `github` profiles from the pom.xml became active when I ran the deployment command. As a result, instead of deploying to GitHub as expected, Maven began deploying to the distributionManagement target specified under the `my-artifactory` profile in the pom.xml.

## The Fix

The issue was resolved by updating the profile configuration in settings.xml to avoid auto-activating my-artifactory unless explicitly called. This ensured that profiles were applied only when needed, no more surprises from overlapping configurations.

Lesson learned: Profiles from settings.xml and pom.xml can interact in unexpected ways, so always be cautious!

## Helpful Maven Commands

hese two Maven commands came in handy while troubleshooting:

### Check active profiles

This command shows the active profiles during a build:

`mvn help:active-profiles -Pgithub`

### View the effective POM

This command outputs the effective POM after applying the profiles:

`mvn help:effective-pom -Pgithub`












