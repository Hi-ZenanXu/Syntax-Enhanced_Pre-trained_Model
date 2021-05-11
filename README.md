# Syntax-Enhanced_Pre-trained_Model (Draft)
Source Data of ACL2021 paper "Syntax-Enhanced Pre-trained Model". 


## Summary of  Paper
In this paper, we present SEPREM that leverage syntax information to enhance pre-trained models. To inject syntactic information, we introduce a syntax-aware attention layer and a newly designed pre-training task are proposed. Experimental results show that our method achieves state-of-the-art performance over six datasets. Further analysis shows that the proposed dependency distance prediction task performs better than dependency head prediction task.

For more details about our paper, we refer the interested readers to the xxxxx.

## Pre-training Data
We randomly collected 1B sentences from publicly released common crawl news datasets ([CCNews](https://commoncrawl.org/)) that contain English news articles crawled between December 2016 and March 2019.  Then, we adopted off-the-shelf [Stanza](https://github.com/stanfordnlp/stanza) to automatically generate the syntax information for each sentence. 
It took a month and a half to get the results when running on 64 V100-32G. The average token length of each sentence is 25.34, and the average depth of syntax trees is 5.15.</br>

Now, we make the constructed 1B sentence public with the correponding syntax information to the community.</br>
You can download the data from my onedrive (preparing).</br>
<b>Please note that</b> the total size of all files is above 800GB.</br>
Since I am using my student certificate, the data on onedrive will <b>expire in 2023</b>.

### 1. File Structure
Due to the large amount of data,  we split the results of raw syntax information into **11** sections instead of storing in a single file. </br>
Each section generally contains **10** folders with each folder contains about **10000** json files.</br>
Unfortunatelly, the first section was deleted by mistake, so we can only provide the  **2nd~11th** sections.</br>

We proviede the statistics of the results as follows:
|Section Number|Number of Folder|Is provided|Total Number of Sentence|
:-:|:-:|:-:|:-:
|1|10|:x:||
|2|10|:grinning:||
|Sum|||0|

### 2. Data Format
The storage unit of raw syntactic information is the json file mentioned above. </br>
Each json file contains about **10000** raw syntax information, including *lemma*, *xpos*, *upos*, *head* and *deprel*.</br>
We take one  item from the file **2/1/1_1_10000.json** as an example

<table>
  <tr>
    <td><b>lemma</b></td> 
    <td>['you', 'should', 'stick', 'with', 'you', 'kid', '.']</td> 
    </tr>
  <tr>
    <td><b>xpos</b></td> 
    <td>['PRP', 'MD', 'VB', 'IN', 'PRP$', 'NN', '.']</td> 
  </tr>
  <tr>
    <td><b>upos</b></td> 
    <td>['PRON', 'AUX', 'VERB', 'ADP', 'PRON', 'NOUN', 'PUNCT']</td> 
  </tr>
  <tr>
    <td><b>head</b></td> 
    <td>[3, 3, 0, 6, 6, 3, 3]</td> 
  </tr>
  <tr>
    <td><b>deprel</b></td> 
    <td>['nsubj', 'aux', 'root', 'case', 'nmod:poss', 'obl', 'punct']</td> 
  </tr>
</table>
<b>Note that</b>, we only utilize the head information to build the syntax tree in our paper.</br>
How to make better use of xpos, upos and deprel information <b>is still a challenge</b>.

<!--
<table>
  <tr>
    <td><b>lemma</b></td> 
    <td>['if', 'you', 'head', 'to', 'a', 'restaurant', 'this', 'weekend', ',', 'you', 'will', 'not', 'get', 'a', 'glass', 'of', 'water', 'without', 'ask', '.']</td> 
    </tr>
  <tr>
    <td><b>xpos</b></td> 
    <td>['IN', 'PRP', 'VBP', 'IN', 'DT', 'NN', 'DT', 'NN', ',', 'PRP', 'MD', 'RB', 'VB', 'DT', 'NN', 'IN', 'NN', 'IN', 'VBG', '.']</td> 
  </tr>
  <tr>
    <td><b>upos</b></td> 
    <td>['SCONJ', 'PRON', 'VERB', 'ADP', 'DET', 'NOUN', 'DET', 'NOUN', 'PUNCT', 'PRON', 'AUX', 'PART', 'VERB', 'DET', 'NOUN', 'ADP', 'NOUN', 'SCONJ', 'VERB', 'PUNCT']</td> 
  </tr>
  <tr>
    <td><b>head</b></td> 
    <td>[3, 3, 13, 6, 6, 3, 8, 3, 13, 13, 13, 13, 0, 15, 13, 17, 15, 19, 13, 13]</td> 
  </tr>
  <tr>
    <td><b>deprel</b></td> 
    <td>['mark', 'nsubj', 'advcl', 'case', 'det', 'obl', 'det', 'obl:tmod', 'punct', 'nsubj', 'aux', 'advmod', 'root', 'det', 'obj', 'case', 'nmod', 'mark', 'advcl', 'punct']</td> 
  </tr>
</table>
-->


## Fine-tuning Stage
We evaluate our proposed SEPREM model on entity typing, question answering and relation classification tasks under the different corresponding benchmarks, ${\it e.g.}$,  Open Entity, FIGER, SearchQA, Quasar-T, CosmosQA, and TACRED, respectively. Thanks to RuiZe's help, we use the fine-tuning pipeline provided by [K-adaper](https://arxiv.org/abs/2002.01808). Those piplelines are available from [here](https://github.com/microsoft/K-Adapter).
