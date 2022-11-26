# ensemble-techniques-
all  ensemble techniques  <br />
ensemble means combinig multiple models when we assemble different algorithm and combine into one so we are gonna call it **ensemble techinques** Ensemble methods are techniques that aim at improving the accuracy of results in models by combining multiple models instead of using a single model.<br />
![image](https://user-images.githubusercontent.com/79073189/204076770-c44c517b-e59f-41e7-9b2c-fd8dbac2a8ed.png)

**suppose** if we take decision tree models if we slietly change the data the whole decision model will change for so for this situation we will use **bagging and boosting** baaging it has another word called bootstarping(these are the evaluation methods that we can use out cross valiudation and hold out method)<br />
**Bagging(aka boostrap aggregation):** that otten considers homogeneous weak learners, learns them independently from each and one of the techinque in bagging is called as **random forest**
other in parallel and combines them tollowing some kind ot deterministic averagıng process <br />
**Boosting:** that often considers homogeneous weak learners, learns them sequentially in a very
adaptative way (a base model depends on the previous ones) and combines them following a
deterministic strategy in boosting we have techique such as adaboost, gradien6t boosting,xgboost<br />
**Stacking:** that often considers heterogeneous weak learners, learns them in parallel and combınes
them by training a meta-model to output a prediction based on the different weak models predictions <br /> <br />
**Bagging**
before going to bagging we will take an example suppose we have multiple model and one dataset so what we will do we take an sample from the dataset and feed to model1 and resample(every time should be different sample) the dataset and feed to model2 and so on till modelN so this process called as **row sampling with replacement** <br />
![image](https://user-images.githubusercontent.com/79073189/200339517-f12732b4-c746-4877-8fa3-19803737abb8.png) <br />
lastly the model will give results and here we will use **voting classifier** it means whoever got the majority vote will win <br />
![image](https://user-images.githubusercontent.com/79073189/200340459-48515b5a-00d1-47a3-8fcc-acea145d35c4.png) <br />
but you will why we  call this bagging as boostrap agrregation because as you see the dataset get split and then its combine and give results <br />

**Boosting** <br />
its a sequential technique <br />
**1**. Initialise the dataset and assign equal weight to each of the data point.<br />
**2**. Provide this as input(randomly sample) to the model and identify the wrongly classified data points.(its not neccessary that model always be classified correctly)<br />
**3**. Increase the weight of the wrongly classified data points. this is because those datapoint whose weights are high will be select in next round of model(probability will be high)<br />
![image](https://user-images.githubusercontent.com/79073189/201016905-9c5efc7c-f9a0-461f-9f1a-a88bf468e7d6.png)<br />
**4**. model 2 will clssify those who got wrong will get higher weights and the cycle contineous till Mn(model n)<br />
**5**. if (got required results) <br />
  Goto step 6 <br />
else <br />
  Goto step 2 <br />
**6**now give the input from the test data for all model(earlier we where performing the operation on training data)now classify it 
**7** now we use  **voting classifier** it means whoever got the majority vote will win <br />
![image](https://user-images.githubusercontent.com/79073189/201019881-97223c25-7174-4d77-b484-f647e46f212b.png)

differnce between **bagging and boosting** <br />
Bagging is a parallel learner process vs boosting is sequential.<br />
Boosting is iterative vs bagging doesn't have to be.<br />
Boosting can increase over-fitting whereas bagging generally decreases boosting.<br />
Ensemble learning works well when different models make independent mistakes i.e. when different models make mistakes on different examples.<br />
### Adaboost
before going to adaboost lets know about **stump** its contains only node and two leaves (not great for classification) <br />
![image](https://user-images.githubusercontent.com/79073189/201112195-0dd82b7f-a800-43eb-b91d-9bb01e5a5467.png)
in random forest all decision tree has equal important means there is no weight in that but not in forest for stumps in adaboost  <br />
in random forest all decision tree are independent to each other inforest for stumps in adaboost should be in order the first stump is influence by other stumps is made and so on
### Gradient Boost <br />
lets understand the difference between adaboost and gradient boost  <br />
1)in adaboost weights are increase means updated but in gradient boost optimizing the loss fuction <br />
optimizing the loss fuctions menas improving the ols(ordinary least square because we are trying to reduce ols value) ols become the loss function for gradient boost  <br />
![image](https://user-images.githubusercontent.com/79073189/201259498-09604140-9f62-441a-b8f3-57a95205e84b.png) <br />
2)in adaboost has stumps but gradient boost has leaf nodes means greater trees <br />
**now how gradient boost works** <br />
lets say have this data where age and bmi are independent and height is dependent variable <br />
![image](https://user-images.githubusercontent.com/79073189/201259862-99ddf90c-0f81-4246-9bc2-2bd6524eda94.png) <br />
very 1 step boosting algorithm does is it will take average of the target column (height) initially the boosting algoritm assumes there is no learning model means 0 model so thus it will make column of predicted column and put the average height values in that <br />
and next step is take out the actual predict and residual(actual-predicted) values <br />
![image](https://user-images.githubusercontent.com/79073189/201260659-e28da893-c47d-436d-a829-91b330f0d94e.png) <br />
so what happen in next column is instead of taking target variable as height  column we will take residual column as target column means dependent variable and now model will work on it model will fit on it <br />
now how residual will look like is supppose we say we applied decision tree on it and it will predict values and we it in column as residual predicted  <br />
before moving foward let understand what is **learning rate** <br /> 
 the learning rate is a tuning parameter in an optimization algorithm that determines the step size at each iteration while moving toward a minimum of a loss function. (at what change at what speed you want change the predicted value)<br />
 now what happend in next step is it will add the predicted height value + (learning rate X predicted resiudual) and update the predicted height column  and obviously the residual column will also change so this is how iteration one get completed and the cycle gose on   <br />
 ![image](https://user-images.githubusercontent.com/79073189/201262636-d08769bd-dfde-489f-9904-a9894f620d9f.png) <br /> 
here what we are trying is we are coming closer to the actual value
lastly the final prediction value will loss like this <br /> 
![image](https://user-images.githubusercontent.com/79073189/201263080-904959e8-408b-49a9-9c7e-e6af227660ea.png) <br /> 
here the base value is avg value
#### XGBM,LGBM Light GBM, XGBOOST
**XGBOOST**(extreme gradient boosting) **by tanqi chen**
xgboost is gain popularity for two main reason 1) faster processing  speed 2)accurate results performance is really good  <br /> 
we can say xgboost is **advance version of gradient boosting** <br /> 
why its really faster because of paralelization ,cache optimization ,out of memory computation and for performance is regularization (prevent from  overfiting and underfiting ),auto pruning (it means it will not allow tree to go beyond the certain level thus the model will not be baised),missing value handling  <br /> 
#### how it works   
xgboost dose two things  <br /> 
1)xgboost regression  <br /> 
2)xgboost classification <br /> 
xgboost is mainly built for largly complicated dataset  <br /> 
**xgboost regression**
to start with we have to built xgboost tree(which is unique regression tree that  which uses by xgboost)(there are many ways to build xgboost tree but we are taking ones most  common xgboost tree) <br />
each tree will start with single leaf and all the residuals will go the leaf now we should calculate similarity scores = sum of the residuals squared  / number of residuals + lamda(lamda is regularization parameter)    <br /> 
after calculating similarity scores  contineu growing the tree by taking the condition split of lowest values in the graph   <br /> 
![image](https://user-images.githubusercontent.com/79073189/204083251-d99f0b9b-9008-4fe3-b0c0-8eb50161823d.png)
now calculate the similarity scores for other two leaf for just example like this  <br /> 
![image](https://user-images.githubusercontent.com/79073189/204083366-05fedfc3-b453-4239-a9d7-7e44ae6bcfd0.png)   <br /> 
but how we can know if it is building better leaves cluster that the root(means what should we take the threshold  value for the root leaves) to know this we will use **gain**  which formula is left(similarity)+right(similarity)-root(similarity)
now we to this process by shifting the threshold values by its data and do this all process and take out the gain vaules lastly after you reach last treshold value stop the process and comparre the gain value with others and whoever got the highest value will win(for to condition split leaves in root)
now do this process for further leaves <br /> 
![image](https://user-images.githubusercontent.com/79073189/204083959-f6fb3a1c-71ed-4083-b664-19debb153e7e.png)  <br /> 
![image](https://user-images.githubusercontent.com/79073189/204085497-fb48f3c2-b24a-45c8-9e3b-30d7f47be73b.png)<br /> 

now we have to prune the tree we will prune the tree based on the gain value we start with picking a random average number this  random average number we call it **gemma** now we go the lowest branch of the tree and apply this formula gain- gemma (those who will get the negative value will remove the branch and positive will not remove the branch and done pruning)
remember lambda we use while calculating similarity score there is rule for lambda which is when lambda is > 0 the similarity score,gain  become smaller (note dont put the gemma value as 0)
now we will take out the **output value** for each leafs formula output values =sum od residuals /number of residuals +lambda  <br /> 
![image](https://user-images.githubusercontent.com/79073189/204084934-5f0bbcfc-6b72-4430-8b2c-0ed5911704f7.png) <br /> 
just like we build our first tree so now we make new prediction nd just like unextreme Gradient
Boost, XGBoost makes new
predictions by starting with the initial
Prediction and adding the output of the Tree,
scaled by a Learning Rate X output values 
![image](https://user-images.githubusercontent.com/79073189/204085144-622701e5-acbc-43aa-b33c-d1198d7def76.png)
xgboost calls learning rate as eta and the default value is 0.3 and we will put the value and take out the new prediction to check the prediction is effective or not we will put training data and will see in graph the you will the predicted value annd actual value are closer  but not the accurate so put the vaules as residuals line 
![image](https://user-images.githubusercontent.com/79073189/204085423-31024811-f942-403b-b003-520d4382a73c.png)
and build the tree based on the newest residuals until  you have reach the smallest number of residuals 
