---
layout: project-index
title: Dhananjay Projects 
excerpt: "A List of Things I can boast about"
comments: true
projects:
    

    - title: "Empirical Analysis of Jenkins Pipelines"
      link: ""
      pdf: ""
      github: ""
      image: ""
      about: "Discovered patterns and trends in various repositories and their continuous integration pipelines. Analyzed groovy syntax and extracted stages, shell script commands, build invocations using different build tools."
      
    - title: "Git Repository Analyze"
      link: ""
      github: ""
      image: ""
      about: "Developed a git patch analyzer which does string and syntax level parsing to analyze and generate reports for the repositories written in java. Determines common bugs by analyzing repeated patterns in ‘patches’ to source code."

    - title: "DevOps application workflow for automatically building and analyzing software applications."
      link: "https://github.com/DhananjayGupta300/DevOps-Workflow-for-Automatically-Building-and-Analyzing-Software-Applications"
      github: "https://github.com/DhananjayGupta300/DevOps-Workflow-for-Automatically-Building-and-Analyzing-Software-Applications"
      image: "/images/ABC.gif"
      about: "This project simulates the DevOps environment from developers pushing their code to automated building, testing and analyzing of code. Our Java project simulates this process by downloading repositories from GitHub, uploading each repository to a local GitLab server, which triggers the build process and code analysis in the locally installed Jenkins server. Our Jenkins server configuration built, tested and analyzed project code using JaCoCo and Understand. Our implementation of the DevOps environment focused on Java Maven applications containing unit tests and JaCoCo support. The project is implemented in Java and built with Gradle. GitHub, GitLab, and Jenkins Java APIs are used to access GitHub.com, the local GitLab server, and the local Jenkins server from the Main.java file. The JGit Java library is used for git repository management within our project. These dependencies are documented in the build.gradle file. We were able to successfully perform a stress test of our Java application by pushing 54 Github projects through our DevOps simulation without error. From the execution of our application to the last job being built in Jenkins, it took approximately 20 minutes. 25 out of the 54 applications built successfully some of which had included JaCoCo code coverage, unit testing results, and produced Understand code analysis. The remaining 29 failed for a variety of reasons such as missing pom.xml build file, failed unit tests, missing plugins, etc. Please note that our application only pulls the first 100 repository results of our GitHub.com query due to GitHub API limitations. Despite this GitHub API limitation, during our stress test we found that 100 repositories was enough to produce a sufficient number of successful builds."

    - title: "Online Shopping Web Application"
      link: "https://github.com/DhananjayGupta300/Online-Shopping-Web-Application"
      github: "https://github.com/DhananjayGupta300/Online-Shopping-Web-Application"
      image: "/images/onlineshoppingwebapplication.jpg"
      about: "This web application displays various categories of products to purchase or look for. It allows users to have their private accounts and put items in a shopping cart."
      
      
    
      
      
    - title: "Comparative Study of Priority Queue Implementations"
      link: "http://ijariie.com/FormDetails.aspx?MenuScriptId=3670"
      pdf: "/papers/one.pdf"
      image: "/images/FirstPaper.jpg"
      about: "Provides a survey of ways to implement priority queues and their associated complexities" 
      
    - title: "An Approach to Improve the Efficiency of Priority Queue Implementations"
      link: "http://ijariie.com/FormDetails.aspx?MenuScriptId=3966"
      pdf: "/papers/two.pdf"
      image: "/images/SecondPaper.png"
      about: "Discuses an approach to improve efficiency in implementing Priorty Queues through memory pool."
      
    - title: "Android Projects"
      link: "https://github.com/DhananjayGupta300/Android-Projects"
      github: "https://github.com/DhananjayGupta300/Android-Projects"
      image: "/images/Android.jpg"
      about: "Academic and non-academic projects on Android development."
      
      
    
   
---

