# English recipe flowgraph dataset
The recipe flowgraph datasets used in our papers published at CEA2017 [1] and LREC2020 [2] are available for download. 

## Download files:
### r-100 dataset
These recipes were sampled from each category of ‘dish type’ in the Allrecipes UK/Ireland web site (http://allrecipes.co.uk/) as of December 2016. The sample selection criteria are based on the proportions and rank orders in which recipes are listed within each dish type. The number of the recipes of each dish type in the web site and the corpus are shown in Table 3 in paper [1].
- The zip file: [r-100.zip](r-100.zip)
- The original, unannotated data can be downloaded from the URLs listed: [r-100.json](r-100.json)
### r-200 dataset
There recipes was sampled from the Allrecipes UK/Ireland web site completely randomly.
- The zip file: [r-200.zip](r-200.zip)
- The original, unannotated data can be downloaded from the URLs listed: [r-200.json](r-200.json)
## Contents:
### '*.list' provide r-NE list:
An example of the file is as below:

```
1 1 1 Preheat VV0 Ac-B
1 1 9 the AT O
1 1 13 oven NN1 T-B
1 1 18 to II O
1 1 21 170 MC St-B
1 1 25 C ZZ1 St-I
1 1 27 / CC O
1 1 29 Gas NN1 St-B
1 1 33 mark NN1 St-I
1 1 38 3 MC St-I
1 1 40 . . O
  ... 
5 1 1 Bake VV0 Ac-B
5 1 6 in II O
5 1 9 the AT O
5 1 13 oven NN1 T-B
```
Here, the first three numbers show the number of the step, the number of the sentence in the step, and the number of word in the sentence. These three numbers are also used as node ID in the flowgraph file. The fourth token shows the corresponding word, the fifth token shows POS tag automatically labeled with the parsing system RASP, and the last token shows manually labeled r-NE tag.

### '*.flow' provide flowgraph edge list
An example of the file is as below:
```
1 1 13 t 1 1 1
1 1 21 o 1 1 1
1 1 29 o 1 1 1
  ...
1 1 1 t-eq 5 1 13
```
Each line of the flow file corresponds to a directed edge in the recipe flowgraph. The first three numbers ('1 1 9' in the example above) represents the ID of the origin and the last three numbers ('1 1 1' ) represents the destination of the edge. These node IDs are as described above. Therefore, this example represents the following sub-graph;
```
oven/T -(Targ)-> Preheat/Ac
170 C/St -(Other-mod.)-> Preheat/Ac
Gas mark 3/St -(Other-mod.)-> Preheat/Ac
  ...
Preheat/Ac -(T-eq)-> oven/T
```
The tag in the center means the label of the edge. "a", "t", "d", "o" are abbrebiation of "Agent", "Target", "Destination" and "Other-mod.", respectively.

A line started with "#" shows a comment written by an annotator, and should be ignored for processing purposes.

# References:
[1] [Yoko Yamakata, John A Carrol, and Shinsuke  Mori, "A Comparison of Cooking Recipe Named Entities between Japanese and English", CEA2017, Pages 7–12, 2017. ](https://dl.acm.org/doi/10.1145/3106668.3106672)

[2] [Yoko Yamakata, Shinsuke Mori and John Carroll, "English Recipe Flow Graph Corpus", LREC2020, paper number 582, 2020 (to appear).](https://lrec2020.lrec-conf.org/en/conference-programme/accepted-papers/)
