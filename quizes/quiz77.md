![49B2730A-97CF-406C-8CB6-C94F04053D6F](https://github.com/yutaro741/G12_quiz/assets/111973553/48ba8289-ef5b-4c46-a9ef-20ce17969a82)

```.py
def porarity_check(data):
    return data[1:].count("1")%2==int(data[0])#One line coding but using count.

num = ["100111001011001110010110011100101", "011101111101110111110111001111"]
[print(porarity_check(i)) for i in num]

def porarity_check(data):
    out = 0
    for i in range(1, len(data)):
        if data[i]=="1":#Count the number of "1" in the data
            out += 1
    return int(data[0])==out%2 #Find out with using mod2.

[print(porarity_check(i)) for i in num]
```

Output:
```
True
False
True
False
```
