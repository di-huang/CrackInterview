1. [Medium]压缩算法
````python
class Solution:
    def compress(self , str):
        left = str.rfind('[')
        while left != -1:
            right = str.find(']', left)
            num, temp = str[left + 1 : right].split('|')
            str = str[:left] + int(num) * temp + str[right + 1 : ]
            left = str.rfind('[')
        return str
````