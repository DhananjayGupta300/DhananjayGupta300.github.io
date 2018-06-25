---

layout: post

title: “Just Git-ting!”

excerpt: "Git: Identifying some undesirable properties"

modified: 2018-01-22

tags: [Git, Problems, Design, Analysis, Dhananjay Gupta]

comments: true

image:
  feature: DhananjayGuptaJustGitting.jpg

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

Success of a software development project, and the usability of the final product, depends on the quality of the concepts that underlie its design. Here are a few **key takeaways** from the early stage of the first study, on the Git version control system by [Santiago De Rosso](https://spderosso.github.io/) and [Daniel Jackson](https://en.wikipedia.org/wiki/Daniel_Jackson_(computer_scientist)).


Background
----------

**Conceptual design** for us, is about the design of user-visible behavior, and not the design of internal software structure, and we use the term “conceptual model” for a specification that focuses on concepts rather than the details of behavior. <br/><br/>
It is important identifying underlying concepts, and separating them from their realization in code. Doing so enables conceptual design to be pursued independently of implementation decisions; in short, the most basic form of “what” before “how.” <br/><br/>
Sometimes the conceptual basis of a software product is built by analogy to the real world. Git is an example of this, with concepts such as “tracked file,” “staging area” and “local repository” that have no a priori meaning. <br/><br/>
discover or invent the right concepts, and that rough edges in these concepts and their relationships will lead to rough edges in the delivered product.


>   The Mythical Man Month, Fred Brooks described **conceptual integrity** as “the most important consideration in system design.”


Conceptual design is about the design of user-visible behavior, and not the design of internal software structure, and the term “conceptual model” is used for a specification that focuses on concepts rather than the details of behavior. <br/><br/>
Brooks lists three principles as representing the notion of conceptual integrity: 

1. **Orthogonality** – that individual functions should be independent of one another
2. **Propriety** – that product should have only the functions essential to its purpose
3. **Generality** – that single function should be usable in many ways

<br/><br/>

The Gist! Problems with Git
---------------------------

#### Staging area complications:

- Explanations of Git use the term “*tracked files*” to refer to files that have been added. This confuses novices, since such files are tracked only in the sense that the status command will notice that changes to them have not been committed. *Contrary* to initial expectation, if a tracked file is updated, a subsequent commit will save the older version of the file (representing its state the last time the add command was called), and not the latest version.
- The situation is made more *complicated* by the fact that tracked files may not have corresponding versions in the staging area. Following a commit, a file that had been previously added remains tracked, but the version in the staging area is removed. The term “*staged file*” often used interchangeably with “*tracked file*” is thus subtly different: in this case, we have a file that is tracked but no longer staged.

#### conceptual model:

conveyed by an application–in its documentation, marketing materials, implied by its user interface, and even in the culture that surrounds it – has to be regarded as inseparable from the application itself. So to the extent that consensus is missing on an application’s conceptual model, it is arguably the application itself that is at *fault*.

#### File Discrepancies:

+ A File is the identity of a *Unix file*, to be distinguished from its contents. In Git, identity is equated with the path of the file; thus the concept might equally well have been named File Path. <br/>
+ An alternative designation of File would treat it as an identity independent of the file’s path, so that a change of name could be regarded as a modification of one of the properties of a file. Git sometimes provides an *illusion* that this is the case; by examining the contents of files, for example, the git status command is able to report when the name of a file has been changed (but will also *incorrectly* report a change of name if you copy a file and delete the original). <br/>
+ It is important to note that existence of a File does not imply that a Unix file corresponding to it exists in the file system, since a File can be staged for removal on the next commit. <br/>
+ **Tracked Files:**<br/>
  - The Pro Git book describes *tracked files* as *“files that were in the last snapshot; they can be unmodified, modified or staged.”* It’s not entirely clear what is meant by “files that were in the last snapshot” but from the context it appears to mean “files that were in the last commit point.” The book then says “Untracked files are everything else,”but then qualifies this, surprisingly, with “[namely] any files in your working directory that were not in your last snapshot and are not in your staging area” suggesting that tracked files also includes files that have been staged but are not part of the last snapshot, *contradicting* the earlier definition. <br/>
+ **Untracked Files:** <br/>
  - Executing `git rm --cached` of a tracked file stages the removal of the file without touching the file in the working directory, so that it will be deleted from the repository at the next commit. Subsequently running `git status` will show the file under both the “Changes to be committed” section (as “deleted”) and in the “Untracked files” section. We thus have a file that is both tracked and untracked (according to our designations).
  
#### The `git rm` command:

To remove the file from the repository, in contrast, one executes a `git rm`, which removes the staged and working versions, and additionally marks the file for removal in the next commit. Git’s documentation is not a big help here; the man page for `git rm`, for example, states “Remove files from the index, or from the working tree and the index.” suggesting that an unstaging is performed, when in fact a staging for removal is performed instead. <br/><br/>
Some care is required in distinguishing between a file being unstaged (meaning that its staged version is removed) and being staged for removal (which means that the staging area records the absence of the file rather than its presence, so that it will be removed from the local repository on the next commit). Suppose a file is added (using the `git add` command), then removed (using the `Unix rm` command)and then committed (using the `git commit` command). Prior to the commit, the file has a staged version but no working version; after the commit, it has no staged version either.      

Conclusion
----------

**orthogonality** – <br/>
*What Happened to My Changes?* <br/><br/>
The concepts of staged and working versions are not orthogonal. Many commands that are primarily intended to modify one of the two modify the other too. Worse,whether or not these ripple effects occur depends on which arguments are presented to the commands. <br/><br/> 
**propriety** – <br/> 
*Just Let Me Commit!* <br/><br/> 
Some Git enthusiasts make arguments for the value of the staging concept, but for most users it offers inessential functionality, and its presence complicates the use of Git considerably. <br/><br/>
**generality** – <br/>
*I Just Want to Switch Branches!* <br/><br/>
Branches are intended to support independent lines of development. A line of development comprises both the working versions of files and committed versions. And yet, in Git’s conceptual model, only the committed versions are organized by branch; while there are potentially multiple committed versions of a file (one per branch), there can only be one working version. There is thus a lack of generality, with the branching feature essentially available only in one area and not another. <br/><br/> 
*I Just Want to Stop Tracking a File!* <br/><br/>
The concepts of “assumed unchanged” and “untracked” play fundamentally the same role: they mark files that are not to be included in commits. And yet there is no general concept that subsumes the two of them, since Git distinguishes files according to whether they have been previously committed; a file can only be untracked if it is not also committed. Whether a file is committed is not under the user’s control, since a file can be committed as a result of a pull from another user’s repository. In short,there is a violation here both of generality (since a more general concept would subsume both cases), and propriety (since the concept of “assumed unchanged file” could be eliminated).
