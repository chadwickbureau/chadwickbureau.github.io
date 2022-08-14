---
title: About historical minor league data
---

At the moment, the data on professional baseball outside of the Major Leagues, as seen,
for example, on baseball-reference.com, is a mashup which combines a  number of secondary
datasets produced over the years by various researchers.
Most of these datasets focused on information of interest to the researcher,
and therefore their coverage was targeted to particular leagues, people, and/or types of
information.
By combining them, we have been able to produce a first cut at an encyclopedic
dataset which has broad coverage of much of baseball history.

The resulting mashup is useful, but very incomplete.  The limited scope of each
individual secondary dataset means there are many, many gaps in coverage.
Furthermore, because the datasets were produced to solve a particular need for
the researcher, and not necessarily to be part of a systematic encyclopedia,
information on the provenance of specific datapoints varies significantly across
the datasets.  Although our experience is the information in our dataset is
generally reliable when it is present, it is generally not possible to identify
a primary source for most of it.  And, when a data point is null (or absent)
in our data, it is difficult to say whether this is because the information
was not ever recorded, or simply was not recorded in one of the secondary
datasets.

We are now building a new, comprehensive dataset covering the history of
professional baseball.
We find ourselves in a situation that is quite similar to that faced by ICI
when they started to produce the dataset that became the original Macmillan
Baseball Encyclopedia, and we are following a strategy which in many ways is
the same as the one they adopted.
We are going back to the most primary sources we can find, and building a
new dataset "from scratch," where each datapoint is traceable back to
a source.
Of course, we are benefitting greatly from the massive progress that has been
made in computer hardware, and in software for organising, transforming, and
merging large datasets, in the half a century since the Macmillan
appeared, but in many ways our research principles and strategy would
be instantly recognisable to anyone who worked on the Big Mac.

One important difference between the late 1960s and today is that dissemination
of data is so much faster.
Although the Macmillan Encycloepdia was famously the first book to be typeset
by computer, it took hours to do the typesetting, and of course the only way
to disseminate the information was by printing physical books.
Today, we are able to update websites in minutes, or seconds, and people
can interact with the data in a variety of ways.
Therefore, unlike ICI, we do not need to wait to complete our work to publish
it; rather we can disseminate new information on a rolling basis.

To accomplish this in an efficient fashion, we have developed a structured
approach to building our new dataset.  We organise our work into well-defined
blocks, and when each block is ready, it is merged into the dataset and
disseminated.  We do this in a way that maintains continuity for all of
the identifiers associated with people, leagues, teams, and so on, so
this updating process should largely be transparent to users: over time, the
quality of the data simply gets better.  The way to think about this
process is that we are not "changing" or "editing" the legacy mashup
data; we are **replacing it block by block**, with a new dataset that is
built directly from sources, and that we are able to improve iteratively
going forward as we incorporate new sources of information.


# Our strategy

To produce a dataset of this size efficiently requires having a good way
of organising work into coherent blocks we can use to replace chunks of
existing information.  We provide below a high-level outline of our strategy.


## League statistics

We work with a given league-season as the unit of statistical compilation.
Most of the historical statistics in the original mashup came from an impressive
database compiled by Ed Washuta.  Ed's work was comprehensive in breadth, going
back to 1901, but limited in the statistical columns it covered.

We are currently working backwards in time (similar to Retrosheet), replacing
the statistical coverage from Ed's dataset.  For each league-season, we identify
the most complete source(s) for league-level performance.  Often, the official
averages published by the league (and frequently appearing in, e.g., a Guide)
is the best existing source.  In some cases, we also have work done by researchers
which provides averages for leagues which did not publish them, or which improves
on what was published by adding missing players (including "less-thans"),
additional statistical detail, or correcting errors in statistical tabulation or
person names.

As a further stage, we have developed a methodology for efficiently capturing
from newspapers boxscores, game logs, and identifying information on individual players.
We use this methodology to fill in additional information for a league,
especially for leagues where official averages were not published, or were sketchy
or otherwise clearly unreliable.
We produce updated versions of a league-season at the league-season level; this
means that, until we have worked through a league-season completely, it is possible
(and in some situations probable) that player lists or statistical totals
for that league-season are incomplete.


## Person identification

Players, managers, and other personnel are usually incompletely identified in
published averages and in newspaper accounts.
To link up each person's baseball career, and to fill in additional identifying
and biographical details, we have developed a structured approach for establishing
identification based on principles from records linkage, to develop the
person identifications in the Chadwick Register.

The backbone of our identification strategy is to link among several of the most
comprehensive collections of information on people:

* The _Sporting News_ contract cards, available on the LA84 Foundation's website,
  contain useful data on players and other personnel active from about 1920 to 1980,
  with some limited or sketchy information in the 1910s.
  The content of the cards varies widely.  Some players who played just a few minor
  league games (or were signed but never played at all) have very complete information,
  while many with significant minor league careers have little information beyond
  their name and a list of transactions.  We are finding that a majority of the cards
  do have some information which is useful for improving our data quality.
* Thanks to a partnership with Baseball Reference, we are indexing and abstracting
  information from the questionnaires which have been scanned and are available on
  ancestry.com.  These documents are quite useful for filling in basic biographical
  details, and especially schools attended (which are rarely recorded systematically).
* Thanks to Pete Palmer, we have an improved version of the person biographical table
  from the Howe Sports Bureau, with coverage from the early 1980s to the early 2000s.
* Stalwart 19th century baseball researcher Reed Howard has contributed an extensive
  listing of the careers and biographical details for players and other personnel
  from the 1860s through to the early 20th century, with source citations.
  
Taken together, the above give us coverage across all of baseball history.  We are
now matching and cross-linking these listings with each other, as well as with the
league averages we produced as described above.  This is a process which will take
several years to complete fully, as there are several hundred thousand records to
be transcribed and collated - for example, there are over 170,000 contract cards alone.
In the meanwhile, an important output of the process is that we will be able to
provide source links for more and more person entries.  For example,
where we have linked a person to a contract card, Baseball Reference displays 
link(s) to their corresponding card(s) on the person's page.

The person details we can glean from the above sources are often still incomplete.
One of the achievements of the Macmillan Encyclopedia was not just getting historical
statistics organised and checked, but also providing biographical details for players
on a much more systematic basis.
The core of that information was information that had been collected over the years
by Lee Allen, who was the historian at the Hall of Fame in the 1960s and who had a
special interest in knowing details about Major League players' lives outside of baseball.
To collect this type of information for our Register, we have formed what we call the
[Lee Allen group](/doc/leeallen), an informal network of researchers who collect
data on baseball people using sources from outside baseball, including obituaries, vital
records, and the like.  This group is responsible for reporting the passings of former
players and personnel in near-real time.  In addition, once we have linked contract cards,
profiles, or questionnaires to Register people, but information on them is still missing,
they have a go at seeing if they can find information from other sources to fill out
demographics in the Register.


## Summary

Our historical data will always be incomplete and a work in progress.  We estimate that
at least 250,000 people have played at least one game in one of the over 5,000 seasons
played in a professional league.  The incompleteness of sources - not to mention the
errors and ambiguities within and across sources - will always be limitations, as well as
the sheer amount of work it takes to organise the information scattered across those
sources.  It should be noted that almost all of the work in producing historical data
prior to 1984 is being done by volunteer researchers; without their generosity with
their time and talents, very little of the work described above would happen.

The description above gives an idea of what a data user can expect of our historical
data, what our roadmap is for developing it, and what reasonable timelines are for
how that development will happen.

We are always looking for new researchers to support the projects we are working on.
We know our approach of working systematically through a given source does not appeal
to everyone, but we find it rewarding to see the quality of our data improve day
by day.  If you think you might be interested in participating, please do get in touch.
Our system is designed such that we can efficiently incorporate contributions of both
small and large amounts of work - so it is possible to make useful contributions with
just a few hours of work here and there.

