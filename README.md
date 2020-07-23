# DeepInf-tf
- https://github.com/xptree/DeepInf
  这个论文中代码是用的pytorch, 打算改为用tensorflow的。
  july 19 遇到些问题，正在调试，明天在更新一版。
- july 20 查 tf pretrained embeding , 发现 buildin attention layers.
- july 22 tf 自带的 attention layer 貌似和 DeepInf 里的 gat layer 不一致，自定义一个 keras layer
一些pytorch里的function 在 tf 里面没有对应的,比如 masked_fill_ ，还有的是同样功能但是换了名字，比如 squeeze 在tf 里也有同名的。但是 unsqueeze 在tf 里确实 expand_dims()!
- july 23 01:17
tf.broadcast_to 不支持 shape 为(None,2,50),set  input layer batch size 
tf.keras.layers.Softmax() 做最后output 总报错 softmax object  no op attribute,换成 tf.nn.softmax
tf.keras.layers.Permute() index 从 1 开始，估计 0是 batch size 不能改顺序
多input 时 layer name 必填 和 fit() 中要一致
tf.nn 等function 不要放init 里然后 call 里self. 用，直接call 里调用
- july 24 01:38 <br>
add more gat layers  <br>
fix shape <br>
pytorch nllloss maybe == tf SparseCategoricalCrossentropy <br>
finaly i see this line. <br>
WARNING:tensorflow:Gradients do not exist for variables ['Variable:0', 'Variable:0', 'Variable:0'] when minimizing the loss.
  465/24349 [..............................] - ETA: 12:59 - loss: 0.5603
  <br>
 todo: WARNING ? add pretrained embedding.  metrics, evaluate, predit. tensorboard.

