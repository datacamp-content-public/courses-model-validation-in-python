---
title: Insert title here
key: f5ee25065d4316063abbffafc2aaa8d0

---
## Introduction to Cross Validation

```yaml
type: "TitleSlide"
key: "9bddb05bf6"
```

`@lower_third`

name: Kasey Jones
title: Data Scientist


`@script`



---
## Typical Modeling Procedure

```yaml
type: "TwoColumns"
key: "6f285c2ff2"
```

`@part1`
![](http://assets.datacamp.com/production/repositories/3927/datasets/d2c50685c17cd1e95eb3e36a135115178bb92819/Round_1.png){{1}}


`@part2`
```
X_train, X_val, y_train, y_val =
    train_test_split(X, y,
                     test_size=0.2)

rf = RandomForestClassifier(
    n_estimators=50, max_depth=2)

rf.fit(X_train, y_train)
``` {{2}}


```
out_of_sample = rf.predict(X_test)
score = accuracy_score(y_test, out_of_sample)
print(score)
```

`Out[1]: 0.967`{{3}}


`@script`



---
## A Modeling Second Opinion

```yaml
type: "TwoColumns"
key: "b698d2067d"
```

`@part1`
![](http://assets.datacamp.com/production/repositories/3927/datasets/2fba07f04ef89b97f0964e7c66398cba083290f1/Round_2.png)


`@part2`
```
X_train, X_val, y_train, y_val =
    train_test_split(X, y,
                     test_size=0.2)

rf = RandomForestClassifier(
    n_estimators=50, max_depth=2)

rf.fit(X_train, y_train)
```


```
out_of_sample = rf.predict(X_test)
score = accuracy_score(y_test, out_of_sample)
print(score)
```

`Out[1]: 0.929`


`@script`



---
## Final Slide

```yaml
type: "FinalSlide"
key: "1ff72fa887"
```

`@script`


