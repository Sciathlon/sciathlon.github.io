---
title: "R figure skating analysis"
date: 2018-01-20T12:55:16+01:00
draft: false
tag: ["figure skating", "R", "data science", "Olympics"]
---

Analysing medals won per athlete/per country with R
===================================================

As I am learning data science by doing little projects, today I am introducing a little data analysis using
[R](https://www.r-project.org/) on figure skating in the Olympics. I am going to look at the
medals won using data from the [official Olympics database
website](http://www.olympiandatabase.com). First I formatted the data to
make it a csv (comma separated values) file which is very easy to parse
in R

Total number of athletes that have won at least a medal per country
-------------------------------------------------------------------

![](../Analysis_medal_per_athlete_files/figure-markdown_strict/unnamed-chunk-1-1.png)

This first plot represents the total number of medals per country over
all the years they participated. Figure skating has been part of the
winter Games since the beginning but not all nations have participated
since the start, and some countries don't exist any more but they are
still represented under their official name of the time, for example the
USSR. Looking at the plot, the first thing we notice are the highest
scoring nations: USA, Russia (both modern and USSR with the code USR),
Canada, Austria. Let's dig deeper into what kind of medals each country
mostly wins to see if certain countries are better:

Number of gold medals per country
---------------------------------

![](../Analysis_medal_per_athlete_files/figure-markdown_strict/unnamed-chunk-2-1.png)

Here we see a clear difference with the previous plot: Russia clearly
dominates the sport, more than twice the amount compared to any other
country if you count Russia+USSR wins. My own country, France, is pretty
low in that plot (we are great at the dance category though). Another thing I noted is Canada is not doing as well as I'd imagined
well, which I was surprised about. Now let's zoom in on the athletes
that are so good they won multiple times:

Athletes that have won multiple times
-------------------------------------

<table>
<thead>
<tr class="header">
<th align="right">rank</th>
<th align="left">Athlete</th>
<th align="left">NationID</th>
<th align="right">G</th>
<th align="right">S</th>
<th align="right">B</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="right">1</td>
<td align="left">Gillis GrafstrÃ¶m</td>
<td align="left">SWE</td>
<td align="right">3</td>
<td align="right">1</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">2</td>
<td align="left">Sonja Henie</td>
<td align="left">NOR</td>
<td align="right">3</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">2</td>
<td align="left">Irina Rodnina</td>
<td align="left">URS</td>
<td align="right">3</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">4</td>
<td align="left">Yevgeny Plushenko</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">2</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">5</td>
<td align="left">Artur Dmitriev</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">1</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">6</td>
<td align="left">Andree Brunet</td>
<td align="left">FRA</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">1</td>
</tr>
<tr class="odd">
<td align="right">6</td>
<td align="left">Pierre Brunet</td>
<td align="left">FRA</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">1</td>
</tr>
<tr class="even">
<td align="right">8</td>
<td align="left">Yekaterina Gordeyeva</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">8</td>
<td align="left">Aleksandr Zaitsev</td>
<td align="left">URS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">8</td>
<td align="left">Maxim Trankov</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">8</td>
<td align="left">Oksana Grishuk</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">8</td>
<td align="left">Lyudmila Belousova</td>
<td align="left">URS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">8</td>
<td align="left">Richard Button</td>
<td align="left">USA</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">8</td>
<td align="left">Sergei Grinkov</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">8</td>
<td align="left">Katarina Witt</td>
<td align="left">GDR</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">8</td>
<td align="left">Tatiana Volosozhar</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">8</td>
<td align="left">Yevgeny Platov</td>
<td align="left">RUS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td align="right">8</td>
<td align="left">Oleg Protopopov</td>
<td align="left">URS</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td align="right">8</td>
<td align="left">Karl SchÃ¤fer</td>
<td align="left">AUT</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">0</td>
</tr>
</tbody>
</table>

Most of those on the list are Russian, but number
1 and 2 are from Sweden and Norway. Gillis Grafström is the most
successful skater at the olympics, but passed away in 1938. Norwegian
Sonja Henie was also a very successful skater and celebrity and left us
in 1969. Irina Rodnina is retired from competition and is now doing
politics.

French athletes with medals
---------------------------

Since I am french and I used to skate in France, I'm very interested in
how we did over the years so here are all the french athletes who have
won at least a medal in the order they are scored according to how many
and which color their medals were.

<table>
<thead>
<tr class="header">
<th></th>
<th align="right">rank</th>
<th align="left">Athlete</th>
<th align="left">NationID</th>
<th align="right">G</th>
<th align="right">S</th>
<th align="right">B</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>6</td>
<td align="right">6</td>
<td align="left">Andree Brunet</td>
<td align="left">FRA</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">1</td>
</tr>
<tr class="even">
<td>7</td>
<td align="right">6</td>
<td align="left">Pierre Brunet</td>
<td align="left">FRA</td>
<td align="right">2</td>
<td align="right">0</td>
<td align="right">1</td>
</tr>
<tr class="odd">
<td>43</td>
<td align="right">43</td>
<td align="left">Gwendal Peizerat</td>
<td align="left">FRA</td>
<td align="right">1</td>
<td align="right">0</td>
<td align="right">1</td>
</tr>
<tr class="even">
<td>48</td>
<td align="right">43</td>
<td align="left">Marina Anissina</td>
<td align="left">FRA</td>
<td align="right">1</td>
<td align="right">0</td>
<td align="right">1</td>
</tr>
<tr class="odd">
<td>138</td>
<td align="right">126</td>
<td align="left">Paul Duchesnay</td>
<td align="left">FRA</td>
<td align="right">0</td>
<td align="right">1</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td>173</td>
<td align="right">126</td>
<td align="left">Isabelle Duchesnay-Dean</td>
<td align="left">FRA</td>
<td align="right">0</td>
<td align="right">1</td>
<td align="right">0</td>
</tr>
<tr class="odd">
<td>190</td>
<td align="right">126</td>
<td align="left">Alain Calmat</td>
<td align="left">FRA</td>
<td align="right">0</td>
<td align="right">1</td>
<td align="right">0</td>
</tr>
<tr class="even">
<td>207</td>
<td align="right">201</td>
<td align="left">Philippe Candeloro</td>
<td align="left">FRA</td>
<td align="right">0</td>
<td align="right">0</td>
<td align="right">2</td>
</tr>
<tr class="odd">
<td>212</td>
<td align="right">201</td>
<td align="left">Patrick Pera</td>
<td align="left">FRA</td>
<td align="right">0</td>
<td align="right">0</td>
<td align="right">2</td>
</tr>
<tr class="even">
<td>266</td>
<td align="right">214</td>
<td align="left">Jacqueline du Bief</td>
<td align="left">FRA</td>
<td align="right">0</td>
<td align="right">0</td>
<td align="right">1</td>
</tr>
</tbody>
</table>

We have 10 french athletes who have won medals in history, and when
I started skating it was when the Marina and Gwendal couple were very
famous and I wanted to be like them. Andree and Pierre Brunet
were also a very famous couple and revolutionized the sport at the time,
they are proper legends. Let's look at those athletes who don't get as much attention,
the ones who have not won the olympics:

Athletes who have not won a gold medal
--------------------------------------

![](../Analysis_medal_per_athlete_files/figure-markdown_strict/unnamed-chunk-5-1.png)

We notice that there is a very high number of athletes from USA who
never won gold, more than in any country. However we know they also
enter the highest number of athletes because they have the budget to
send as many athletes as possible and not just the ones they know will
win. To showcase that more, let's look at the
proportions of winning athletes per country:

![](../Analysis_medal_per_athlete_files/figure-markdown_strict/unnamed-chunk-6-1.png)

Some countries have very few
medal winning athletes, Korea has only one athlete that won medals and
she won gold once, and Finland has had 2 that also both won so they both
have a 100% win rate of medal winning athletes, which tells us a little about their strategy: send only the ones who can win. Otherwize Russia, of course, and its close
neighbour Belarus have the highest proportion of gold medals per
medal-winning athlete.

Best scoring athletes at the olympics
-------------------------------------

I am using a different database here which is from the ISU
([International skating Union](http://www.isu.org/statistics)) and holds
all the personal best of athletes. Because this article is about the
olympics, I will focus on athletes that have had their personal best at
Olympic events. This is biased in the sense that not all athletes have
their personal Best during an Olympic event, because it's so much
pressure it can be difficult to do your best, but as I am interested in
what happens at an Olympic event, I think it's fitting to use this set
of data. This data represents athletes that do their best in this event.

### Ladies' performances

    ## Parsed with column specification:
    ## cols(
    ##   rank = col_integer(),
    ##   Name = col_character(),
    ##   NationID = col_character(),
    ##   Event = col_character(),
    ##   Date = col_character(),
    ##   Score = col_double(),
    ##   Category = col_character()
    ## )

<table>
<thead>
<tr class="header">
<th></th>
<th align="right">rank</th>
<th align="left">Name</th>
<th align="left">NationID</th>
<th align="left">Event</th>
<th align="left">Date</th>
<th align="right">Score</th>
<th align="left">Category</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>2</td>
<td align="right">2</td>
<td align="left">Yuna KIM</td>
<td align="left">KOR</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">25.02.2010</td>
<td align="right">228.56</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>3</td>
<td align="right">3</td>
<td align="left">Adelina SOTNIKOVA</td>
<td align="left">RUS</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">224.59</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>9</td>
<td align="right">9</td>
<td align="left">Carolina KOSTNER</td>
<td align="left">ITA</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">216.73</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>24</td>
<td align="right">24</td>
<td align="left">Joannie ROCHETTE</td>
<td align="left">CAN</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">25.02.2010</td>
<td align="right">202.64</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>46</td>
<td align="right">46</td>
<td align="left">Shizuka ARAKAWA</td>
<td align="left">JPN</td>
<td align="left">XX Olympic Winter Games 2006</td>
<td align="left">23.02.2006</td>
<td align="right">191.34</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>52</td>
<td align="right">52</td>
<td align="left">Laura LEPISTÖ</td>
<td align="left">FIN</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">25.02.2010</td>
<td align="right">187.97</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>64</td>
<td align="right">64</td>
<td align="left">Rachael FLATT</td>
<td align="left">USA</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">25.02.2010</td>
<td align="right">182.49</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>87</td>
<td align="right">87</td>
<td align="left">Mae Berenice MEITE</td>
<td align="left">FRA</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">174.53</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>89</td>
<td align="right">89</td>
<td align="left">Valentina MARCHEI</td>
<td align="left">ITA</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">173.33</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>95</td>
<td align="right">95</td>
<td align="left">Ksenia MAKAROVA</td>
<td align="left">RUS</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">25.02.2010</td>
<td align="right">171.91</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>119</td>
<td align="right">119</td>
<td align="left">Diana NIKITINA</td>
<td align="left">LAT</td>
<td align="left">Youth Olympic Games 2016</td>
<td align="left">16.02.2016</td>
<td align="right">165.60</td>
<td align="left">J</td>
</tr>
<tr class="even">
<td>174</td>
<td align="right">172</td>
<td align="left">Min-Jeong KWAK</td>
<td align="left">KOR</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">25.02.2010</td>
<td align="right">155.53</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>295</td>
<td align="right">288</td>
<td align="left">Cheltzie LEE</td>
<td align="left">AUS</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">25.02.2010</td>
<td align="right">138.16</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>312</td>
<td align="right">304</td>
<td align="left">Anais VENTARD</td>
<td align="left">FRA</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">17.01.2012</td>
<td align="right">136.08</td>
<td align="left">J</td>
</tr>
<tr class="odd">
<td>316</td>
<td align="right">308</td>
<td align="left">Vanna GIANG</td>
<td align="left">USA</td>
<td align="left">Youth Olympic Games 2016</td>
<td align="left">16.02.2016</td>
<td align="right">135.65</td>
<td align="left">J</td>
</tr>
<tr class="even">
<td>328</td>
<td align="right">320</td>
<td align="left">Lucrezia GENNARO</td>
<td align="left">ITA</td>
<td align="left">Youth Olympic Games 2016</td>
<td align="left">16.02.2016</td>
<td align="right">134.18</td>
<td align="left">J</td>
</tr>
<tr class="odd">
<td>441</td>
<td align="right">430</td>
<td align="left">Jordan BAUTH</td>
<td align="left">USA</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">17.01.2012</td>
<td align="right">123.39</td>
<td align="left">J</td>
</tr>
<tr class="even">
<td>481</td>
<td align="right">468</td>
<td align="left">Silvia FONTANA</td>
<td align="left">ITA</td>
<td align="left">XX Olympic Winter Games 2006</td>
<td align="left">23.02.2006</td>
<td align="right">120.37</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>616</td>
<td align="right">594</td>
<td align="left">Darin KHUSSEIN</td>
<td align="left">UKR</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">17.01.2012</td>
<td align="right">109.31</td>
<td align="left">J</td>
</tr>
<tr class="even">
<td>795</td>
<td align="right">758</td>
<td align="left">Nina Larissa WOLFSLAST</td>
<td align="left">AUT</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">17.01.2012</td>
<td align="right">96.26</td>
<td align="left">J</td>
</tr>
<tr class="odd">
<td>862</td>
<td align="right">818</td>
<td align="left">Myrtel SALDEEN OLOFSSON</td>
<td align="left">SWE</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">17.01.2012</td>
<td align="right">92.54</td>
<td align="left">J</td>
</tr>
<tr class="even">
<td>977</td>
<td align="right">919</td>
<td align="left">Lieselotte SWERTS</td>
<td align="left">BEL</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">17.01.2012</td>
<td align="right">85.57</td>
<td align="left">J</td>
</tr>
</tbody>
</table>

Here is a table of all the athletes competing in the ladie's event at
Olympics and have had their personal best in them. Here they are sorted
by score and the beautiful Korean Yuna Kim is at the top. Adelina
SOTNIKOVA just below her won the last Olympics. Below her, Carolina
KOSTNER is an italian ice skating legend, she has a very unique style.
The french Mae Berenice MEITE is a few spots below, she is very
successful in France and with a very athletic technique, some of her tricks are so dangerous they have been banned from competition.

Let's look at the last games from 2014:

<table>
<thead>
<tr class="header">
<th></th>
<th align="right">rank</th>
<th align="left">Name</th>
<th align="left">NationID</th>
<th align="left">Event</th>
<th align="left">Date</th>
<th align="right">Score</th>
<th align="left">Category</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>3</td>
<td align="right">3</td>
<td align="left">Adelina SOTNIKOVA</td>
<td align="left">RUS</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">224.59</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>9</td>
<td align="right">9</td>
<td align="left">Carolina KOSTNER</td>
<td align="left">ITA</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">216.73</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>87</td>
<td align="right">87</td>
<td align="left">Mae Berenice MEITE</td>
<td align="left">FRA</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">174.53</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>89</td>
<td align="right">89</td>
<td align="left">Valentina MARCHEI</td>
<td align="left">ITA</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">20.02.2014</td>
<td align="right">173.33</td>
<td align="left">S</td>
</tr>
</tbody>
</table>

In the last Olympics, 4 athletes got their career PB, the winner Adelina
SOTNIKOVA, two italians Carolina KOSTNER and Valentina MARCHEI, and ...
our french national winner, Mae Berenice MEITE! We'll see if the 2014
winner can beat her own score this year, I certainly hope for something
spectacular.

    ## Parsed with column specification:
    ## cols(
    ##   rank = col_integer(),
    ##   Name = col_character(),
    ##   NationID = col_character(),
    ##   Event = col_character(),
    ##   Date = col_character(),
    ##   Score = col_double(),
    ##   category = col_character()
    ## )

<table>
<thead>
<tr class="header">
<th></th>
<th align="right">rank</th>
<th align="left">Name</th>
<th align="left">NationID</th>
<th align="left">Event</th>
<th align="left">Date</th>
<th align="right">Score</th>
<th align="left">category</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>24</td>
<td align="right">24</td>
<td align="left">Evan LYSACEK</td>
<td align="left">USA</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">18/02/10</td>
<td align="right">257.67</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>39</td>
<td align="right">39</td>
<td align="left">Stephane LAMBIEL</td>
<td align="left">SUI</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">18/02/10</td>
<td align="right">246.72</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>49</td>
<td align="right">49</td>
<td align="left">Peter LIEBERS</td>
<td align="left">GER</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">14/02/14</td>
<td align="right">239.87</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>52</td>
<td align="right">52</td>
<td align="left">Johnny WEIR</td>
<td align="left">USA</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">18/02/10</td>
<td align="right">238.87</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>62</td>
<td align="right">62</td>
<td align="left">Tomas VERNER</td>
<td align="left">CZE</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">14/02/14</td>
<td align="right">232.99</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>106</td>
<td align="right">106</td>
<td align="left">Artem BORODULIN</td>
<td align="left">RUS</td>
<td align="left">XXI Olympic Winter Games 2010</td>
<td align="left">18/02/10</td>
<td align="right">210.16</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>117</td>
<td align="right">116</td>
<td align="left">Matthew SAVOIE</td>
<td align="left">USA</td>
<td align="left">XX Olympic Winter Games 2006</td>
<td align="left">16/02/06</td>
<td align="right">206.67</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>148</td>
<td align="right">147</td>
<td align="left">Min ZHANG</td>
<td align="left">CHN</td>
<td align="left">XX Olympic Winter Games 2006</td>
<td align="left">16/02/06</td>
<td align="right">196.27</td>
<td align="left">S</td>
</tr>
<tr class="odd">
<td>324</td>
<td align="right">316</td>
<td align="left">Feodosiy EFREMENKOV</td>
<td align="left">RUS</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">16/01/12</td>
<td align="right">163.46</td>
<td align="left">J</td>
</tr>
<tr class="even">
<td>453</td>
<td align="right">439</td>
<td align="left">Timofei NOVAIKIN</td>
<td align="left">FRA</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">16/01/12</td>
<td align="right">147.23</td>
<td align="left">J</td>
</tr>
<tr class="odd">
<td>609</td>
<td align="right">589</td>
<td align="left">John-Olof HALLMAN</td>
<td align="left">SWE</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">16/01/12</td>
<td align="right">120.12</td>
<td align="left">J</td>
</tr>
<tr class="even">
<td>721</td>
<td align="right">697</td>
<td align="left">Alexandr LYAN</td>
<td align="left">KAZ</td>
<td align="left">Youth Olympic Games 2012</td>
<td align="left">16/01/12</td>
<td align="right">95.87</td>
<td align="left">J</td>
</tr>
<tr class="odd">
<td>734</td>
<td align="right">710</td>
<td align="left">Lauri LANKILA</td>
<td align="left">FIN</td>
<td align="left">Youth Olympic Games 2016</td>
<td align="left">15/02/16</td>
<td align="right">92.08</td>
<td align="left">J</td>
</tr>
</tbody>
</table>

For men we have 13 athletes that seem to do their best during Olympics,
from various nationalities.

<table>
<thead>
<tr class="header">
<th></th>
<th align="right">rank</th>
<th align="left">Name</th>
<th align="left">NationID</th>
<th align="left">Event</th>
<th align="left">Date</th>
<th align="right">Score</th>
<th align="left">category</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>49</td>
<td align="right">49</td>
<td align="left">Peter LIEBERS</td>
<td align="left">GER</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">14/02/14</td>
<td align="right">239.87</td>
<td align="left">S</td>
</tr>
<tr class="even">
<td>62</td>
<td align="right">62</td>
<td align="left">Tomas VERNER</td>
<td align="left">CZE</td>
<td align="left">XXII Olympic Winter Games 2014</td>
<td align="left">14/02/14</td>
<td align="right">232.99</td>
<td align="left">S</td>
</tr>
</tbody>
</table>

During the last Olympics however only two men have had their best score
there, German Peter Liebers and Czech Tomas Verner, neither ranking in
the top 10 scores of all time.

That's all for today, I hope this was entertaining! There is still so
much we could do with this data but it'll be for another time!

Sciathlete

Here is the code if you want to have a look:

    #reading csv file
    medalCount <- read.csv(file="./stats_athletes_with_medals_count.csv", header=TRUE, sep=",")
    medalCountdf <- data.frame(medalCount)
    #number of athletes per country that have won at least one medal
    tbl_total_num_athletes_with_medal <- table(medalCountdf$NationID)
    barplot(tbl_total_num_athletes_with_medal, main="Number of medals won per country")
    #Number of gold medals won per country
    tbl_gold <- table(medalCountdf[which(medalCountdf$G!=0),]$NationID)
    barplot(tbl_gold, main="Number of gold medals won per country")
    #table of multiple winning athletes
    multiple_gold_athletes <- medalCountdf[which(medalCountdf$G>1),]
    print(multiple_gold_athletes)
    #table of french athletes with medals
    french_athletes_score <- medalCountdf[which(medalCountdf$NationID=="FRA"),]
    print(french_athletes_score)
    #table of countries that have never won gold
    nations_with_athletes_with_no_wins <- table(medalCountdf[which(medalCountdf$G<1),]$NationID)
    barplot(nations_with_athletes_with_no_wins, main="Number of athletes per country who have never won")
    #proportion of athletes that won a medal that won gold
    proportionWinningAthletes <- table(medalCountdf[which(medalCountdf$G>0),]$NationID)/table(medalCountdf$NationID)
    barplot(proportionWinningAthletes*100)

    print((sum(table(medalCountdf[which(medalCountdf$G>0),]$NationID))/length(medalCountdf$NationID))*100)
    #reading Personal Best dataframe
    library(readODS)
    ISU_ladies_df <- read_ods("ISU_events_PB_ladies.ods") ## return only the first sheet
    olympics_ladies <- ISU_ladies_df[grep("Olympic",ISU_ladies_df$Event),]
    olympics_ladies

    olympics_ladies_2014 <- olympics_ladies[grep("2014",olympics_ladies$Date),]
    olympics_ladies_2014

    ISU_men_df <- read_ods("ISU_events_PB_men.ods")
    olympics_men <- ISU_men_df[grep("Olympic",ISU_men_df$Event),]
    olympics_men
    #Personal best of athletes obtained in 2014 Olympics
    olympics_men_2014 <- olympics_men[grep("14",olympics_men$Date),]
    olympics_men_2014
