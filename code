# -*- coding: utf-8 -*-

import pandas as pd
from sklearn import tree
from sklearn.linear_model import LogisticRegression
from sklearn.svm import SVC
from IPython.display import display
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split

data=pd.read_csv('http://football-data.co.uk/mmz4281/1718/E0.csv')
x=data.iloc[:,[7,8]]
y=data.iloc[:,9]


X_train, X_test, y_train, y_test = train_test_split(x, y, random_state=0)
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

no_of_matches=len(data)

plt.hist(data["HTR"])
#half_time based on values predection based on y value
#home team winning predection
home_wins=len(data[data.HTR=='H'])
win_rate=(float(home_wins)/(no_of_matches))*100
print("total number of matches: {}".format(no_of_matches))
print ("Number of matches won by home team: {}".format(home_wins))
print ("Win rate of home team: {:.2f}%".format(win_rate))
print("\n")


#away team winning predection
away_wins=len(data[data.HTR=='A'])
win_rate=(float(away_wins)/(no_of_matches))*100
print("total number of matches: {}".format(no_of_matches))
print ("Number of matches won by away team: {}".format(away_wins))
print ("Win rate of away team: {:.2f}%".format(win_rate))
print("\n")


#matches to be draw
draw=len(data[data.HTR=='D'])
draw_rate=(float(draw)/(no_of_matches))*100
print("total number of matches: {}".format(no_of_matches))
print ("Number of matches draw: {}".format(draw))
print ("matches draw rate: {:.2f}%".format(draw_rate))
print("\n")


                    
clf = tree.DecisionTreeClassifier().fit(X_train,y_train)

print('Accuracy of Decision Tree classifier on training set: {:.2f}'
     .format(clf.score(X_train, y_train)))
print('Accuracy of Decision Tree classifier on test set: {:.2f}'
     .format(clf.score(X_test, y_test)))
