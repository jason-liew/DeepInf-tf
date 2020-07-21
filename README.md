# DeepInf-tf
- https://github.com/xptree/DeepInf
  这个论文中代码是用的pytorch, 打算改为用tensorflow的。
  july 19 遇到些问题，正在调试，明天在更新一版。
- july 20 查 tf pretrained embeding , 发现 buildin attention layers.
- july 22 tf 自带的 attention layer 貌似和 DeepInf 里的 gat layer 不一致，自定义一个 keras layer
一些pytorch里的function 在 tf 里面没有对应的,比如 masked_fill_ ，还有的是同样功能但是换了名字，比如 squeeze 在tf 里也有同名的。但是 unsqueeze 在tf 里确实 expand_dims()!
