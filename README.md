# Analyze of Human Activity Recognition Dataset
###### Author: Krzysztof Jarek


Project was made using as the base for its dataset prepared by Jorge L. Reyes-Ortiz, that contained samples from smartphones' gyroscopes and accelerometers, and also labels corresponding to the one of users states: WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING. Link to the dataset: [UCI HAR Dataset](https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones)

## Project purpose
My purpose was to use the data and find good model to make decisions based on them. That's why I was testing the SVM model- to find how good was an idea of dataset creator to use this- and Linear Regression. Finding which one would fit better and work better.

Author's article: [article](https://www.elen.ucl.ac.be/Proceedings/esann/esannpdf/es2013-84.pdf)

## Used tools
```
- SVC
- LogisticRegresion
- PCA
- StandardScaler
- GridSearchCV, RandomizedSearchCV
- Pipeline
- OneVsRestClassifier
- roc_curve, label_binarize
```
all from [sklearn](https://sklearn.org) library. I also used `Numpy` and `Matplotlib` library.

## Modelings steps

1. Firstly I loaded the sets. This one with data to model I decomposed with use of PCA.
2. Then I plotted the decomposed to 24 dimensions data and their labels.
![alt text](https://github.com/KrzysiekJa/ML-project-on-HAR-Dataset/blob/master/plot.png "Plot")
3. Then I trained the SVC model on data in few configurations.
4. And on the same data I trained Linear Regression one.
5. Finally, I made a classification repost for best two models.
![alt text](https://github.com/KrzysiekJa/ML-project-on-HAR-Dataset/blob/master/results_table.png "Table")

![alt text](https://github.com/KrzysiekJa/ML-project-on-HAR-Dataset/blob/master/roc_curve.png "Table")

## Conclusion

Better mean results, using grid searcher, showed SVC model, but was computing much slower. Also, for another comparison for final repost, better scores gives SVC.

## Misses

Firstly, I was trying to use as the learning set decomposed set with raw data from instruments, but without well-made signal preprocessing, it was giving low result (best: 0.67 for SVM), so I used special set already prepared by researchers.
Also, I was trying to use the Hidden Markov' Chains model with use of [hmmlearn](https://hmmlearn.readthedocs.io/en/latest/#) library. But after long fight I reconciled that tools aren't made for my case in which I wanted to use labels set.

