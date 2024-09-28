---
title: "Java 10 Time Based Release Versioning"
date: "2020-07-22"
categories: 
  - "java-10"
---

Java 10 has introduced time based release versioning. In this article, I will be explaining this feature in detail.

## Before Java 10

Before Java 10, Java did not have a time based release. Instead, Java release was driven by features. So, if there was some delay in developing the features, the Java release also would be delayed. Java 10 time based release versioning gets rid of this issue by guaranteeing a Java release every 6 months.

There are two main aspects to time based release versioning as follows:

## Feature Release

Feature releases occur every 6 months. All those features that are ready will be part of the release. The features that are not ready will be part of the next release. Support for these releases last only for 6 months, that is until the next release. The current version of Java is Java 14. It was released in March 2020 and it is a feature release.

## Long Term Release (LTS)

Long term releases occur once in every three years. Support for such release would be for 3 years. Java 11 is the current LTS version of Java. It was released in September 2020

## Update Release

Update releases occur every quarter. Update releases are strictly limited to bug fixes. Each feature release has two update releases.

## Conclusion

So, in this article, we understood Java 10's time based release versioning model. We understood what is a feature release, an LTS and Update release and the differences between them.
