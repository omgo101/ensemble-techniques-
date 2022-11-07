# ensemble-techniques-
all  ensemble techniques  <br />
ensemble means combinig multiple models when we assemble different algorithm and combine into one so we are gonna call it **ensemble techinques** Ensemble methods are techniques that aim at improving the accuracy of results in models by combining multiple models instead of using a single model.<br />
**suppose** if we take decision tree models if we slietly change the data the whole decision model will change for so for this situation we will use **bagging and boosting** baaging it has another word called bootstarping(these are the evaluation methods that we can use out cross valiudation and hold out method)<br />
**Bagging(aka boostrap aggregation):** that otten considers homogeneous weak learners, learns them independently from each and one of the techinque in bagging is called as **random forest**
other in parallel and combines them tollowing some kind ot deterministic averagıng process <br />
**Boosting:** that often considers homogeneous weak learners, learns them sequentially in a very
adaptative way (a base model depends on the previous ones) and combines them following a
deterministic strategy <br />
**Stacking:** that often considers heterogeneous weak learners, learns them in parallel and combınes
them by training a meta-model to output a prediction based on the different weak models predictions <br /> <br />
**Bagging**
before going to bagging we will take an example suppose we have multiple model and one dataset so what we will do we take an sample from the dataset and feed to model1 and resample(every time should be different sample) the dataset and feed to model2 and so on till modelN so this process called as **row sampling with replacement** <br />
![image](https://user-images.githubusercontent.com/79073189/200339517-f12732b4-c746-4877-8fa3-19803737abb8.png) <br />
lastly the model will give results and here we will use **voting classifier** it means whoever got the majority vote will win <br />
![image](https://user-images.githubusercontent.com/79073189/200340459-48515b5a-00d1-47a3-8fcc-acea145d35c4.png) <br />
but you will why we  call this bagging as boostrap agrregation because as you see the dataset get split and then its combine and give results <br />
