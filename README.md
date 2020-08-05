## 项目说明

本项目论文《ALBERT: A Lite BERT for Self-supervised Learning of Language Representations》
相对于Bert模型：  
- 降低了空间复杂度，把参数量从108M降到了12M,但并没有降低时间复杂度。模型将比如12层的bert分为3个group，每个group包含4层，则这4层的参数是相同的。而且注意，每个group中的层
都是连续的。
- albert将word_embeddings的维度进行变换，论文中表示，128的词向量维度最佳，之后输入encoder时，会接一个线性层，将128维度转换为hidden size，然后继续输入encoder层  
- albert去掉了next predictions，加入了SOP任务，SOP任务指的是句子的顺序任务，比如：  
      正例：1.今天天气太热了。2.我想去游泳    
      反例：1.我想去游泳。2.今天天气太热了。


其他的和bert一直，虽然只是做了这微小的改变，但是效果却比bert要好，整体参数量减少了一大半，虽然推理时间相差不大。
