![8C438D65-FC85-46A7-87DB-8EC94458D2D3](https://github.com/yutaro741/G12_quiz/assets/111973553/3ba59e0f-6f20-4b75-99fb-8ca01b3561df)

```.py
def bin(N):#Function that return 8 digit binary number from base 10 integer.
    out = ""
    for i in range(8):
        out += str((N//2**i)%2)
    return out[::-1]

def converter(data):
    out = ""
    for i in range(len(data)):
        out += bin(ord(data[i]))#Convert chalacter to number, and change it to binary.
        out += " "#add space after each chalacter
    return out[:-1]#return with Deleteing last " "

print(converter("Hello World!"))
print(converter("42 is the answer."))
print(converter("ABC123"))
```

Output:
```
01001000 01100101 01101100 01101100 01101111 00100000 01010111 01101111 01110010 01101100 01100100 00100001
00110100 00110010 00100000 01101001 01110011 00100000 01110100 01101000 01100101 00100000 01100001 01101110 01110011 01110111 01100101 01110010 00101110
01000001 01000010 01000011 00110001 00110010 00110011

```
