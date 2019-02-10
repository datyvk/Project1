# Project1
In order to run the code, first the files are downloaded from their respective sources into excel and converted into CSV files. I will link the data source but for intents and purposes, included the processed and randomized CSV as part of the submittion so you can run the programs necessary without any pre processing.
Titanic: https://www.kaggle.com/dmilla/introduction-to-decision-trees-titanic-dataset?fbclid=IwAR0WZdBrq296WxXGUpWrSpdBHXXMN8b6Mp0uSK9C_rkd_aniSmsq1OCDiM4

Adult: http://archive.ics.uci.edu/ml/datasets/Adult

The combined data sheets with testing cross validation and training accuracy and other data used in graphs are saved in these google sheets
https://docs.google.com/spreadsheets/d/15WZhfrUXd4xYVRBqwS8NkSmnuL9e3wVeenjXUMdAqF0/edit?usp=sharing
https://docs.google.com/spreadsheets/d/15WZhfrUXd4xYVRBqwS8NkSmnuL9e3wVeenjXUMdAqF0/edit?usp=sharing


If you use the files we provded which is the 10% 20% ... 80%, randomized, and test  arf files skip to step 5. If you want to do things from scatch or see how we got those files continue. Otherwise they are at this github
https://github.com/datyvk/Project1

1. First download the data and import them into excel. Titanic will then be processed by the python code we provide called process.py, a portion of the code from the kaggle link , which will mark some of the values into groups and discreatize them. Adult will just be imported under excel's data portion. Later on based on my personal decisions on what is necesary and not, more attributes are deleted. Attritubutes and discretization for the adult file was done by hand, which i found similar attribute values and groupe them together. (The original and post processed files are included as examples but most of it was just done by hand using excel and replace all) 
	For adults, I caterogirzed everything such as preschool, 4-5th, 7-8th. 11th into pre highschool, college and associate school into college, and master PHD prof school etc into higher education.
	Marriage status were converted so that seperated widowed divorced are all grouped as well
	Native region became contiental regions
	Captain gain loss and fnlwgt was deleted
	For titanic title siblings parents were deleted
	the python script descretized age and ticket price

2. Open both files in Weka's explore section, and apply the filter for randomize, and save them as arff files called randomTit.arff and adult raandomized.arff and csv files

3. using another python script we provide we divded the csv file into 10% 20% 30%... 80% and saved them each, as well as the last 20% as our test set.

4. Convert each file into arff file by importing them into weka and saving them as arff files

5. Using the randomized 80% file for each data, we open them in weka and run cross validation 10 fold using classifiers and tune the hyper paramters. This is done under the 
classify tab, where you click choose for classifier (we used multilayer Perceptron, IBK, J48, SMO, and AdaBoost1). right clicking them will allow you to chose the paramters, and proceeded to run different hyper paramters based on each of the algorithims and found the one with the highest accuracy. We will cover what to pick for each of the setting in the write up and why we picked them there. This is done for each algorithm for each data set for a total of 12 iterations of fine tuning is completed

6. With the decided hyperparamters, we opened each of the 10 to 80% files and trained them three times, while recording the summary section with the data breakdown.
	a. First time we ran 10 fold cross validation to receive accuracy 
	b. the we ran them against themslves using the training set option for test
	c. lastly we tested them against the last 20% test data we didnt use for training


