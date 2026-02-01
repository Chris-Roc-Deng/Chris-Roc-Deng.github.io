## 背景
elasticsearch 是基于lucene搜索引擎的, lucene是es单个节点内实现检索的基本结构。由于luence是基于单节点的,缺少高可用、高可靠、拓展性的一些能力, es基于lucene之上拓展了对应欠缺的能力


与mysql 等关系型数据库之间的概念对照为
|--| --|
|rmdb | es|
|schema| index
|table| index|
|row | document|

type这个概念在7.x版本基本上被废弃了, 原因为es初期设计参考了关系型数据库,一个数据库下可以有多张表, 但elasticsearch是基于luence的,实际上都为同一个索引文件,还需要多一层映射到对应的数据索引上，管理复杂容易产生冲突

## 基础数据结构

### 倒排索引(Inverted Index)


### Posting list
存储完整内容的结构, 使用json存储, 映射关系为 doc_id -> posting list

### doc value


### term dictionary(词项词典)