![298045CE-F5EC-4511-A7DC-D49F9551D5D9](https://github.com/yutaro741/G12_quiz/assets/111973553/254e4958-8a41-423d-9634-ca600e7e117b)

CODING:
```.py
def build_data_pkg(new_mac, prev_mac, prev_ips):
    k = 0
    for i in range(len(prev_mac)):#Check there is same mac address or not.
        if prev_mac[i] == new_mac:
            k = i
    if prev_ips == []:#Add initial address if there is none.
        prev_ips.append("192.168.0.0")
    elif k==0:
        ip = []
        for i in prev_ips:
            i = i.split(".")
            ip.append(int(i[-2])*256+int(i[-1]))
        n = max(ip)+1
        prev_ips.append(f"""192.168.{n//256}.{n%256}""")#Make another ip address if different.
    else:
        prev_ips.append(prev_mac[i])#Add corresponding ip address if same
    prev_mac.append(new_mac)
    return prev_mac, prev_ips

mac = []
ip = []
while True:#Loop forever
    mac_add = input()
    mac, ip = build_data_pkg(mac_add, mac, ip)
    for i in range(len(mac)):
        print(mac[i], ip[i])
```

Input:
```
00:1A:2B:3C:4D:5E
12:34:56:78:90:AB
00:1A:2B:3C:4D:5E
FF:EE:DD:CC:BB:AA
```

Output:

<img width="433" alt="Screen Shot 2023-09-12 at 16 03 07" src="https://github.com/yutaro741/G12_quiz/assets/111973553/f46d4c9d-e89c-4c07-9aa6-05db092ec5f8">
