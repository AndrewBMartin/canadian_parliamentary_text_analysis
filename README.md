#  Canadian Parliamentary Text Analysis

This repo is fundamentally organized data and some example analysis on how to use it.

See [What do Canadian Politicians Talk About in Parliament](https://medium.com/@andrew.brown.martin/what-do-canadian-politicians-talk-about-in-parliament-1baf9cf78f1c) for an introduction to the data and analysis.

### The data
We've parsed the text transcripts of the 43-1 and 43-2 parliament sessions (late 2019 - mid 2021), and organized the data by speaker, and political party, see `./parliament_text_raw.json`. Types for `./parliament_text_raw.json` given below.

```
[{
   text: string - text of speech
   party: string - MP political affiliation at time of speaking
   img: string - url to image of MP
   name: string - MP name
   index: int - speaker order on current bill
   bill: string - bill ID
}]
 ```

We've also done some secondary processing and re-organized the data so that it's indexed by word used, and maps to the relative frequency of each party using that word, see `./parliament_text_by_word.json`. Types for `./parliament_text_by_word.json` given below. Computation of relative frequency can be found in Appedix 1 of `word_frequency.ipynb`.
```
{
    [word: string] : {
         Bloc?: float;
         Conservative?: float;
         Green?: float;
         Independents?: float;
         Liberal?: float;
         NDP?: float;
    }
}
```

### Examples

Examples given in `word_frequency.ipynb` all use heatmaps to compare how often each party uses specific words. The data allows similar analysis to be done at the MP level instead of the party level. Other interesting work could include NLP based keyword analysis and summarization.

### Acknowledgement
The data comes from [Open North](https://openparliament.ca/about/). They are not a government organization and neither am I. 

