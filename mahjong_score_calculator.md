```.py
        if self.dealer == "dealer":
            if self.waryo == "Tsumo":
                if int(self.ids.Han.text) == 1:
                    rules = {30: "500 all", 40: "700 all"}
                    for key, value in rules.items():
                        if key == int(self.ids.Fu.text):
                            self.ids.Score.text = value
                    if int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "500 all"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "700 all"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "800 all"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "1000 all"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "1200 all"
                elif int(self.ids.Han.text) == 2:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "700 all"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "800 all"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "1000 all"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "1300 all"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "1600 all"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "2000 all"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "2300 all"
                elif int(self.ids.Han.text) == 3:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "1300 all"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "1600 all"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "2000 all"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "2600 all"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "3200 all"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "3900 all"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "4000 all"
                elif int(self.ids.Han.text) == 4:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "2600 all"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "3200 all"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "3900 all"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "4000 all"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "4000 all"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "4000 all"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "4000 all"
                elif int(self.ids.Han.text) >= 5:
                    self.ids.Score.text = "4000 all"
                elif 7 >= int(self.ids.Han.text) >= 6:
                    self.ids.Score.text = "6000"
                elif 10 >= int(self.ids.Han.text) >= 8:
                    self.ids.Score.text = "8000"
                elif 12 >= int(self.ids.Han.text) >= 11:
                    self.ids.Score.text = "12000"
                elif int(self.ids.Han.text) >= 13:
                    self.ids.Score.text = "16000"
            elif self.waryo == "Ron":
                if int(self.ids.Han.text) == 1:
                    if int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "1500"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "2000"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "2400"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "2900"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "3400"
                elif int(self.ids.Han.text) == 2:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "2000"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "2400"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "2900"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "3900"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "4800"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "5800"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "6800"
                elif int(self.ids.Han.text) == 3:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "3900"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "4800"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "5800"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "7700"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "9600"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "11600"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "12000"
                elif int(self.ids.Han.text) == 4:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "7700"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "9600"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "11600"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "12000"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "12000"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "12000"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "12000"
                elif int(self.ids.Han.text) >= 5:
                    self.ids.Score.text = "12000"
                elif 7 >= int(self.ids.Han.text) >= 6:
                    self.ids.Score.text = "18000"
                elif 10 >= int(self.ids.Han.text) >= 8:
                    self.ids.Score.text = "24000"
                elif 12 >= int(self.ids.Han.text) >= 11:
                    self.ids.Score.text = "36000"
                elif int(self.ids.Han.text) >= 13:
                    self.ids.Score.text = "48000"

        elif self.dealer == "None":
            if self.waryo == "Tsumo":
                if int(self.ids.Han.text) == 1:
                    if int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "300/500"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "400/700"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "400/800"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "500/1000"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "600/1200"
                elif int(self.ids.Han.text) == 2:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "400/700"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "400/800"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "500/1000"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "700/1300"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "800/1600"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "1000/2000"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "1200/2300"
                elif int(self.ids.Han.text) == 3:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "700/1300"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "800/1600"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "1000/2000"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "1300/2600"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "1600/3200"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "2000/3900"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "2000/4000"
                elif int(self.ids.Han.text) == 4:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "1300/2600"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "1600/3200"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "2000/3900"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "2000/4000"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "2000/4000"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "2000/4000"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "2000/4000"
                elif int(self.ids.Han.text) >= 5:
                    self.ids.Score.text = "2000/4000"
                elif 7 >= int(self.ids.Han.text) >= 6:
                    self.ids.Score.text = "3000/6000"
                elif 10 >= int(self.ids.Han.text) >= 8:
                    self.ids.Score.text = "4000/8000"
                elif 12 >= int(self.ids.Han.text) >= 11:
                    self.ids.Score.text = "6000/12000"
                elif int(self.ids.Han.text) >= 13:
                    self.ids.Score.text = "8000/16000"
            elif self.waryo == "Ron":
                if int(self.ids.Han.text) == 1:
                    if int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "1000"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "1300"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "1600"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "2000"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "2300"
                elif int(self.ids.Han.text) == 2:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "1300"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "1600"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "2000"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "2600"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "3200"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "3900"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "4500"
                elif int(self.ids.Han.text) == 3:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "2600"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "3200"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "3900"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "5200"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "6400"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "7700"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "8000"
                elif int(self.ids.Han.text) == 4:
                    if int(self.ids.Fu.text) == 20:
                        self.ids.Score.text = "5200"
                    elif int(self.ids.Fu.text) == 25:
                        self.ids.Score.text = "6400"
                    elif int(self.ids.Fu.text) == 30:
                        self.ids.Score.text = "7700"
                    elif int(self.ids.Fu.text) == 40:
                        self.ids.Score.text = "8000"
                    elif int(self.ids.Fu.text) == 50:
                        self.ids.Score.text = "8000"
                    elif int(self.ids.Fu.text) == 60:
                        self.ids.Score.text = "8000"
                    elif int(self.ids.Fu.text) == 70:
                        self.ids.Score.text = "8000"
                elif int(self.ids.Han.text) == 5:
                    self.ids.Score.text = "8000"
                elif 7 >= int(self.ids.Han.text) >= 6:
                    self.ids.Score.text = "12000"
                elif 10 >= int(self.ids.Han.text) >= 8:
                    self.ids.Score.text = "16000"
                elif 12 >= int(self.ids.Han.text) >= 11:
                    self.ids.Score.text = "24000"
                elif int(self.ids.Han.text) >= 13:
                    self.ids.Score.text = "32000"
```
