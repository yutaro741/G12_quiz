![A8D416A8-A4DD-4482-9A29-340D6510FA01](https://github.com/yutaro741/G12_quiz/assets/111973553/80427dd6-af64-4291-927c-59776ea724b1)


```.py
def firewall(data):#
    num = 0
    for i in range(16):#convert first 16 digits to decimal
        num += 2**(15-i)*int(data[i])
    if num == 80 or num == 22123:#Check converted number is equal to 80 or 22123
        return "Allowed", data[16:]
    else:
        return "Filtered", None

datas = ["0101011001101011101001001001110010001", "01011001101011101001001001110010001"]
[print(firewall(data)) for data in datas]#Test for outputs

def firewall(data):#One line coding.
    return ("Allowed", data[16:]) if data[:16]=="0101011001101011" or data[:16]=="0000000001010000" else ("Filtered", None)

[print(firewall(data)) for data in datas]
```
Output:
```
('Allowed', '101001001001110010001')
('Filtered', None)
('Allowed', '101001001001110010001')
('Filtered', None)
```
