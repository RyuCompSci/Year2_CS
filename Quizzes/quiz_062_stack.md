### Stack

```.py
class Stack:
    def __init__(self):
        self.data = []

    def pop(self):
        x = self.data[-1]
        del self.data[-1]
        return x

    def push(self, value):
        self.data.append(value)

    def isempty(self):
        if len(self.data) == 0:
            return "True"
        else:
            return "False"

    def data(self):
        for i in self.data:
            return i

class adder:
    def __init__(self, text):
        self.stack_text = text

    def sum(self):
        s = 0
        while not self.stack_text.isempty():
            s += ord(self.stack_text.pop())-96
        return s
```
