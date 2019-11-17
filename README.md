# DataGeneratorForNLP

为NLP生成训练数据，分类两类场景

1. 从零生成数据
2. 有大量未标注数据，少量或者没有标注数据

## chatito

[Chatito](https://github.com/rodrigopivi/Chatito)使用简单易上手的[DSL](https://github.com/rodrigopivi/Chatito/blob/master/spec.md)语法来为几类场景的NLP任务生成数据。原话是

> Generate datasets for AI chatbots, NLP tasks, named entity recognition or text classification models using a simple DSL!

亲测确实方便生成一定量的数据，但是生成的训练集和测试集都是一个模板（构成规则）出来的，训练测试数据同源同构，很容易造成严重的过拟合。典型的表现是在测试集上的准确率和F1等指标会接近1，在未知数据上的泛化性会不好。



显然，采用这种方式生成数据并不是最好的方式。但在实在没有数据的情况下，怎样去解决同源的问题呢？想到的解决方式有几点：

1. 生成的过程中，只填入几条典型的场景，同类型的采用词典，并后续任务上构造词典特征
2. 生成后采用一些数据增强方式（同义词替换、位置交换等），增加训练数据的多样性。

使用Chatito从零生成数据使用参见[NLP训练数据生成之chatito](https://zekizz.github.io/NLP/chatito/)。



TODO：

- snorkel使用
- GAN

