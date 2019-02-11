---

layout: post

title: “JAVA on the Rocks!”

excerpt: "JAVA: Java and Version Advocacy, wanted a new release to be neat? Well, here we got JAVA, on the rocks! "

modified: 2019-02-10

tags: [Java, Java 8, Programing Language, New Release, New Version, Software Engineering , Analysis, Dhananjay Gupta]

comments: true

image:
  feature: DhananjayGuptaJavaVersions.jpg

---

 

<section id="table-of-contents" class="toc">
  <header>
    <h3>Overview</h3>
  </header>
<div id="drawer" markdown="1">
*  Auto generated table of contents
{:toc}
</div>
</section><!-- /#table-of-contents -->




Introduction
------------

#### JAVA: Java And Version Advocacy!

Ever wanted a new release to be neat? Well, here we got JAVA on the rocks! This is a late post holding a gist of discussions at a meetup with guest speaker **Gill Tene**, CTO, Azul Systems, held at Arity, Chicago. <br/><br/>

The Java world is in the midst of tectonic shift. With dramatic changes to the pace of feature introduction, release lifecycles, compatibility policies, security update policies, and the required pace of adoption in production, all happening at the same time, the world ahead will look nothing like what you may have gotten used to. These are a few takeaways. They will provide a quick overview of what developers and operational people need to know if Java is part of their world.

<figure>
    <a href="/images/DhananjayGuptaJavaVersions.jpg"></a>
    <figcaption>It is not funny anymore!</figcaption>
</figure>

Takeaways
---------

2019 for Java, release pace, compatibility, free updates, version overlap.
+ Java 9+ deprecated (major architectural change approach) major parts of the JDK.
+ There is a new module system. Class file version will change every 6 months.
+ A new release every six months, whereas, LTS (Long Time Support) versions will come out every 3 years, i.e. after every six releases (Java 8, 11, 17,... then the progression continues).
+ Java ecosystem is siting in Maven Central, Github, it has lot of cross-dependencies. There are very few ‘leaf’ libraries, the ones only depending on JDK. They all work for Java 8! Dang, enters Java 9+ breaking everything (for the better?).
+ Example: OOS Library: HdrHistogram broke on Java 9, used in packages like NetflixOSS, Elastic Search etc., fixing it broke Java 7. Eventually built helper classes to bridge gaps. Is it possible if HdrHistogram had any dependencies?
+ Only leaf nodes could survive.

Conclusion
----------

+ Everybody is in a circle, **YOU GO FIRST!** 
+ How about a community shift of Maven Central to support Java 9+? Will it be like Java 6 to 7? Or like Python 2 to Python 3, which is not essentially solved after 11 years. 
+ Is Multi-Version Jars a solution?
<br/><br/>
The conclusion is open ended, nobody heretofore, has the perfect answer to all these questions. 

### My Opinion 

Java 8 will be around for quite a while. <br/><br/> Moving forward to Java 11 or the latest is a better option because rest of the versions are already dead.
<br/><br/> The main problem is building a roadmap on using Java in production. Jakarta EE eclipse has 894 dependencies, so what about Java 11? A 12-18 months security update overlap is critical for continuity (Java 8 fixed 1926 bugs in seventeen months, 1213 bugs in between the sixth and eighteenth months).<br/> Earlier, the long term supported versions provided stability, security and free updates, all together. The dynamic shift has rendered a problem, no more overlap now! One must pick any two from among stability, security and free. <br/><br/>

Someone must take care of this! Who are they going to be? 

The discussion is thereby **open-ended!** JAVA, on the rocks indeed given me a buzz! does it ring any bells to you?

