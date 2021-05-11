# Syntax-Enhanced_Pre-trained_Model (Draft)
Source Data of ACL2021 paper "Syntax-Enhanced Pre-trained Model". 


## Paper
In this paper, we present SEPREM that leverage syntax information to enhance pre-trained models. To inject syntactic information, we introduce a syntax-aware attention layer and a newly designed pre-training task are proposed. Experimental results show that our method achieves state-of-the-art performance over six datasets. Further analysis shows that the proposed dependency distance prediction task performs better than dependency head prediction task.

For more details about our paper, we refer the interested readers to the xxxxx.

## Pre-training Data
We make the constructed 1B sentence public with the correponding syntax information to the community.</br>
You can download the data from xxxx (preparing)

### 1. File Structure
Due to the large amount of data,  we split the results of raw syntax information into **11** sections instead of storing in a single file. </br>
Each section generally contains **10** folders with each folder contains about **10000** json files.</br>
Unfortunatelly, the first section was deleted by mistake, so we can only provide the  2nd~11th sections.</br>

We proviede the statistics of the results as follows:
|Section Number|Number of Folder|Is provided|Total Number of Sentence|
:-:|:-:|:-:|:-:
|1|2|:x:||
|1|2|:grinning:||
|Sum|||0|

### 2. Data Format
The storage unit of raw syntactic information is the json file mentioned above. </br>
Each json file contains about **10000** raw syntax information, including *lemma*, *xpos*, *upos*, *head* and *deprel*.</br>
We show an item in file **2/1/1_1_10000.json** as an example

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

## Fine-tuning Stage

