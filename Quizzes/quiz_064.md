### Queue to stack

```.py
from quiz_62 import Stack
from Queue import queue
import random


def sort_q2s(scores):
    output = Stack()
    while not scores.ismepty():
        copy = queue()
        min = 10
        while not scores.ismepty():
            item = scores.dequeue()
            if item < min:
                min = item
            copy.enqueue(item)
        #remove the min from original queue
        scores = copy
        copy = queue() #empty queue

        while not scores.ismepty():
            item = scores.dequeue()
            if item == min:
                output.push(item)
            else:
                copy.enqueue(item)
        scores = copy
    return output


scores = queue()
for _ in range(10):
    scores.enqueue(random.randint(1, 8))

print(f"Original: {scores}, Output:{sort_q2s(scores)}")
```

#### quiz_62.py

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

    def __repr__(self):
        output = ''
        for i in self.data:
            output += str(i) + " "
        return output[:-1]
```

#### Queue.py

```.py
class queue:
    def __init__(self):
        self.data = []

    def enqueue(self, value):
        self.data.append(value)

    def dequeue(self):
        if not self.data:
            return "None"
        else:
            x = self.data[0]
            del self.data[0]
            return x

    def empty(self):
        self.data = []

    def ismepty(self):
        if len(self.data) == 0:
            return True
        else:
            return False

    def data(self):
        z = "|"
        for i in range(len(self.data)):
            z += str(self.data[i])+"|"
        y = "_" * len(z)
        y1 = "‾" * len(z)
        y += "\n" + z + "\n" + y1
        return y

    def __repr__(self):
        output = ''
        for i in self.data:
            output += str(i) + " "
        return output[:-1]
```

![]()
