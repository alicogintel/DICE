# DICE
A **D**ataset for **I**dentifying **C**ommonsense **E**rrors in E-Commerce Knowledge Graph

## Description
DICE aims at evaluating model abilities of identifying commonsense errors in E-commerce knowledge graph. It contains 9,229 concept pairs extracted from AliCoCo (Alibaba E-commerce Cognitive Concept). DICE has already been split into train/dev/test set. In these three files,  each line contains a label and two similar concepts, split by "\t", such as:
- 1 特大码帆布鞋  中长款帆布鞋
- -1  一次性音响  多功能音响

The label is either **1** or **-1**, where **1** indicates that the first concept is more plausible, **-1** indicates that the second concept is more plausible. 

## Analysis
### Character numbers
All concepts have characters between 2 to 7, here is the detailed distribution:

| # characters    | 2   | 3    | 4   | 5   | 6   | 7   |
| ------------ | ---- | ------ | ---- | ------- | --------- | --------|  
| count | 1  |  394   | 4678   | 3006    |    149      | 1 |

### Contradiction type
According to the self-contradictory property, concepts can also be classified into several categories:

| Contradiction type | Percentage | Example |
|--- | --- | --- |
| Function | 19.6 | figure-slimmer shoe (修身凉鞋) *vs* hole-prevent shoe (防踢凉鞋) |
|		Style/Design | 25.8 | loose table (宽松桌子) *vs* double-layer table (双层桌子) |
|		Material | 14.3 | cotten linen biscuits (棉麻饼干) *vs* whole wheat biscuits (全麦饼干) |
|		User | 8.8 | female child supplementary food (女童辅食) *vs* baby supplementary food (宝宝辅食)  |
|		Measure | 8.9 | big shelf (大码置物架) *vs* large shelf (大型置物架) |
|		Space | 2.6 | sneakers at the office (办公室运动鞋) *vs* sneakers at the gym (健身房运动鞋) |
|		Event | 9.2 | converted shoes (改装凉鞋) *vs* knitted shoes (编织凉鞋) |
|		Thing | 7.7 | salt coat (海盐外套) *vs* baseball coat (棒球外套) |
|		Time | 1.9 | summer teakettle (夏季烧水壶) *vs* winter teakettle (冬天烧水壶) |
|		Other | 1.1 | transparent suit pant (透明西装裤) *vs* grey suit pant (灰色西装裤) |

## How to use
- Combine all concepts together and get 9,229\*2=18,458 concepts. Use it to train a model which accepts a concept each time and predicts it have commonsense contradiction or not.
- Use current splitted train/dev/test set to train model which accepts two concepts each time and selects a more plausible one.
