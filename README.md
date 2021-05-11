# Syntax-Enhanced_Pre-trained_Model
Source Data of ACL2021 paper "Syntax-Enhanced Pre-trained Model".


## Paper
In this paper, we present SEPREM that leverage syntax information to enhance pre-trained models. To inject syntactic information, we introduce a syntax-aware attention layer and a newly designed pre-training task are proposed. Experimental results show that our method achieves state-of-the-art performance over six datasets. Further analysis shows that the proposed dependency distance prediction task performs better than dependency head prediction task.

For more details about our paper, we refer the interested readers to the xxxxx.

## Pre-training Data
We make the constructed 1B sentence public with the correponding syntax information to the community.</br>
You can download the data from xxxx (preparing)

### 1. File Structure
Since it's impossible to store the syntax information of the whole **1B** sentence in a single file, we split the results into **11** sections.</br>
Each section generally contains **10** folders with each folder contains about **10000** json files.</br>
A very unfortunate news is that the first section was deleted by mistake, so we can only provide the  2nd~11th sections.</br>

We proviede the statistics of the results as follows:
|Section Number|Number of Folder|Is provided|
:-:|:-:|:-:
|1|2|:x:|
|1|2|:grinning:|
### 2. Data Format

## Fine-tuning Stage

