# English recipe flowgraph dataset
The recipe flowgraph dataset used in our [1] and/or [2] papers is available here:

## Download files:
### r-100 dataset
These recipes were sampled from each category of ‘dish type’ in the Allrecipes UK/Ireland web site (http://allrecipes.co.uk/) as of December 2016. The sample selection criteria are based on the proportions and rank orders in which recipes are listed within each dish type. The number of the recipes of each dish type in the web site and the corpus are shown in Table 3 in the paper [1].
- The zip file: r-100.zip
- The original data can be download according to the list: r-100.json
### r-200 dataset
There recipes was sampled from the Allrecipes UK/Ireland web site completely randomly.
- The zip file: r-200.zip
- The original data can be download according to the list: r-200.json
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
```
Here, the first three numbers show the number of the step, the number of the sentence in the step, and the number of word in the sentence. These three numbers are also used as node ID in the flowgraph file. The forth token shows the corresponding word, the fifth token shows POS tag automatically labeled with the parsing system RASP, and the last token shows manually labeled r-NE tag.

### '*.flow' provide flowgraph edge list
An example of the file is as below:
```
1 1 13 t 1 1 1
1 1 21 o 1 1 1
1 1 29 o 1 1 1
```
Each line of the flow file correspond each directed edge of this recipe flowgraph. The first three numbers ('1 1 9' in the example above) represents the ID of the origin and the last three numbers ('1 1 1' ) represents the destination of the edge. The ID is referred from the list file mentioned above. Therefore, this example represents a sub-graph below;
```
oven/T --> Preheat/Ac
170 C/St --> Preheat/Ac
Gas mark 3/St -> Preheat/Ac
```
# References:
[1] Yoko Yamakata, John A Carrol, and Shinsuke  Mori, "A Comparison of Cooking Recipe Named Entities between Japanese and English", CEA2017, Pages 7–12, 2017. 

[2] Yoko Yamakata, Shinsuke Mori and John Carroll, "English Recipe Flow Graph Corpus", LREC2020, paper number 582, 2020.
