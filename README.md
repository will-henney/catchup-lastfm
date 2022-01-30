# Catch up missing years of scrobbling to last.fm

So now I have scrobbling working from my iPhone again (using Marvis Pro), I would like to fill in all the years I missed (2016 to 2021).

## Overview of the cunning plan

* [x] Export data from iTunes library as CSV
* [ ] Read CSV file with pandas
* [ ] Select the time period we want
* [ ] Use the last.fm API to scrobble the tracks with the right date specified
* [ ] Voila

## Detailed steps in the cunning plan

### Get my iTunes Library track data out of Apple Music

It seems that the only 3 pieces of relevant useful data that is saved in the library is the date/time that a track was last played, the date/time it was first added, and the total number of plays. 
So for the initial version, I will just scrobble the last play  of each track. 
Maybe later we could scrobble more up to the total play number, but we would have to look at the play number already on last.fm too, so as to avoid double counting. 

I went to the Songs view in the macOS Music app and added the column for "Last Played" and then sorted by it. Then I selected the entire list and copied it and pasted into an empty Numbers document. Then I exported as CSV. The result is `data/will-itunes-library-last-played.csv`

### Install pylast package and get API account

I have done this and also made a separate test account for trying things out: `test-wjh`

