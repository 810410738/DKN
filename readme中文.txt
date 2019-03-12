### 文件夹中的文件
- `data/`
  - `kg/`
    - `Fast-TransX`: TransE及其扩展的知识图谱嵌入模型的有效实现(from https://github.com/thunlp/Fast-TransX);
    - `kg.txt`: 知识图谱文件knowledge graph file;
    - `kg_preprocess.py`: 为DKN预处理知识图谱并输出知识嵌入文件；生成实体嵌入和上下文实体嵌入
    - `prepare_data_for_transx.py`: 为Fast-TransX生成所需的输入文件;;
  - `news/`
    - `news_preprocess.py`: 预处理新闻数据；
    - `raw_test.txt`: 原始测试数据集文件 raw test data file;
    - `raw_train.txt`: 原始训练集文件 raw train data file;
- `src/`: DKN的实现

> Note: 
由于BingNews的隐私策略和Github上的文件大小限制，此存储库中发布的原始数据集和知识图只是本文中报告的原始数据集的一小部分。

### 输入文件的格式
- **raw_train.txt** and **raw_test.txt**:  
  `user_id[TAB]news_title[TAB]label[TAB]entity_info`
	对于每一行，`news_title`是一组单词`w1 w2 ... wn`，`entity_info`是一组实体id和实体名称`entity_id_1:entity_name;entity_id_2:entity_name...`
  for each line, where `news_title` is a list of words `w1 w2 ... wn`, and `entity_info` is a list of pairs of entity id and entity name: `entity_id_1:entity_name;entity_id_2:entity_name...`
- **kg.txt**:  
  `head[TAB]relation[TAB]tail`
  对于每一行，`head`和`tail`是对应的实体id，`relation`是关系id
  for each line, where `head` and `tail` are entity ids and `relation` is the relation id.
  
 ### Required packages
 The code has been tested running under Python 3.6.5, with the following packages installed (along with their dependencies):
- tensorflow-gpu == 1.4.0
- numpy == 1.14.5
- sklearn == 0.19.1
- pandas == 0.23.0
- gensim == 3.5.0