# 指南
## 目标文件
### 1. Parser: ./parser parser_kgat_openke

- 在67行增加了一个--kg_embedding_model_name，可选的有
    - transe
    - transr
    - transd
    - complex
    - distmult

### 2. 模型： ./model/KGAT_openke.py

- self.\_\_init\_\_()
    - 找到注释为"opneke KG Embedding"的那一行，去改下面的东西

- self.calc_kg_loss_?()
    - ?是对应的KG Embedding Model Name，找到对应的函数改就行

- self.update_attention_batch_?()
    - ?是对应的KG Embedding Model Name，找到对应的函数改就行

- 最后就是在self.update_attention_batch()和self.forward()里写了点if-else，应该没什么要再加的

### 3. 运行： ./main_kgat_openke.py

- 只改了一下对应的import

- 如果要运行原始的KGAT，运行 ./main_kgat.py就行，对应的其他两个文件就是./model/KGAT.py和./parser/parser_kgat.py