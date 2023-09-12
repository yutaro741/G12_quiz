![06A80B81-CD64-4E75-B0DE-6C527C0EA20D](https://github.com/yutaro741/G12_quiz/assets/111973553/e600c809-0735-4b3a-835d-eaebff50252c)
Code:
```.py
def max_min(data:list):
    min, max = data[0], data[0]#Set initial value of min, max as first value.
    for i in range(len(data)):
        if min>data[i]:#If data is smaller than min, update min
            min = data[i]
        if max<data[i]:#If data is bigger than max, update max
            max = data[i]
    return max-min

print(max_min([100, 45, 12, 3, 56, 7]))
```
OUTPUT:
```
97
```
