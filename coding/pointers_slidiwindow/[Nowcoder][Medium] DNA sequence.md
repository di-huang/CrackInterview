[DNA sequence](https://www.nowcoder.com/practice/e8480ed7501640709354db1cc4ffd42a?tpId=37&tqId=21286&rp=1&ru=%2Fta%2Fhuawei&qru=%2Fta%2Fhuawei%2Fquestion-ranking&tab=answerKey) <br />
Easy sliding window question. <br />

**Algorithm:** <br />
Just set a sliding window of size N and update the string with the largest GC-Ratio. <br />
````python
X = input()
N = int(input())

res_str, res_num = X[:N], 0
for i in range(N):
    if res_str[i] == 'C' or res_str[i] == 'G':
        res_num += 1

cur_num = res_num
i, j = 1, N
while j < len(X):
    if X[i - 1] == 'C' or X[i - 1] == 'G':
        cur_num -= 1
    if X[j] == 'C' or X[j] == 'G':
        cur_num += 1
    if cur_num > res_num:
        res_num = cur_num
        res_str = X[i : j + 1]
    i += 1
    j += 1

print(res_str)
````

