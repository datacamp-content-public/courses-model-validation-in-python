---
title: Insert title here
key: f5ee25065d4316063abbffafc2aaa8d0

---
## KFold Cross Validation

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
``` {{3}}

`Out[1]: 0.967` {{4}}


`@script`



---
## 5-Fold Cross Validation

```yaml
type: "FullSlide"
key: "71687d2717"
```

`@part1`
![](http://assets.datacamp.com/production/repositories/3927/datasets/07fc602b9307a5c4fd8d1590a4315f48232e3371/five_rounds.png)


`@script`



---
## KFold Cross Validation with sklearn

```yaml
type: "FullCodeSlide"
key: "ce2cace212"
```

`@part1`
`n_splits`: number of cross-validation splits {{1}}

`shuffle`: boolean indicating to shuffle data before splitting {{1}}

`random_state`: random seed {{1}}

```
from sklearn.model_selection import KFold

X = np.array(range(40))
y = np.array([0] * 20 + [1] * 20)

kf = KFold(n_splits=5, random_state=1111)
``` {{2}}

```
splits = kf.split(X)
``` {{3}}


`@script`



---
## Analyzing the KFold Splits

```yaml
type: "FullCodeSlide"
key: "dc890a9a25"
```

`@part1`
Recall that X consists of 40 data points

```
kf = KFold(n_splits=5, random_state=1111)
splits = kf.split(X)

for train_index, test_index in splits:
    print(len(train_index), len(test_index))
``` {{1}}

`Out[3]: 32 8 32 8 ...` {{1}}

```
print(train_index, test_index)
``` {{2}}

`[ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31]` {{2}}

`[32 33 34 35 36 37 38 39]` {{2}}


`@script`
__


---
## Let's fold some data!

```yaml
type: "FinalSlide"
key: "1ff72fa887"
```

`@script`


