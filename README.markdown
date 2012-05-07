#ABOUT

This repository is here as a maven reposity. 
##Publish
To publish to this maven repository, do the following

In your build.sbt file:

    publishTo := Some(Resolver.file("Github Pages", Path.userHome / "Projects" / "wml.github.com" / "maven" asFile)(Patterns(true, Resolver.mavenStyleBasePattern)))

    publishMavenStyle := true

Then do:

    mkdir ~/Projects
    cd ~/Projects
    git clone git@github.com:WML/wml.github.com.git
  
    cd <your git repository>
    git publish

Then commit:

    cd ~/Projects/wml.github.com
    git add maven/*
    git commit -m 'publish something'
    git push origin master
  
##USAGE
To get artifacts from the maven repository, add to your build.sbt file:

    resolvers += "wml-repo" at "http://wml.github.com/maven/"
