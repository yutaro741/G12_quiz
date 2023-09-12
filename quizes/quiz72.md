![298045CE-F5EC-4511-A7DC-D49F9551D5D9](https://github.com/yutaro741/G12_quiz/assets/111973553/5a84c33d-ff1e-4dae-8885-d74158bc97c0)
Input:
```.py
import random
def slmacGenerator(N:int):#One line coding
    return [f"{hex(random.randint(0, 255))[2:]}:{hex(random.randint(0, 255))[2:]}:{hex(random.randint(0, 255))[2:]}:{hex(random.randint(0, 255))[2:]}:{hex(random.randint(0, 255))[2:]}:{hex(random.randint(0, 255))[2:]}" for i in range(N)]

def hlmacGenerator(N:int):
    out = []
    alf = {0:"0", 1:"1", 2:"2", 3:"3", 4:"4", 5:"5", 6:"6", 7:"7", 8:"8", 9:"9", 10:"A", 11:"B", 12:"C", 13:"D", 14:"E", 15:"F"}#Change base 10 to base 16
    while len(out)<N:#Loop until output things gets N
        s = ""
        for i in range(6):#Loop for 6 structures
            for i in range(2):#Loop for 2 digits
                s += alf[random.randint(0, 15)]#Add random one digit number with base 16
            s += ":"#Add ":" after the structure
        state = True
        for i in out:
            if i == state:#Find there is no dupulication
                state = False
        if state:
            out.append(s[:-1])#Add Mac with reducing last ":"
    return out

print(slmacGenerator(5))
print(hlmacGenerator(5))
```

Output:
```
['ff:d6:67:9c:63:fe', 'e6:19:3:d1:43:6c', '50:f0:8e:22:a9:23', 'ae:8:3f:88:b4:17', '86:cb:ae:77:2c:e4']
['33:71:57:C7:2A:28', '8A:00:20:E9:EE:88', '01:32:AD:7A:14:3D', '91:08:22:B5:C6:06', 'FF:DE:87:B3:D8:F4']
```
