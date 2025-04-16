Evidence
========
A primary intellectual activity is the gathering of evidence to
determine the nature and structure of things. It is closely related to
the task of discrerning similarity, and of reasoning by analogy.
This git repo is a rumination of these tasks, plus an attempt to express
these ideas as functional code, expressed as OpenCog [Atomese](https://wiki.opencog.org/w/Atomese).

Overview
--------
The process of evidence-gathering and stitching together a story is
used everywhere in human undertakings: examples include journalism, to
put together a news story; jury trials, to determine guilt or innocence;
scientific investigation, to understand the structure of nature.

An example from biology is whole-genome sequencing: stitching
together snippets of genetic sequences, obtained from PCR, into a whole.
Unlike journalism, jury trials or scientific investigation, genome
sequencing can be machine-automated. It is, however, extremely domain
specific: it can only be used for genetics. It is not extensible to
other domains.

The goal of the present project is to explore the foundations of
evidence gathering and the weaving together of (coherent) stories,
and to expose this foundation so that it is amenable to algorithmic
processing. To describe the process of construction sufficiently well,
that it can be applied to arbitrary domains and situations. And not just
philosophically or mathematically, but expressed as software that can
actually do "useful things" that "people want".

The project here is a mash-up of theory and experiment, of philosophy
math and code. The terminology will bounce between abstract concepts and
low-level code. Apologies in advance if it veers off into the opaque.
The topic is difficult.

Genealogy
---------
A concrete example is in order, one that sits part-way between
abstraction and algorithmic directness. Genealogical research provides
such an example.

Genealogy, as practiced by familysearch.org (controlled by the Church
of the LDS) is semi-automated.  The raw material consists of public data
about births, deaths, census records, military draft records,
naturalization records, passenger lists, parish church records,
marriage certificates, obituaries and the like. Each data item provides
a bit of information that attests a specific event. Some are highly
structured: birth certificates have a regular form. Others, not so much:
obituaries may or may not list relatives, and may or may not make the
relationships clear.  The task is to stitch together a genealogical
structure out of these fragmentary jigsaw pieces.

The evidentiary issue is that no single attestation of an event or
relation is fully trustworthy.  A short survey is worthwhile.
Most of the records predate computerization, and are hand-written,
usually in cursive. Cursive writing is not standardized: there is a vast
variety of styles, especially problematic in 18th and 19th century
European records. There are errors from the transcription of these
texts. The spelling of names and surnames presents a challenge,
espcially for European immigrants, where the spelling conventions clash
between the native language and English: many names are simplified and
Anglicized. Catholic Church parish records often convert native names to
Church Latin. Census records indicate that some people are either sloppy
or are fudging the facts, or perhaps they really do not know thier
birthdays or how they were spelling their surname a decade earlier.
Many surnames are extremely common, and there are many couples named
"John & Mary".

In practice, the stitching-together is semi-automated. The
familysearch.org system offers up a list of possible record matches,
based on names, dates, locations. A human reviewer then has to review
the record and make a judgement call: is this an appropriate match? If
so, it can be added to a record, buttressing support for a particular
name, date, location, spelling, event.

The judgement call is often hierarchical in nature. For example: do the
father's and mother's names match? Well, perhaps they do, but there is
some alteration in spelling: Maria vs. Mary, Elizabeth vs. Betty. One
can assign some probability or confidence in the beleif that these are
the same parents. To butress that beleif, one can look at sibilings: if
two children are born three months apart to the same mother, then
this is a piece of negative evidence that absolutely demands a rejection
of a match. That is, of course, only if the recorded birthday is
correct. Perhaps there are other attestations to the birthday? The
evidentiary chain is now four levels deep: individual -> parents ->
siblings -> birthdays -> evidence of birthdays. Each arrow in this chain
can be assigned a confidence; each act of confidence assignment is some
agglomeration of the supporting evidence. A preponderance of evidence
is desired. This can be taken as a mathematical mean or average, but
it can also be some more complex algorithm extending across the
structure: for example, "voting in new members to the club of facts".
In comp sci, similarity is measured with cosine distance, Jaquard
distance, mutual information, Kullbeck-Liebler divergence or any one
of dozens or hundres of different similarity measures, which can be
aggregated and weighted in a large variety of ways (random forests,
collections of experts, membership clubs, etc.)

A much simpler, and more easily automated example occurs in operating
system storage integrity. Here, one is presented with mutiple files,
often having the same name, but not always; often having the same
timestamp, but not always; often appearing in the same directory, but
not always; often having the same size, but not always; often having the
same content, but sometimes haveing all-zeros where the data should have
been. Or perhaps MP3's with missng bytes, or images with steganographic
watermarks. The challenge is to find the copy of the file that is least
likely to be corrupted, and is most likely to be "correct". Despite the
fact that all data is directly available from the operating system,
using very pure and well-defineed, structured software interfaces, this
turns out to be a hard problem.



Status
------
Version 0.0.0. Nothing yet.
