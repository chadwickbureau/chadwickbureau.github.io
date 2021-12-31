---
title: About our historical data
---

The origin of our data on professional baseball outside of the Major Leagues is a 
mashup of a number of secondary datasets produced over the years by various researchers.
In most cases, these datasets focused on information of interest to the researcher,
and therefore focused on particular leagues, people, and/or types of information.
By combining them, we have been able to produce a first cut at an encyclopedic
dataset which has broad coverage of much of baseball history.

The resulting mashup is useful, but very incomplete.  The limited scope of each
individual secondary dataset means there are many gaps in coverage.
Furthermore, because the datasets were produced to solve a particular need for
the researcher, and not necessarily to be part of a systematic encyclopedia,
information on the provenance of specific datapoints varies significantly across
the datasets.  Although our experience is the information in our dataset is
generally reliable when it is present, it is generally not possible to identify
a primary source for most of it.  And, when a data point is null (or absent)
in our data, it is difficult to say whether this is because the information
was not ever recorded, or simply was not recorded in one of the secondary
datasets.

We have therefore constructed a strategy for developing the dataset into
a truly encyclopedic resource with both depth and breadth.
In contrast to our underpinning secondary datasets, which are generally topic-organised,
we organise our work by **source**.  That is to say, when we work with a given source,
we extract and index **all** of the information present in the source.
Because we want our dataset to be comprehensive, this is a very efficient way of
ingesting data.  The trade-off is that, in general, we do not go in search of
trying to "fill in" a given data point.  For example, if we do not have a date of
birth for Joe Shlabotnik, we don't in general go trying to find it; instead, we
systematically index sources (such as, for example, media guides or official rosters),
and at some point we are likely to find Shlabotnik's birthday if it was recorded
somewhere.

Working in this way has several benefits:
* It naturally produces a form of audit trail that allows us to trace every
  piece of information we add to its source.  We have a [separate semi-technical
  introduction](bioclusters) which describes how we link together references
  to the same person from different sources to build up their profile in our
  data.
* We can work efficiently by knowing which sources have been used, and which have
  not.  If we looked only for information of a given type, we might wind up
  consulting the same source many times over - or we might not realise that a
  source contains other useful information.  We've found that it is not uncommon
  for a piece of information in a source to turn out to be a useful clue in
  confirming or linking information in other sources.
  
As a result of our approach, we do not think of ourselves as making "changes" or
"revisions" to our data.  Rather, what we are doing is **replacing** the data
which originates from the underpinning secondary sources, with data produced
more systematically from primary sources.  We do this in a way that maintains
continuity, so from the perspective of data users, information simply becomes
gradually more complete over time.  However, what is more important - even if
less visible - is that over time our data is becoming more and more
**reproducible**, that is, traceable from original sources.  This is what is
essential for ensuring data quality.

## Our plans for 2022

We have several lines of work in progress in which we are systematically working
through several key types of sources.  Here is what we expect will happen as
2022 progresses.

### League statistics

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

As of the start of 2022, we have completed all leagues from 1953 forward,
with the exception of a small number of leagues in 1953 and 1954, and some
leagues based in Mexico which were part of the National Association.
At our current rate of progress, we anticipate that by the end of 2022 we will
complete the "replacement" of statistics with more systematically-built versions
for all leagues from the early 1940s to present.

### Linking Sporting News contract cards

The _Sporting News_ contract cards, available on the LA84 Foundation's website,
are proving to be a useful resource.  The cards contain interesting data ranging
roughly from 1920 to 1980, with some limited or sketchy information in the 1910s,
and cards for most Major League players prior to 1920.

The content of the cards varies widely.  Some players who played just a few minor
league games (or were signed but never played at all) have very complete information,
while many with significant minor league careers have little information beyond
their name and a list of transactions.  We are finding that a majority of the cards
do have some information which is useful for improving our data quality.

We are working through indexing these systematically, one card at a time.  This is much more
efficient than trying to search for a card matching a Register entry.  The OCR of
the cards is quite good, but the search facility on LA84 looks for exact word
matches only; therefore, it would be difficult to find a card if the OCR was not
accurate, or if a name was spelled differently on the card.
The cards are also not organised chronologically.

Because of the breadth of coverage of this source, we are making matching cards
to Register people a high priority.  However, because the cards are not organised
chronologically, the improvements to data quality will be incremental and scattered
across the decades.

This is a large project that will take several years to complete.  In the meanwhile,
as we match cards to Register entries, a link to the card(s) matched will appear
on the person's corresponding page on baseball-reference.com.


### Indexing player profiles

We have a number of career profiles of individual people which several researchers
have generously provided to us.  For example, Bob McConnell allowed us in 2008
to scan [his profiles of over 1300 major and minor league players](https://www.dropbox.com/sh/rntugcqba320uau/AAAVXoRuZ87axOS2R8MvMvr1a?dl=0).
Reed Howard, our 19th century stalwart researcher, has produced an
[extensive register of people from baseball's earlier years](/reports/howard).
Likewise, similar types of career profiles appear in official media guides produced
by teams and leagues.

We are currently indexing and matching these to the Register.  In 2022 we are focusing
first on researcher-produced profiles.  Our reasoning is that a researcher profiles a person
because the person is of interest for some reason.  Therefore, it is more likely that a
data user would also have an interest in that person's profile in our data, and so prioritising
improving the quality of that data seems sensible.


### Player questionnaires

For many years it was customary for data compilers to ask players to fill out standard
questionnaires with biographical information.  Many of these have been collected and
scanned, and are now available on ancestry.com.  In 2022 we are beginning a new index
of these, linking and merging them to Register person entries.  We anticipate this will be
an interesting data source: although the coverage is of a much smaller population than,
for example, the contract cards, the information in them will be much more complete,
especially as regards full names, dates and places of birth, and schools attended.


### Data from outside baseball: The Lee Allen group

Running in parallel to these, we are working with what we call the
[Lee Allen group](/doc/leeallen).  This is an informal network of researchers who collect
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

