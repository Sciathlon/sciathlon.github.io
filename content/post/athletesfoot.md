---
title: "Athlete's foot and its treatment"
date: 2018-06-05T20:55:49+02:00
draft: false
tags: ["Pubmed", "Health", "infection", "fungi", "bioinformatics", "data analysis", "clinical trial"]
---

Today we will be looking at data about a health issue that
affects many athletes: athlete's foot. It's not a very glamorous subject
but it's still interesting, as fungi
are warrior eukaryotes that survive everywhere. Athlete's foot is generally a fungal infection on the feet referred
to as "tinea pedis" but can be something else that causes inflammation
on the foot, however the definitions vary according to who
you talk to... I am going to stick to the more accepted definition which
is the fungal infection. It can happen to all kinds of different
athletes in various sports: tennis, running, martial arts, swimming...
The reason it appears on feet very often is because it is a hot and humid
region of the body where our sweat gets trapped, creating the perfect
environment for fungi. The infection can persist for years if not
treated, can be reoccuring and is often misdiagnosed. It is also easy to
mistake for something else and athletes won't notice until it gets
pretty bad. [This
article](http://cochranelibrary-wiley.com/doi/10.1002/14651858.CD003584.pub2/abstract;jsessionid=AE95E5871D19B79AF274398319206B9B.f04t02)
stated in 2012 that about 15% of the world population could be affected. So that's one reason to be
mindful of our hygiene when we work out. Since I don't know too much
about it, I decided to look a bit more at what research can tell us
about it.

I am going to scrape the pubmed database first as I did in [this post
about
triathlon](https://sciathlon.github.io/post/triathlon_pubmed_analysis/).
Then I am going to look a bit closer at the medication that we can use
to treat it, see how it works from a biological point of view and look
at a clinical trial of one of the most common topical treatments
prescribed.

Pubmed database article scraping
================================

Sending the query
-----------------

The API I am using with the
[RISmed](https://cran.r-project.org/web/packages/RISmed/RISmed.pdf)
package sends a query to Pubmed depending on the criteria you want.
Those include start and finish date, date type, type of search, and
subject.

Number of publications mentioning "athlete's foot" from 2000-2017
-----------------------------------------------------------------

There are 855 articles that have been published about athlete's foot on
the pubmed database total since the year 2000, which is more than I
expected. The standard deviation for the number of articles published in
successive years is 5.9160798 which is not very much variation compared
to other subjects I've searched for recently, but maybe it's because it's a medical subject. The plot showing the
evolution of the number of publications is below:

![](../athleteFoot_files/figure-markdown_strict/unnamed-chunk-3-1.png)

It started off at very few publications, only 30 in the year 2000 then
became a little more popular until 2003 when it decreased. Apparently
scientists took interest in it a bit more after 2010 and it's been
somewhat stable since with its highest at 64 in 2016. It's not a crazy
popular subject on pubmed, probably because it's not a subject that gets
financed a lot. 

Most publishing journals on the subject
=======================================

Here are the top 10 most publishing journals:

![](../athleteFoot_files/figure-markdown_strict/unnamed-chunk-4-1.png)

The journals that publish most are the ones on dermatology. There are
also some specifically on fungal infections with at the very top
[Mycoses](https://onlinelibrary.wiley.com/journal/14390507), a german
journal that started in the 50s.

Top authors diversity and specialty
-----------------------------------

I wanted to see if there is a big variety of authors writing on the
subject so I pulled them up. There are 2894 different authors with the
most publishing author having done 23. The mean number of articles
published by an author on the subject is 1.2753974 so most authors have
published only one article on the subject, so they are
probably usually publishing on other fungal infections or skin diseases.

Most used words in abstracts over the years and in titles
---------------------------------------------------------

We are now going to look at the 10 most used words in abstracts over the
years in the table below in different years:

<table>
<thead>
<tr class="header">
<th align="right">year</th>
<th align="left">words</th>
<th align="right">freq</th>
<th align="right">nPub</th>
<th align="right">year</th>
<th align="left">words</th>
<th align="right">freq</th>
<th align="right">nPub</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="right">2000</td>
<td align="left">tinea</td>
<td align="right">98</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">tinea</td>
<td align="right">84</td>
<td align="right">50</td>
</tr>
<tr class="even">
<td align="right">2000</td>
<td align="left">pedis</td>
<td align="right">53</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">patients</td>
<td align="right">46</td>
<td align="right">50</td>
</tr>
<tr class="odd">
<td align="right">2000</td>
<td align="left">patients</td>
<td align="right">38</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">study</td>
<td align="right">45</td>
<td align="right">50</td>
</tr>
<tr class="even">
<td align="right">2000</td>
<td align="left">trichophyton</td>
<td align="right">32</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">pedis</td>
<td align="right">41</td>
<td align="right">50</td>
</tr>
<tr class="odd">
<td align="right">2000</td>
<td align="left">onychomycosis</td>
<td align="right">26</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">rate</td>
<td align="right">32</td>
<td align="right">50</td>
</tr>
<tr class="even">
<td align="right">2000</td>
<td align="left">treatment</td>
<td align="right">18</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">t</td>
<td align="right">29</td>
<td align="right">50</td>
</tr>
<tr class="odd">
<td align="right">2000</td>
<td align="left">clinical</td>
<td align="right">16</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">clinical</td>
<td align="right">28</td>
<td align="right">50</td>
</tr>
<tr class="even">
<td align="right">2000</td>
<td align="left">skin</td>
<td align="right">16</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">athletes</td>
<td align="right">27</td>
<td align="right">50</td>
</tr>
<tr class="odd">
<td align="right">2000</td>
<td align="left">after</td>
<td align="right">15</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">foot</td>
<td align="right">27</td>
<td align="right">50</td>
</tr>
<tr class="even">
<td align="right">2000</td>
<td align="left">prevalence</td>
<td align="right">15</td>
<td align="right">30</td>
<td align="right">2017</td>
<td align="left">nfl</td>
<td align="right">25</td>
<td align="right">50</td>
</tr>
</tbody>
</table>

A lot of the top words have remained the same throughout the years. The
first thing to notice is tinea is the top word, so it is the fungal
infection that is most studied on the subject of athelte's foot. A
couple other words that are dissimilar attract my attention: in 2000 we
had "prevalence", so they focused on what science can teach us to
prevent it from happening together, but not as much as "treatment" which
is mentioned more. We also have "onychomycosis" which is tinea unguium
and "Trichophyton" which is the name of the genus which contains the
tinea fungus. This explains why tinea and pedis were not mentioned at
the same frequency, because there are several types of tinea infections.
This is because it happens that when the foot is infected, the hands can
also be affected, as well as other areas of the body. In 2017 the
interesting word is "nfl", national football league", which is American
football. This shows that this sport is the one for which the subject
sparked the interest of scientists.

Let's see if the use of these top 10 words evolved over time in this
next plot (frequency normalized by number of articles published each
year):

![](../athleteFoot_files/figure-markdown_strict/unnamed-chunk-7-1.png)

Most of the words are not changing in their frequency of use, they are
right at or below 1 mention per article. Then there is tinea which is
being mentioned less and less throughout the years.

WordCloud of the most common words
----------------------------------

The wordcloud is one of my favorite figures to generate with R and I
frequently generate them for my amused colleagues at work.

![](../athleteFoot_files/figure-markdown_strict/unnamed-chunk-8-1.png)

Fungi, bacteria, shoes?
=======================

I wanted to see in which context more precisely athlete's foot articles
are published, so I'm checking for specifically certain words in the
title:

Let's look at the number of titles with certain keywords in them:

<table>
<thead>
<tr class="header">
<th>//</th>
<th>total</th>
<th>fungi</th>
<th>bacteria</th>
<th>shoes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>number of articles</td>
<td>853</td>
<td>138</td>
<td>57</td>
<td>28</td>
</tr>
</tbody>
</table>

Medication for athlete's foot
=============================

Some of the most common tinea pedis fungi are trichophyton, microsporum
and epidermophyla according to [this
website](http://www.patientcareonline.com/infection/differentiating-types-tinea)
and with a quick search on Pubmed's [taxonomy
search](https://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi?mode=Tree&id=34384&lvl=3&keep=1&srchmode=1&unlock),
I found that they are Arthrodermataceae. There are many different
options that treat athlete's foot, usually topical creams, and oral
treatments. [This clinical trial
article](https://www.mdedge.com/cutis/article/148474/hair-nails/clinical-trial-designs-topical-antifungal-treatments-onychomycosis)
states that there are 3 topical treatments that are used:

-   tavaborole

-   efinaconazole

-   ciclopirox

Understanding the tavaboroles' action and possible adverse effects
==================================================================

As a biologist, I always look up clinical trials on the medication I've
been prescribed, I also
check how these chemicals actually work. If you wanted to know how to do
that as well, let's take the example of tavaborole.

The clinical trial I mentioned in the section above is about tavaborole.
What you look for in this study is the number of people involved
(treated and control), and whether it is randowmized, blind, or double
blind (neither patient nor doctor know who has the treatment and who has
the placebo). A clinical trial protocol can become very complicated
depending on the product tested, but for medication like a pill or
cream it is fairly straightforward. Make sure to check the primary and secondary
goals stated, because they are not always the same from study to study.
Clinical trials have different purposes: getting rid of symptoms, a
prevention of worsening of a condition, a lack of adversary effects...
Here the primary goal is "completely cure the nail infection". They
explain that this means no visible fungi. In the secondary goals you
also have "negative fungal culture". Then you can look at the results of
the study which show here a clear difference between the treatment and
the placebo, but I am still surprised at the number of failures with the
actual treatment:

![](../athleteFoot_files/figure-markdown_strict/unnamed-chunk-11-1.png)

I think it's possible that they didn't work on all infections because
the species of fungi were different and maybe some aren't
sensitive to this particular treatment because they have a variant of
the protein.

What is also important to look at is also the statistical method they
used to determine whether there is an effect or not. Here they used the
[Cochran-Mantel-Haenszel](https://en.wikipedia.org/wiki/Cochran%E2%80%93Mantel%E2%80%93Haenszel_statistics)
method for a test of superiority, which is very typical for this kind of
study.

I also wanted to know how the medication works biologically speaking. I
did a quick search on
[wikipedia](https://en.wikipedia.org/wiki/Tavaborole) and found that it
inhibits leucyl-tRNA synthetase, a protein that is important for protein
synthesis in the fungi. This protein also exists in humans. If they are
really similar and their target exists in both fungi and humans, this
could mean adverse effects. I then went on
[Pubmed](https://www.ncbi.nlm.nih.gov/pubmed) and searched for the human version of the protein. If you
scroll down on the [page](https://www.ncbi.nlm.nih.gov/gene/51520) and
go down you will find a lot of information about where it is expressed
and the expression levels (you will notice it is expressed in the skin
for example), as well as much more information. I scrolled down to
"protein interaction" and did the same thing for a fungi version of the
gene, but there wasn't as much information unfortunately so I couldn't
compare. By pulling up the DNA sequence I can already tell the proteins
are very different. I did a quick alignment and I got no result. I will
get more into details for this kind of work in an upcoming article, I
want to do it justice.

Lastly, I looked for articles that talk about Tavaborole and found [this
gem](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5753160/) which
compares the 3 treatments I quoted above. They found that tavaborole is
actually fungistatic in keratin-containing medium, meaning it prevents
further growth of fungi. This is incredible! In the presence of keratin,
a protein found in nails, tavaborole is actually only fungistatic! This
explains the mild results of the clinical study above. I encourage you
to read the article which is free, if you're interested.

Sciathlete
