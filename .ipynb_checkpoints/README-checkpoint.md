# aws-sagemaker-iris

Used the AWS SageMaker ML environment to build and deploy a decision tree classifier on the [Iris Data Set](https://en.wikipedia.org/wiki/Iris_flower_data_set). 

The ```iris.csv``` dataset consists of 150 observations including a label and four predictors for each data point. The label denotes the flower's species from three Iris species: Setosa, Versicolor and Verginica encoded by 0, 1 and 2 respectively in the dataset. The features are the width and length of the flower's petals and sepals.

The model output of AWS SageMaker comes in the form of a tarball. The shell command ```tar -xzf model.tar.gz``` was used to unzip it and get the joblib file which is a SciKit-Learn object in the classifier variable ```clf```. The properties of the classifier are given by running ```print(clf)```:

```
DecisionTreeClassifier(class_weight=None, criterion='gini', max_depth=None,
            max_features=None, max_leaf_nodes=30,
            min_impurity_decrease=0.0, min_impurity_split=None,
            min_samples_leaf=1, min_samples_split=2,
            min_weight_fraction_leaf=0.0, presort=False, random_state=None,
            splitter='best')
```

Lastly, to get a visual representation of the tree, the dot file of the graph was generated. 

To convert it into a png, the ```python-graphviz``` package has to be installed in a virtual conda environment. Once this is done, we can run the dot command ```dot -Tpng tree.dot -o tree.png``` in the same environment to get the image of the tree:

[](tree.png)