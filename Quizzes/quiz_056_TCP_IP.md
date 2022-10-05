### TCP/IP

```.py
class ip_packet:
    def __init__(self, port_tx: int, port_rx: int, mac_tx: str, mac_rx: str, ip_tx: str, ip_rx: str):
        self.port_tx = self.binarizer(port_tx)
        self.port_rx = self.binarizer(port_rx)
        self.mac_tx = self.maclist2binary(mac_tx.split(":"))
        self.mac_rx = self.maclist2binary(mac_rx.split(":"))
        self.ip_tx = self.iplist2binary(ip_tx.split("."))
        self.ip_rx = self.iplist2binary(ip_rx.split("."))

    def hex2dec(self, num: str):
        symbols = {"A": 10, "B": 11, "C": 12, "D": 13, "E": 14, "F": 15}
        result = 0
        for index, digit in enumerate(num):
            if digit in "0123456789":
                digit_dec = int(digit)
            else:
                digit_dec = symbols[digit]
            result += 16 ** (len(num) - 1 - index) * digit_dec
            return result

    def binarizer(self, number: int):
        result = ''
        while number > 0:
            result = str(number % 2) + result
            number = number // 2
        return result.rjust(8, "0")

    def maclist2binary(self, mac):
        result = ""
        for element in mac:
            result += self.binarizer(self.hex2dec(element))
        return result

    def iplist2binary(self, ip):
        result = ''
        for element in ip:
            result += self.binarizer(int(element))
        return result

    def build(self):
        return self.port_rx + self.port_tx + self.mac_rx + self.mac_tx + self.ip_rx + self.ip_tx
```

![]()
