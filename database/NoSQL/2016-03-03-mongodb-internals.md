---
layout:     post
title:      "A Glimpse of MongoDB Internals"
subtitle:   "A comparison between two NoSQL databases"
date:       2016-02-26 12:00:00
author:     "aaronice"
keyword:    ["MongoDB", "CouchDB", "NoSQL", "Database"]
header-img: ""
---



MongoDB saves documents whose attributes can be updated freely
MongoDB存储的是任意属性的文档集合。
MongoDB adds paddings into documents to reduce fragments
MongoDB通过在文档尾部预留空间的方式来修改文档时引发的碎片。
MongoDB uses pre/next points to increase lookup speed
MongoDB通过在文档中加入了指向前／后文档的指针来加速遍历。
MongoDB saves the documents into a sequence of 16M, 32M, … 2GB files
MongoDB将文档集合保存在16M、32M、……、2GB的文件中。
MongoDB uses BTree (a better version of BST) to build index
MongoDB使用BTree来建立索引。


## Reference



* [A Journey through the MongoDB Internals *#nosql13*](https://2013.nosql-matters.org/bcn/wp-content/uploads/2013/12/storage-talk-mongodb.pdf)
* [MongoDB Storage Engine Internals](https://www.mongodb.com/presentations/storage-engine-internals)
