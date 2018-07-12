# 网格搜索
## 在sklearn中使用网格搜索
### 1. 导入 GridSearchCV
```from sklearn.model_selection import GridSearchCV```
### 2.选择参数
选择我们想要选择的参数，并形成一个字典。 在这本字典中，键 (keys) 将是参数的名称，值 （values) 将是每个参数可能值的列表
```parameters = {'kernel':['poly', 'rbf'],'C':[0.1, 1, 10]}```
### 3.创建一个评分机制 (scorer)
我们需要确认将使用什么指标来为每个候选模型评分。 这里，我们将使用 F1 分数。
```
from sklearn.metrics import make_scorer
from sklearn.metrics import f1_score
scorer = make_scorer(f1_score)
```
### 4.使用参数 (parameter) 和评分机制 (scorer) 创建一个 GridSearch 对象。 使用此对象训练模型 （fit the data)
```
# Create the object.
grid_obj = GridSearchCV(clf, parameters, scoring=scorer)
# Fit the data
grid_fit = grid_obj.fit(X, y)
```
### 5.获得最佳估算器 (estimator)
`best_clf = grid_fit.best_estimator_`