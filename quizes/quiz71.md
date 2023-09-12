![71CFE9B5-856A-4118-8BFD-C0F4FA2FAF20](https://github.com/yutaro741/G12_quiz/assets/111973553/fbfb3f33-4a7f-4b2d-87ec-17429cc2a1b5)

Input:
```.py
import random
def sliPv6machine(N:int):#one line coding
    return [f"{hex(random.randint(0, 65535))[2:]}:{hex(random.randint(0, 65535))[2:]}:{hex(random.randint(0, 65535))[2:]}:{hex(random.randint(0, 65535))[2:]}:{hex(random.randint(0, 65535))[2:]}:{hex(random.randint(0, 65535))[2:]}:{hex(random.randint(0, 65535))[2:]}:{hex(random.randint(0, 65535))[2:]}" for i in range(N)]


def hliPv6machine(N:int):
    out = []
    alf = {0:"0", 1:"1", 2:"2", 3:"3", 4:"4", 5:"5", 6:"6", 7:"7", 8:"8", 9:"9", 10:"A", 11:"B", 12:"C", 13:"D", 14:"E", 15:"F"}#Change within base 10 to base 16
    while len(out)<N:#Loop until number of iPv6 gets more than N
        all = ""
        for i in range(8):#Loop for 8 structures
            for i in range(4):#Loop for 4 characters
                all += alf[random.randint(0, 15)]#Add random 1-digit number with base 16
            all += ":"#Add ":" in each structures
        out.append(s[:-1])#Remove ":" for the last structure
        out = list(set(out))#Check if there is no same iPv6.
    return out

print(sliPv6machine(5))
print(hliPv6machine(5))
```

Output:
```
['214b:307c:ed2c:130c:2a6f:2e3:c073:1b19', 'd0bd:f1b9:38db:a096:c3f9:ee72:9e4e:6197', 'd82b:7a13:f96f:7beb:85e2:fa71:8f31:d86c', '3606:d5be:9483:27dd:24dd:91b1:75ca:56b', 'a06a:9803:d3db:addc:2583:3256:3a27:d561']
['5518:E02C:11D4:9800:2C65:E718:76D1:BA95', '4299:133E:ABC2:E6CB:3323:4C0C:8400:4E4C', '6854:EF60:3CA0:4EEC:0072:75C6:B553:80E3', '8750:CB33:7E01:D6EA:C752:E754:CFFC:8BC8', '7F9C:A5AF:2428:CB5E:8004:4A4D:7F6D:48F1']
```
