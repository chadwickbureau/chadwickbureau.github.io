---
title: Bioclusters: How the Register documents people's careers
---

## Bioclusters: How the Register documents people's careers

The objective of the Register is to organise data documenting people's
careers in baseball. A central research question is how many people fall
within the Register's scope, of having played, managed, or umpired in a
game or been an executive or administrator of a league or club, at a
sufficiently high level. We don't know the answer to this, even to an
approximation. The Register crossed 400k entries in mid-2021; even
conservative extrapolation suggests we will have more than 1m entries
soon as we organise data on college ball and improve coverage of pre-WW2
minor and semipro leagues.

We are accustomed to having encyclopedias of MLB players, and now
websites like Baseball-Reference (which uses the Register) and
Wikipedia, which present basic information on players and other baseball
people. These tidy presentations of information mask a much more messy
reality underneath. All the information you see in those places
ultimately comes from some original source. The sources for the
information are scattered, generally contain incomplete information, and
surprisingly often contain conflicting information. What you see in
those resources is the product of countless hours of work by hundreds of
researchers over the year. Nevertheless, even details like proper names
or dates of birth for historical MLB players continue to be revised,
despite 50 years of scrutiny by researchers, to say nothing of the much
broader population the Register documents.

This document explains how we go about establishing basic identifying
details for people in the Register.

## Why a 'wiki' approach isn't enough

A simple approach to developing this data would be to have an editable
database or a wiki, in which we record these details. We can illustrate
the limitations of this approach with a fictitious example.

Suppose we have an entry for Joe Shlabotnik in our database, born in
Springfield. A researcher uncovers a source, call it Source A, that
indicates Shlabotnik was instead born in Shelbyville. However, he
doesn't feel confident in the source, so he leaves the database
unchanged. Now a second researcher uncovers a different Source B, that
has Shlabotnik born in Shelbyville. The fact there is Source A as well
gets lost. This process could repeat many times, so even if Shlabotnik
was in fact born in Shelbyville, the database will remain unchanged.

The opposite situation can occur as well. Sources copy from each other,
in ways we don't observe as researchers. So imagine the opposite
situation, in which we have a lot of sources in which Shlabotnik is
listed as hailing from Springfield -- but it turns out many of them
copied from each other. A researcher finds another source indicating he
was born in Shelbyville, which actually is correct. So simply counting
the number of sources attesting a piece of information isn't good enough
either.

Here we've assumed that there is in fact one Joe Shlabotnik. What if the
reason for the confusion is that there are in fact two, possibly both of
whom were baseball players?[^1] It is not uncommon for sources to
confuse similarly-named people. In our Shlabotnik example, we would need
a way to deal with disentangling Springfield Shlabotnik from Shelbyville
Shlabotnik as we evolve our dataset.

If you were an expert in Shlabotnik studies, you could easily keep all
of this in your head or in a file. If you were tracking a population of
a few hundred people at most, a researcher could also keep all of this
straight. But we want something that scales to 1m people, where
researchers can collaborate to find individual pieces of the puzzle.

This points to a system in which we have a *source-oriented*
organisation of information. That is, our core database doesn't consist
of one entry per person -- it consists of one entry per mention of a
person in some source.

## Our core strategy: Key source compilations

There is a substantial amount of source information, often already in
electronic form, available from the last few decades. Computerisation of
record-keeping started in the late 1980s and was not fully established
until about 2000. Prior to that, identification of people requires
pulling together information from a variety of sources.

Our strategy for establishing a core of well-identified people,
primarily those involved with professional baseball in the US, draws on
the integration of several types of sources. Much of our research
activity involves systematically curating these sources and transcribing
the relevant information into a structured format.

You can read more about our current priorities and progress on some
of these key sources in our [page describing our historical data](/doc/historical).

These sources have often complementary strengths and weaknesses; used
together they allow us to get a fairly accurate picture of basic
information on people and establish the distinctness of similarly-named
individuals, or the case in which an individual is known by more than
one name.

We take a pragmatic approach to collecting and indexing this
information. While we do track the number of people for whom we have an
obituary, the number with a findagrave memorial, the number linked to a
TSN contract card, and so forth, we do not have particular targets in
mind for coverage. Especially when searching non-baseball records,
finding a match for a person is happenstance. We therefore take what you
can think of as a breadth-first approach: We try to have *fairly good*
information across a wide number of people, rather than trying to drill
down one person at a time.

Therefore, we have designed a system that lets us incrementally improve
our identification of different people and the details we know about
each of them, based on information as we encounter it. Our knowledge is
always provisional, and we improve it both by collecting more source
records, and improving the inferences we draw by linking among them.

## Establishing identifications: Record linkage

The objective of the Register is that every person should have an entry,
and every entry should refer to one person. Our underpinning source
collections will contain potentially many references to the same person.
The task of merging together the source data into the Register records
is done using a **record linkage** framework.[^2] Our approach automates
much of the drudgery of trying to find pairs of source references that
refer to the same person. Importantly, confirming matches between
records is done by researchers. Basically, we let automation do what
automation does best -- which allows us to have the ambition to carry
information on 1m or more people -- and let humans do what humans do
best -- which is dealing with the inherent messiness and ambiguity of
the source data.

Here some examples from the files on how this matching looks in
practice.

**An example match**. We have this obituary on file:

	[obituaries:202005_050] Bruder, Henry J. [Hank]
	birth 1930-04-17 @ US/IL/LaSalle
	death 2003-03-28 @ US/IL/Genoa
	highschool St. Bede Academy @ US/IL/Peru

In our findagrave files we have this record

	[findagrave:0080] Bruder, Henry J. [Hank]
	sameas findagrave:135294367
	birth 1930
	death 2003
	burial St. Catherine Cemetery @ US/IL/Genoa

These (almost certainly!) refer to the same person. So, we record a link
indicating that `obituaries:202005_050` and `findagrave:0080` the **same**
person.

**An example non-match**. We have this obituary on file:

	[obituaries:202002_008] Barton, Larry, Jr.
	birth 1939-10-11 @ US/CA/Los Angeles
	death 2020-02-06 @ US/KY/Louisville
	highschool Gardena HS @ US/CA/Gardena
	college Arizona State University

In our findagrave files we have this record

	[findagrave:0091] Barton, Larry, Sr.
	sameas findagrave:73500111
	birth 1912-11-21 @ US/CO/Pueblo
	death 1992-03-05
	highschool Fremont HS @ US/CA/Los Angeles
	burial Maple Park Cemetery @ US/MO/Springfield

These of course refer to different people (father and son in this case).
So we record a link indicating that `obituaries:202002_008` and
`findagrave:0091` are **different** people. Recording when we have records
referring to definitely different people is useful, because it keeps us
from revisiting the same comparison.

**An example unknown**. It's also possible that we can't be sure whether
two records do or don't refer to the same person. We have an obituary:

	[obituaries:202104_016] Fleming, Francis F.
	death 1947-07-05 @ US/MA/Cochituate
	burial St. Joseph Cemetery @ US/MA/West Roxbury

And we also have a birth record:

	[vitals:202104_006] Fleming, Francis Fredrick
	birth 1911-05-01 @ US/MA/Brookline

It's true these *probably* refer to the same person, but there isn't
enough to go on there to be certain. It could easily be another pere et
fils case as with the Bartons, for instance. In this case, we would
record a link indicating it is **unknown** whether
`obituaries:202104_016` and `vitals:202104_006` are the same person or
different people. It is again useful to record comparisons where we
don't have enough information to confirm or refute a match, because it
saves us from revisiting them.

**Finding candidate matches**. There are two main ways in which matches
get found, evaluated, and recorded.

-   We have an automated tool that looks for records which are similar,
    based on names and other information in the record, and prompts the
    researcher to label the link as **same**, **different**, or
    **unknown**, if a link does not already exist.

-   Researchers often look for multiple sources on a particular person
    at the same time. In fact, the Bruder and Fleming examples are both
    products of one researcher working on that person. In such a case,
    the link can just be recorded directly alongside adding the records
    to the files. This amounts to the researcher recording their chain
    of logic as they do their research.


## From source data to the Register: Bioclusters

The next step is to use the source information, and the linkages we
record, to figure out the entries in the Register. An advantage of
looking at pairs of records as above, is it is very easy for a
researcher to look at the pair in isolation, and so we break down the
potentially huge task of matching what someday may be millions of
records, into bite-size chunks. However, we hope to have many sources
referring to a person.

To illustrate how this works, let's pick up the case of Francis Fleming
from the previous section. Although we marked the link between the
obituary and the birth record as unknown, it does turn out they do refer
to the same person. We have a findagrave entry:

	[findagrave:502] Fleming, Francis F.
	sameas findagrave:171956740
	birth 1911
	death 1947
	burial St. Joseph Cemetery @ US/MA/West Roxbury

From this, we definitely *can* say that `findagrave:502` and
`obituaries:202104_016` are the **same** person, and `findagrave:502` and
`vitals:202104_006` are the **same** person. From that, we can logically
infer that in fact `obituaries:202104_016` and `vitals:202104_006` are the
same person.

We don't go back and change the **unknown** link we recorded between
`obituaries:202104_016` and `vitals:202104_006`. We wouldn't want to do
that, because it would change the chain of reasoning we're doing on
Fleming; but also it would be very tedious! Fortunately, we don't have
to, because the chain of logic we just did in the previous paragraph can
be automated. There is a straightforward algorithm which takes all of
the **same** links we record, and creates groups of records, such that
any two records in a group have such a chain of **same** links between
them, and two records in different groups do NOT have any chain of
**same** links between them.[^3] We call such a group of records a
**biocluster**. In this example, `findagrave:502`, `obituaries:202104_016`,
and `vitals:202104_006` would be placed in one biocluster, and, for
example, `findagrave:0080` and `obituaries:202005_050` would be placed in a
different biocluster.

At this point it is worth remarking that the algorithm to construct
bioclusters actually does not use **different** links. This is quite
useful, because it would very tedious if we had to record explicitly
that the records referring to Fleming and those referring to Bruder
referred to different people. We can use **different** links as a
cross-check on the bioclusters, by ensuring that it is never the case
that we place two records in the same biocluster which have been
explicitly recorded as being different; this is quite useful when
disambiguating similarly-named people, especially when their careers
have been confused in sources.

## Persistently identifying people

We have now boiled the problem of identifying people down to the
objective of having one biocluster refer to one person, and vice versa.
We can think of this as a person being represented by a biocluster of
source records. As we do research, the number and contents of clusters
will change. However, we want to establish a stable, persistent
identifier that, to the extent possible, always will refer to the "same"
person.

Let's continue with the Fleming example. As it so happened, when we
started, we had `obituaries:202104_016` and `findagrave:502`, and a
**same** link between them. When we ran the clustering algorithm, it
created a new biocluster containing those two records.

When new clusters are created consisting entirely of new records, the
algorithm assigns an identifier; in this case `SGQN-H677/1`. The part
before the slash is the part of the identifier that is intended to be
persistent. It is generated randomly, and consists of two groups of four
characters selected from letters excluding A, E, I, O, and U and the
digits 3 through 9.[^4] This gives us 377,801,998,336 possible
biocluster names. The part after the slash is a version number; this is
the first version of this biocluster, so it is given number 1.

Now, subsequently we recorded his birth record `vitals:2020104_006` and
linked it to the findagrave record. The next time the clustering was
done, it produced a biocluster of the three records. "Common sense"
tells us that it would be desirable for this new biocluster to be
thought of as referring to the "same" person. The algorithm assigns this
biocluster the identifier `SGQN-H677/2`, that is, version 2 of biocluster
`SGQN-H677`. This gives us a way of establishing continuity: It's
meaningful to think of `SGQN-H677` as being Francis Fleming's "person ID"
in the system, while at the same time we can track when the underpinning
set of information on him changes.

It is quite common in the process of doing research to find two pieces
of information that actually refer to the same person, but we can't be
sure. Imagine instead that we found the findagrave record for Francis
last. In this absence of this record, we would have been in a situation
where we had one biocluster consisting of his obituary, and another
consisting of his birth record. When we found the findagrave record and
added the **same** links, the next run of the algorithm would have
created one cluster.

In this case, we would have been in a situation in which we had **two**
bioclusters which referred to the same person, with two biocluster IDs.
In situations in which we merge bioclusters, we select one of the
biocluster IDs of the contributing clusters to continue. To try to make
IDs as stable as possible, we use a few heuristics to select the
continuing ID. Generally, we will use the ID corresponding to the
"thickest" contributing cluster -- that is, the one which contains the
most details and the most records. Over time, this leads to people who
are well-documented having stable biocluster IDs, while the biocluster
IDs for people who are only provisionally documented so far will be less
stable.

The system described so far builds person identification "from the
ground up" -- bioclusters will only ever merge between successive runs
of the clustering algorithm, and never split. We are conservative in
recording **same** links, as the Fleming example illustrates. However,
there will be times in which we erroneously record a **same** link
between two records, for example, when a source record lists the wrong
information on a person, or when we simply make a clerical error
ourselves. When a **same** link is removed, clusters may split. In such
a case, we look at the split and make a judgment about which resulting
biocluster retains the persistent ID, using judgment and common sense as
to what a user of the data would expect. Because our methods of working
ensure that removing **same** links will be rare, cluster splits
likewise will be.

## From bioclusters to the Register

The "person" identifiers in the Register are eight-character hexademical
numbers, which are different from the biocluster IDs. The final step in
the process is matching a biocluster to a Register entry: each Register
entry is matched to at most one biocluster.

For example, Francis Fleming's biocluster `SGQN-H677/2` contained these
three records:

	[vitals:202104_006] Fleming, Francis Fredrick
	birth 1911-05-01 @ US/MA/Brookline

	[findagrave:502] Fleming, Francis F.
	sameas findagrave:171956740
	birth 1911
	death 1947
	burial St. Joseph Cemetery @ US/MA/West Roxbury

	[obituaries:202104_016] Fleming, Francis F.	
	death 1947-07-05 @ US/MA/Cochituate
	burial St. Joseph Cemetery @ US/MA/West Roxbury

This biocluster is matched to the corresponding Register entry, which is
`f9f87efb`. In doing so, a composite of the information in the sources is
made, and the composite information appears in the Register.
Conceptually it would look like this:

	[f9f87efb] Fleming, Francis Fredrick
	sameas findagrave:171956740
	birth 1911-05-01 @ US/MA/Brookline
	death 1947-07-05 @ US/MA/Cochituate
	burial St. Joseph Cemetery @ US/MA/West Roxbury

At this stage, the researcher would make any judgment calls about
conflicting data. For example, a common situation is when a player
mis-stated their age while playing, and turns out to be a few years
older when we find their birth or death records. In such a case, the
researcher would likely preference the data from the vital record.

The link from the Register to the biocluster includes the version
number. This allows us to track when an underpinning biocluster changes,
and triggers a re-review of the biocluster to pull new or changed
information from the cluster into the Register record.

We have two reasons for maintaining biocluster identifiers that are
different from Register identifiers:

1.  Even prior to the Register's inception, there have been databases on
    baseball players and other people. It would be completely
    impractical to start from a "blank sheet" and re-construct all of
    this information from scratch. Most Register entries do not (yet)
    have an underpinning biocluster; the objective of the process is,
    over time, to support the incremental improvement of Register data.

2.  Identification of people in our system is frequently provisional at
    first, with it being not uncommon for records referring to the same
    person to not yet be linked properly. Distinguishing between
    biocluster IDs and Register IDs allows us as researchers to hide the
    "sausage-making" of our process: Users of the data don't need to
    know, or care, about all of the technical details we deal with in
    converting messy source data to the structured information they see.

## Measuring progress

Perhaps the best part about our project is it will never be finished.
Given the size of our population, there will always be ways to improve
the data by searching out new sources. Open-endedness can also be
demotivating, however: if the task is so huge, why bother doing anything
at all? It's therefore useful to have some measures of progress.

Metrics have another use: communicating to data users. The typical user
of baseball data thinks data is far more reliable than it is, while the
baseball researcher very quickly encounters incompleteness and ambiguity
while doing their work. Further, because there has not been a formal
structure for this type of information, most of the information we have
is what we might call "folk" information, where publications have
largely copied from previous publications without recording specifically
which information comes from which source.

We want to have an answer to the question of *How reliable is the
information in the Register?* We can't ever be sure information is
absolutely correct, so we can't ever give guarantees that claim that the
information is "x% accurate". What we can measure, however, is how much
underpinning information we have.

We can therefore track over time:

1.  The number of source records of certain types we have collected --
    for example, obituaries, findagrave memorials, and so on. This
    reflects the raw materials of research.

2.  The distribution of sizes of bioclusters. This reflects our success
    in making linkages across different sources, giving us a broader
    base of evidence on individual people.

3.  The number of Register entries which have an underpinning biocluster
    ID. This reflects our success in communicating our research results
    to data users.

Although it is not straightforward to quantify the relationship between
more sources and better data, common sense does suggest that the more
underpinning information we have, the more reliable our output will be.
Therefore, we can track and communicate measures like the above, which
reflect the amount of scrutiny that a person's career has been given by
researchers. The more systematically scrutinised a person's record, as
reflected by the size and contents of the underpinning biocluster, the
more likely their record is to be more reliable. Conversely, records
with no or small underpinning bioclusters may signal an opportunity to a
researcher to search for new information to improve that person's
Register record.

## Concluding thoughts

At a first glance, it might seem that our process is quite circuitous.
For example, suppose you find evidence that the date of birth for a
player is listed incorrectly on B-R. The first instinct is this should
be easy to do: just type in the new DOB in "the database" and it would
appear instantly, just like an edit on Wikipedia would. We hope the
discussion has convinced you why that wouldn't be a sustainable way to
provide the most accurate information, and therefore the system doesn't
give the same instant gratification that editing a Wikipedia page does.
In fact, the way our system works, information does go through multiple
steps before it is aggregated and appears in the Register, and then
eventually on B-R, and it can be unpredictable just how long that
process takes.

We believe this downside is more than made up for by the structure of
the process. Notice that each individual step in the process is easy to
do. It is straightforward to extract information into a structured
format. Matching a pair of source records to record a link is easy. The
clustering is fully automated. And, each individual biocluster can be
reviewed on its own and linked to the Register. Each step is a
bite-sized chunk, and each step is completely separate from the other. A
record can be coded by one researcher, linked by another, and then the
resulting biocluster reviewed by a third, or can be done by the same
person at different points in time. The project has benefitted, and we
hope always will benefit, from the work of some stalwart, yeoman
researchers who have worked on the records of thousands of people. Our
system also makes it possible for people to make small contributions as
well: it lets us aggregate all those small and distributed contributions
into a coherent and reliable whole.

## Acknowledgements

The definition of our project is inspired by the role Lee Allen played
in the production of the original Macmillan Baseball Encyclopedia, in
particular the importance of linking to non-baseball sources to
establish identification; we see the Register as being the successor to
his efforts, and of many subsequent researchers, and our methodology is
the translation of the research methods of ICI on the original
encyclopedia to take advantage of modern computing technology and
algorithmic techniques.

Our approach to bioclustering and the assignment of persistent
identifiers was heavily influenced by the Virtual International
Authority File (VIAF), including the description of their process in
Hickey and Toves, 'Managing Ambiguity in VIAF',
<http://dlib.org/dlib/july14/hickey/07hickey.html>.

Jack Morris has provided helpful comments on previous drafts of this
document and other related materials related to the methodology. He is
also the source of the sample records used in this document (and many,
many other records as well).

[^1]: A favorite example is that Slippery Rock University had two
    players named Mike Sikorski, one who started playing the year
    immediately after the other graduated; and furthermore both went on
    to play in the Frontier League. In a population of 1m people,
    coincidences like this happen frequently.

[^2]: See for example <https://en.wikipedia.org/wiki/Record_linkage> for
    a semi-technical overview.

[^3]: For the more technically minded: This is a problem in graph
    theory, where the nodes in the graph are individual source records
    and the **same** links are edges; we then enumerate all of the
    connected components in the graph. It is also computationally
    efficient to update these components as we add new records and new
    links, so this scales up well.

[^4]: This avoids having digits and letters which can be mis-read for
    each other, and avoiding the vowels means we won't randomly generate
    words.
