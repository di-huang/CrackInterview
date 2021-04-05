1. [Medium][Parcel shipping](https://www.nowcoder.com/practice/6e9ce0dcb36a47328ee9c92394717c4e?tpId=170&tqId=34066&rp=1&ru=%2Fta%2Fexam-sohu&qru=%2Fta%2Fexam-sohu%2Fquestion-ranking&tab=answerKey) <br />
````python
def solve(X):
    res = X[5]
 
    X[0] -= X[4] * 11
    res += X[4]
 
    res += X[3]
    space = X[3] * 20
    X[1] -= space // 4
    X[0] -= space % 4
 
    res += X[2] // 4
    X[2] %= 4
    if X[2] > 0:
        res += 1
    if X[2] == 3:
        X[1] -= 1
        X[0] -= 5
    elif X[2] == 2:
        X[1] -= 3
        X[0] -= 6
    else:
        X[1] -= 5
        X[0] -= 7
 
    if X[1] > 0:
        res += X[1] // 9
        X[1] %= 9
        if X[1] > 0:
            res += 1
        X[0] -= (36 - X[1] * 4)
 
    if X[0] > 0:
        res += X[0] // 36
        X[0] %= 36
        if X[0] > 0:
            res += 1
    return res
 
i = input()
while i != "0 0 0 0 0 0":
    l = list(map(int, i.split(" ")))
    print(solve(l))
    i = input()
````

2. [Medium][Kolakoski sequence](https://www.nowcoder.com/practice/79358002fe7c48a6a74f96c0dc734fa1?tpId=170&tqId=34067&rp=1&ru=%2Fta%2Fexam-sohu&qru=%2Fta%2Fexam-sohu%2Fquestion-ranking&tab=answerKey)
````python
N, M = map(int, input().split(" "))
X = list(map(int, input().split(" ")))

i = 1
seq = [X[0]] * X[0]
while i < N:
    temp = seq[i] if i < len(seq) else X[i % M]
    seq += [X[i % M]] * temp
    i += 1

for j in range(N):
    print(seq[j])

````
