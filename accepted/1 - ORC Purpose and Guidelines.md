
Author:  Tres Walsh (SAHChandler)  
Created: 2010-03-29  
Updated: 2010-04-16  
Type:    Guideline  
Status:  Accepted  
Fixes:   None  

ORC Purpose and Guidelines
==========================

   + Motivation
   + What is an ORC?
   + ORC Types
   + ORC Workflow
   + ORC Submission Process
   + ORC Status
   + Writing an ORC
   + Transferring ORC Ownership
   + Rationale
   + Issues
   + References and Footnotes


Motivation
----------

At the time of this writing, there is little to no "set in stone" ruleset for writing additions, features, extensions, or changes to the ooc language. The Benevolent Dictator For Life (herein referred to as the BDFL) has expressed his interest in a set of guidelines, with the community having the ability to vote, discuss, and approve of any additions to the ooc language. These "revisions" are known as an ORC.


What is an ORC?
---------------

ORC stands for ooc Revision Consideration. An ORC is a design document providing information to the ooc community, or describing a new feature for ooc; its processes or environment. The ORC should provide a concise specification of the feature as well as a rationale.

We (the ooc community) intend ORCs to be the primary mechanisms for proposing new features, for collecting community input on an issue, and for documenting the design decisions that have gone into ORC, as well as the invasion of Middle Earth. The ORC author is responsible for building consensus within the community and documenting dissenting opinions.

ORCs are stored in a git repository on github, so that any new members to the ooc community may see the history of ORCs.


ORC Types
---------

There are several types of ORCs

   1. Guideline - A guideline dictates a way in which ooc workflow is to be performed, from code generation, to compiler implementation, as well as any other role that would require a rule of some sort, but does not involve the addition of language changes. 
   2. Feature   - A core language feature. Accepted Feature ORCs will become part of the ooc standard library. Feature ORCs that do no propose a true cross platform implementation, or feature, should be named as Extension ORCs instead.
   3. Extension - An extension is any additional library. This could be anything from a language bridge (e.g. ooc to Python), to a platform specific feature (e.g. DirectX or Cocoa bindings). As these are not part of the core ooc language, they are not required to be implemented by implementations other than the core ooc implementation (i.e. rock).
   4. Fix       - If the community as a whole sees a problem with the language, one that might require changes to the implementation of the language, a Fix ORC should be used. This could detail a new memory model, or writing a garbage collector in ooc, something that would affect the core language, but isn't a feature, as the proposal is a fix to a pre existing feature. If a feature currently exists, but there is no guideline, feature, or extension ORC for it, Fix ORCs should not be used, and an official ORC should be written for said feature. This only applies to current language features that have existed before the creation of ORCs. When a Fix ORC is approved the ORC that it is a Fix for, must make a reference to the ORC number. (e.g. in the future when this ORC must be modified via a Fix, the Fix ORCs will be mentioned in this file.


ORC Workflow
------------

An ORC may have only one idea, or a single solution to any given problem.

Each ORC must have a champion. This is the person who writes, hypes, and answers any and all questions related to the ORC throughout its lifetime. This person is also known as the Author. Before writing the ORC, the Author should ascertain if there is any interest in such an ORC by asking the community in the mailing list, or the IRC Channel. Of course, if most feedback is negative, the Author should seriously consider *not* writing the ORC, though there is nothing stopping them. 

Once the ORC has had what appears to be a decent amount of positive feedback, a draft ORC should be submitted to the community. This allows the Author to modify the ORC more to the community's wishes, as well as fix any problems before the ORC is submitted. 

There is no specific ruleset to determine whether an ORC has received a negative amount of feedback however, there are a few events that a potential Author should take note of as discouragement. Among these are several negative messages in quick succession and grey wizards showing up at your doorstep.

It would be best for potential Authors to keep a tally of yay or nay throughout the community, to judge potential interest. 

Finally the ORC is submitted to the BDFL for final review via a pull request on github. The BDFL may or may not choose any members from the community to discuss the ORC with. Note however, that there must be a 5 day minimum period between the Draft creation and submission. This is to ensure that there is ample enough time for a majority of the community to see and comment on the Draft.

If the ORC is approved, it will be placed in the accepted folder of the [middleearth][1] repository for public consumption and will be a part of the official language specification.

If an ORC is rejected, the BDFL, and any consultants must inform the community of their decision, as well as the reasoning behind. The ORC will then be marked as rejected, and placed in the rejected folder of the middleearth repository (Along with the reasons for it's rejection at the bottom of the file), as a record of it's existence, and to ensure that multiple ORCs on the same subject or idea are not proposed. 

After 6 months, the Author of a rejected ORC may make a case to move their ORC from rejected to accepted. At this point the ORC will be placed in draft status, and the community will once again be allowed to voice their opinions. There is no limit as to how many times an ORC may be tasked for re-evaluation. 

An ORC can replace, or make a previous ORC obsolete. In this instance the older ORC will be marked as Obsolete.

Additionally, if there was a large controversy over the acceptance of an ORC, any member of the community may move to Contest the ORC in question. However, the ORC may not be contested until 3 months after its implementation (which is separate from its acceptance). A Contested ORC will be moved to the Contested status, and will gain immediate priority in ORC Reviews. 

Once an ORC is rejected, or accepted, it will be assigned a number. This number will precede the file's title (e.g. 2 - Some Arbitrary Feature), but the ORC will be referred to in the following way: (i.e. `ORC-2`)


ORC Submission Process
----------------------

The ORC submission process is as follows. Fork the main [middleearth][1] repository on github. From there, work on your ORC in your forks master branch. Eventually, a pull request is sent to the BDFL account (in this case ooc). The BDFL will then merge your master branch into the core middleearth draft branch. Anything in this branch is instantly considered Under Review. Once it is Approved, or Rejected it will be moved into the master branch, or rejected branch (respectively).


ORC Status
----------

An ORC may have only one of the following statuses.

 * Draft
 * Withdrawn
 * Accepted
 * Contested
 * Rejected
 * Obsolete


Writing an ORC
--------------

An ORC must have the following layout

 * The file in which the ORC resides must be named the same as the Name in the header. Spaces must also be included.
 * Header - The Header must contain the Author's name, as well as any alias they use in the ooc community (This is for recognition in the IRC Channel). It must also contain the date the ORC was written in ISO-8601 format (Year-Month-Day). The Header must also contain the ORC's name as well as its current status, as well as any Fix ORCs that affect it.
 * License - All ORCs are released under the [Creative Commons Attribution-Share Alike 3.0 License][2].
 * Index - A bulleted list containing the names of subsections are placed in the ORC, under a large header of the ORC's name.
 * Motivation - A small paragraph explaining how the ORC came to be.
 * Specification - A detailed analysis of the *how* of the ORC, explaining it's implementation, and possible problems that may arise from it.
 * Rationale - A detailed analysis of the *why* behind the ORC, explaining it's necessity to the community.
 * Issues - Any issues that may arise be it from platform implementations, to compiler issues, as well as any problems the Author may have with the ORC.
 * References and Footnotes - The end of the ORC should contain links to any references mentioned in the ORC, as well as footnotes, such as explanations for terminology used. 

While file line endings are not enforced, it is recommended that line endings use the Unix format (LF), rather than the Mac OS X (CR) or Windows (CRLF) line endings. Most Text Editors allow for the selection of line endings.


Transferring ORC Ownership
--------------------------

Every so often the transfership of an ORC's owner is necessary. Whether this be from the Author's disappearance in Real Life, to death, to general dislike of working with the ORC. In the two former cases, a member of the community must contact the BDFL and inform them of the intent to transfer ownership. If no one steps up (withing a 2 month period, after a 3 - 4 month period of no contact), the BDFL will automatically take ownership of the ORC, but may delegate to any member in the community who has shown a willingness in helping with the ORC. The BDFL may also mention to the community a lack of interest, and a need for a new Author. In the last case however, the Author must mention their unwillingness to continue to work on the ORC, and request a member of the community step up. Once a member has come forward, the BDFL must be contacted, and informed of the switch. The BDFL must be informed of the transfer so as to ensure the ORC's information is updated in the ORC repository.


Rationale
---------

As communities grow and prosper, a set of rules and guidelines to ensure quality code, as well as a disciplined community, are necessary. The PEP, from which ORCs are effectively derived, are a perfect example of this. Conversely, several languages take the committee approach, where every couple of years the current state of computing is assessed, and new features are added. In today's world of constantly shifting computing paradigms, a more dynamic approach is necessary to ensure that a language stays up to date with the most recent advances in computer science, while also following the will of the actual users of the language.

Issues
------

In the future, as the community progresses and ooc's use increases, requiring everything to be run through the BDFL may become overwhelming. At some junction in the future, a Fix ORC may be necessary to outline an ORC Editor, which has the same responsibilities as the BDFL in the sense of approval and ownership. However *when* this will occur is still unknown, and doesn't appear to be anywhere in the near future. 


References and Footnotes
------------------------

[1] http://www.python.org/dev/peps/


[1]: http://github.com/ooc/middleearth "ORC Repository"
[2]: http://creativecommons.org/licenses/by-sa/3.0/ "Creative Commons License"
