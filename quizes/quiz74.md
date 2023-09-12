![8CD9E4E9-3BFD-4430-98EA-D72F355DBC58](https://github.com/yutaro741/G12_quiz/assets/111973553/05f6dac4-6c57-4c4d-ab02-22c067e771c2)

```.py
def build_data_pkg(mac_rx, ip_rx, mac_sx, mac_sc, data):
    return [f"{mac_rx}|{ip_rx}|{mac_sx}|{mac_sc}|{data[4*i:4*i+4]}" for i in range((len(data)+3)//4)]

print(build_data_pkg("80:90:AA:F0:22:11", "192.168.1.2", "30:AA:1A:F1:00:AE", "192.168.1.3", "Hello world"))

class data_pkg():#For HL content. With using class.
    def __init__(self, mac_rx, ip_rx, mac_sx, mac_sc):#Fix mac_rx, ip_rx, mac_sx, mac_sc and let only data as changing valiable.
        self.mac_rx = mac_rx
        self.ip_rx = ip_rx
        self.mac_sx = mac_sx
        self.mac_sc = mac_sc
    def build_data_pkg(self, data):
        out = []
        import math
        for i in range(math.ceil(len(data)/4)):
            out.append(f"{self.mac_rx}|{self.ip_rx}|{self.mac_sx}|{self.mac_sc}|{data[4*i:4*i+4]}")#I didn't know that x for str[:x] can be more than length of str!!
        return out

pkg = data_pkg("80:90:AA:F0:22:11", "192.168.1.2", "30:AA:1A:F1:00:AE", "192.168.1.3")
print(pkg.build_data_pkg("I love one line coding"))
print(pkg.build_data_pkg("However I can't use in the actual test"))
```

Output:
```
['80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|Hell', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|o wo', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|rld']
['80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|I lo', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|ve o', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|ne l', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|ine ', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|codi', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|ng']
['80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|Howe', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|ver ', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|I ca', "80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|n't ", '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|use ', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|in t', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|he a', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|ctua', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|l te', '80:90:AA:F0:22:11|192.168.1.2|30:AA:1A:F1:00:AE|192.168.1.3|st']

```
