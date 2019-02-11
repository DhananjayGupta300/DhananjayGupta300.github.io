---

layout: post

title: “JAVA on the Rocks!”

excerpt: "JAVA: Java and Version Advocacy, ever wanted a new release to be neat? Well, here we got JAVA, on the rocks! "

modified: 2019-02-10

tags: [Java, Java 8, Programing Language, New Release, New Version, Software Engineering , Analysis, Dhananjay Gupta]

comments: true

image:
  feature: DhananjayGuptaJAVA.jpg

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




JAVA: Java And Version Advocacy!




Introduction
------------

##JAVA: Java And Version Advocacy!

Ever wanted a new release to be neat? Well, here we got JAVA on the rocks! This is a late post holding a gist of discussions at a meetup with guest speaker Gill Tene (makes JVM’s), CTO, Azul Systems, held at Arity, Chicago.

The Java world is in the midst of tectonic shift. With dramatic changes to the pace of feature introduction, release lifecycles, compatibility policies, security update policies, and the required pace of adoption in production all happening at the same time, the world ahead will look nothing like what you may have gotten used to. These are a few takeaways. They will provide a quick overview of what developers and operational people need to know if Java is part of their world.

## Takeaways
2019 for Java, release pace, compatibility, free updates, version overlap.
+ Java 9+ deprecated (major architectural change approach) major parts of the JDK.
+ There is a new module system. Class file version will change every 6 months.
+ A new release every six months, LTS (Long Time Support): every 3 years, i.e. after every six releases.
+ Java ecosystem siting in Maven Central, Github, it has lot of cross-dependencies. Very few ‘leaf’ libraries, the ones only depending on JDK. They all work for Java 8! Dang, enters Java+ breaking everything (for the better?).
+ Example: OOS Library: HdrHistogram broke on Java 9, used in packages like NetflixOSS, Elastic Search etc., fixing it broke Java 7. Eventually built helper classes to bridge gaps. Is it possible if HdrHistogram had any dependencies?
+ Only leaf nodes could survive.
## Conclusion
+ Everybody is in a circle, YOU GO FIRST! 
+ How about a community shift of Maven Central to support Java 9+? Will it be like Java 6 to 7? Or like Python 2 to Python 3, which is not essentially solved after 11 years. 
+ Is Multi-Version Jars a solution?
The conclusion is open ended, nobody heretofore, has the perfect answer to all these questions. Java 8 will be around for quite a while. <br/> Moving to Java 11 or the latest is a better option because rest of the versions are already dead. The main problem is building a roadmap on using Java in production. A 12-18 months security update overlap is critical for continuity (Java 8 fixed 1926 bugs in seventeen months, 1213 bugs in between the sixth and eighteenth months. Earlier, the long term supported versions provided stability, security and free updates, all together. The dynamic shift has rendered a problem, no more overlap now! One must pick any two between stability, security and free. <br/>
Jakarta EE eclipse has 894 dependencies, so what about Java 11?
Someone must take care of this! Who is it going to be? 

The discussion ends open-ended! 

