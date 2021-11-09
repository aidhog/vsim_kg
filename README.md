# Vertex-similarity benchmark for Wikidata

We provide benchmark similarity lists for a sample of 100 movies extracted from BestSimilar and 100 albums extracted from Last.fm. In the case of BestSimilar, up to 10 movies were extracted for each movie, whereas for Last.fm, up to 20 similar albums were extracted for each album. The data were scraped from the respective sites on 05/12/2019 and linked to Wikidata using the external identifiers available, inclusing MusicBrainz, Amazon Standard Identification Number, Spotify album ID, IMDb ids, etc. 

# Data format

Within the folders for BestSimilar and Last.fm, you will find various files named `Qn.txt`, where `n` is a number and `Qn` is a Wikidata identifier. In there, you will find pairs of entities `Qa,Qb` such that `Qa > Qb` (in string similarity; used to deduplicate results) and `Qn = Qa` or `Qn = Qb`. The first line indicates the most similar pair involving `Qn`, the second line the second most similiar, and so forth.

As an example, the file [BestSimilar/Q116928.txt](https://github.com/aidhog/vsim_kg/blob/datos/) corresponds to the top 10 most similar movies for [The Twilight Saga: New Moon](https://www.wikidata.org/wiki/Q116928). The contents are as follows:

```
Q60487,Q116928
Q217010,Q116928
Q160071,Q116928
Q60506,Q116928
Q116928,Q108006
Q116928,Q116845
Q116928,Q105387
Q116928,Q11593
Q116928,Q115760
Q116928,Q1066714
```

where the left value is lower than the right value in string comparison.

Removing the `Q116928` and comma from each line leaves:

```
Q60487
Q217010
Q160071
Q60506
Q108006
Q116845
Q105387
Q11593
Q115760
Q1066714
```

These movies correspond to:

1. [The Twilight Saga: Breaking Dawn – Part 2](https://www.wikidata.org/wiki/Q60487)
2. [The Twilight Saga: Eclipse](https://www.wikidata.org/wiki/Q217010)
3. [Twilight](https://www.wikidata.org/wiki/Q160071)
4. [The Twilight Saga: Breaking Dawn – Part 1](https://www.wikidata.org/wiki/Q60506)
5. [Speed](https://www.wikidata.org/wiki/Q108006)
6. [Silver Linings Playbook](https://www.wikidata.org/wiki/Q116845)
7. [Independence Day](https://www.wikidata.org/wiki/Q105387)
8. [The Last Airbender](https://www.wikidata.org/wiki/Q11593)
9. [Catwoman](https://www.wikidata.org/wiki/Q115760)
10. [His Girl Friday](https://www.wikidata.org/wiki/Q1066714)

In order of similarity.
