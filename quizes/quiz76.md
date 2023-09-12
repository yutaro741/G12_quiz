![C5C8FD0C-58D7-4AFA-B3AC-D6FFDA29FCB0](https://github.com/yutaro741/G12_quiz/assets/111973553/dbcb76ba-b48a-4cb7-8ebb-00bb5ca93010)

```.py
def error_check(data:str):
    return not data[:len(data)//3]==data[len(data)//3:2*len(data)//3]==data[2*len(data)//3:]#Split data into 3 parts and compare it. Easy!

def hl_error_check(data:str):
    a, b, c = data[:len(data)//3], data[len(data)//3:2*len(data)//3], data[2*len(data)//3:]
    return a if a == b == c else (a if a == b or a == c else (b if b == c else None))#This is shorten if statement. Potentially I can write within one line(With substituting a, b, c), but I didn't do this because it's so awkward.

num1 = "100111001011001110010110011100101"
print(error_check(num1), hl_error_check(num1))
num2 = "011101111101110111110111001111"
print(error_check(num2), hl_error_check(num2))
```

Output:
```
False 10011100101
True 0111011111
```
