### Pattern

```.py
class Pattern:
    def __init__(self):
        pass

    def p_pattern(self):
        x = ["\33[0;31m red", "\33[0;34m blue", "\33[0;32m green", "\33[0;30m black"] #coloring the characters
        y = ""
        z = 0
        for i in range(5): #organizing the columns and rows
            for j in range(5):
                y = y + x[z%4] + " "
                z += 1
            y = y + "\n"
        return y
```

![](quiz_60py.png)
