```.py
import csv
from flask import send_file
from kivymd.app import MDApp
from kivymd.uix.screen import MDScreen
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.schema import Column
from sqlalchemy.testing import db
from sqlalchemy.types import Integer, String


db_engine = create_engine("sqlite:///Mahjong.db")
Base = declarative_base()


class User_database(Base):
    __tablename__ = "MahjongRecords"  # name the table
    id = Column(Integer, primary_key=True)
    hoju_rate = Column(Integer)
    hora_rate = Column(Integer)
    furo_rate = Column(Integer)
    reach_rate = Column(Integer)
    avg_final_score = Column(Integer)
    dist_final_rank = Column(Integer)


class UserInput(Base):
    __tablename__ = "User_input"
    game_id = Column(Integer, primary_key=True)
    num_games = Column(Integer)
    num_hoju = Column(Integer)
    num_hora = Column(Integer)
    num_furo = Column(Integer)
    num_reach = Column(Integer)
    final_score = Column(Integer)
    final_rank = Column(Integer)


Base.metadata.create_all(db_engine)

dbsession = sessionmaker(db_engine)  # Create a class for session
session = dbsession()


class MahjongApp(MDApp):
    def build(self):
        pass


class MainScreen(MDScreen):
    # changes the screen
    def go_calculator(self):
        self.parent.current = "CalculatorScreen"

    def go_records(self):
        self.parent.current = "RecordScreen"


class CalculatorScreen(MDScreen):
    def __init__(self, *args, **kwargs):
        super().__init__(*args, **kwargs)
        self.val = True
        self.dealer = "dealer"
        self.waryo = "Ron"

    # change the screen
    def go_back(self):
        self.parent.current = "MainScreen"

    # def checkbox_click(self, instance, value):
    #     if value:
    #         self.val = True
    #     else:
    #         self.val = False

    def on_lead(self, onoff):
        if onoff.state == "down":
            self.dealer = "None"
            self.ids.Leader.text = "Non-leader"
        elif onoff.state == "normal":
            self.dealer = "dealer"
            self.ids.Leader.text = "Leader"

    def on_agari(self, onoff):
        if onoff.state == "down":
            self.waryo = "Tsumo"
            self.ids.Agari.text = "Tsumo"
        elif onoff.state == "normal":
            self.waryo = "Ron"
            self.ids.Agari.text = "Ron"

    def calculate(self):
        if int(self.ids.Fu.text) % 10 != 0:
            self.ids.Fu.text = str((int(self.ids.Fu.text)//10+1)*10)
        elif int(self.ids.Fu.text) % 10 == 0:
            self.ids.Fu.text = str((int(self.ids.Fu.text)//10)*10)

        rules = {}

        if self.dealer == "dealer":
            if self.waryo == "Tsumo":
                if int(self.ids.Han.text) == 1:
                    rules = {30: "500 all", 40: "700 all", 50: "800 all", 60: "1000 all", 70: "1200 all"}
                elif int(self.ids.Han.text) == 2:
                    rules = {20: "700 all", 25: "800 all", 30: "800 all", 40: "1000 all", 50: "1300 all",
                             60: "1600 all", 70: "2000 all"}
                elif int(self.ids.Han.text) == 3:
                    rules = {20: "1300 all", 25: "1600 all", 30: "2000 all", 40: "2600 all", 50: "3200 all",
                             60: "3900 all", 70: "4000 all"}
                elif int(self.ids.Han.text) == 4:
                    rules = {20: "2600 all", 25: "3200 all", 30: "3900 all", 40: "4000 all", 50: "4000 all",
                             60: "4000 all", 70: "4000 all"}
                elif int(self.ids.Han.text) >= 5:
                    self.ids.Score.text = "4000 all"
                elif 7 >= int(self.ids.Han.text) >= 6:
                    self.ids.Score.text = "6000 all"
                elif 10 >= int(self.ids.Han.text) >= 8:
                    self.ids.Score.text = "8000 all"
                elif 12 >= int(self.ids.Han.text) >= 11:
                    self.ids.Score.text = "12000 all"
                elif int(self.ids.Han.text) >= 13:
                    self.ids.Score.text = "16000 all"
            elif self.waryo == "Ron":
                if int(self.ids.Han.text) == 1:
                    rules = {30: "1500", 40: "2000", 50: "2400",
                             60: "2900", 70: "3400"}
                elif int(self.ids.Han.text) == 2:
                    rules = {20: "2000", 25: "2400", 30: "2900", 40: "3900", 50: "4800",
                             60: "5800", 70: "6800"}
                elif int(self.ids.Han.text) == 3:
                    rules = {20: "3900", 25: "4800", 30: "5800", 40: "7700", 50: "9600",
                             60: "11600", 70: "12000"}
                elif int(self.ids.Han.text) == 4:
                    rules = {20: "7700", 25: "9600", 30: "11600", 40: "12000", 50: "12000",
                             60: "12000", 70: "12000"}
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
                    rules = {30: "300/500", 40: "400/700", 50: "400/800", 60: "500/1000", 70: "600/1200"}
                elif int(self.ids.Han.text) == 2:
                    rules = {20: "400/700", 25: "400/800", 30: "500/1000", 40: "700/1300", 50: "800/1600",
                             60: "1000/2000", 70: "1200/2300"}
                elif int(self.ids.Han.text) == 3:
                    rules = {20: "700/1300", 25: "800/1600", 30: "1000/2000", 40: "1300/2600", 50: "1600/3200",
                             60: "2000/3900", 70: "2000/4000"}
                elif int(self.ids.Han.text) == 4:
                    rules = {20: "1300/2600", 25: "1600/3200", 30: "2000/3900", 40: "2000/4000", 50: "2000/4000",
                             60: "2000/4000", 70: "2000/4000"}
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
                    rules = {30: "1000", 40: "1300", 50: "1600",
                             60: "2000", 70: "2300"}
                elif int(self.ids.Han.text) == 2:
                    rules = {20: "1300", 25: "1600", 30: "2000",
                             40: "2600", 50: "3200", 60: "3900", 70: "4500"}
                elif int(self.ids.Han.text) == 3:
                    rules = {20: "2600", 25: "3200", 30: "3900",
                             40: "5200", 50: "6400", 60: "7700", 70: "8000"}
                elif int(self.ids.Han.text) == 4:
                    rules = {20: "5200", 25: "6400", 30: "7700",
                             40: "8000", 50: "8000", 60: "8000", 70: "8000"}
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

        if rules:
            for key, value in rules.items():
                if key == int(self.ids.Fu.text):
                    self.ids.Score.text = value

        if int(self.ids.Fu.text) > 70:
            self.ids.Score.text = "Error"


class RecordScreen(MDScreen):
    # changes the screen
    def go_back(self):
        self.parent.current = "MainScreen"

    def go_history(self):
        self.parent.current = "HistoryScreen"

    def go_addRecords(self):
        self.parent.current = "AddRecordsScreen"


class AddRecordsScreen(MDScreen):
    def go_back(self):
        self.parent.current = "RecordScreen"

    def add_data(self):
        user_a = UserInput(num_games=self.ids.Games.text, num_hoju=self.ids.Hoju.text, num_hora=self.ids.Hora.text,
                           num_furo=self.ids.Furo.text, num_reach=self.ids.Reach.text, final_score=self.ids.Score.text,
                           final_rank=self.ids.Rank.text)
        session.add(user_a)
        session.commit()
        total_game, total_hoju, total_hora, total_furo, total_reach, total_final_score, total_final_rank = \
            0, 0, 0, 0, 0, 0, 0

        # columns = [UserInput.num_games, UserInput.num_hora]
        # totals = [0,0,0,0,0]
        # for i in range(session.query(UserInput.game_id).count()):
        #     for index, c in enumerate(columns):
        #         if session.query(c).filter(UserInput.game_id == i + 1).first()[0]:
        #             totals[index] += int(session.query(c).filter(UserInput.game_id == i+1).first()[0])
        for i in range(session.query(UserInput.game_id).count()):
            if session.query(UserInput.num_games).filter(UserInput.game_id == i+1).first()[0]:
                total_game += int(session.query(UserInput.num_games).filter(UserInput.game_id == i+1).first()[0])
            if session.query(UserInput.num_hoju).filter(UserInput.game_id == i+1).first()[0]:
                total_hoju += int(session.query(UserInput.num_hoju).filter(UserInput.game_id == i+1).first()[0])
            if session.query(UserInput.num_hora).filter(UserInput.game_id == i+1).first()[0]:
                total_hora += int(session.query(UserInput.num_hora).filter(UserInput.game_id == i+1).first()[0])
            if session.query(UserInput.num_furo).filter(UserInput.game_id == i+1).first()[0]:
                total_furo += int(session.query(UserInput.num_furo).filter(UserInput.game_id == i+1).first()[0])
            if session.query(UserInput.num_reach).filter(UserInput.game_id == i+1).first()[0]:
                total_reach += int(session.query(UserInput.num_reach).filter(UserInput.game_id == i+1).first()[0])
            if session.query(UserInput.final_score).filter(UserInput.game_id == i+1).first()[0]:
                total_final_score += int(session.query(UserInput.final_score).filter(UserInput.game_id == i+1).first()[0])
            if session.query(UserInput.final_rank).filter(UserInput.game_id == i+1).first()[0]:
                total_final_rank += int(session.query(UserInput.final_rank).filter(UserInput.game_id == i+1).first()[0])
        user_c = session.query(User_database).filter(User_database.id == 1).first()
        user_c.hoju_rate = round(total_hoju / total_game, 3)
        user_c.hora_rate = round(total_hora / total_game, 3)
        user_c.furo_rate = round(total_furo / total_game, 3)
        user_c.reach_rate = round(total_reach / total_game, 3)
        user_c.avg_final_score = round(total_final_score / total_game, 3)
        user_c.dist_final_rank = round(total_final_rank / total_game, 3)
        session.commit()
        # session.query(User_database).delete()
        # user_c = User_database(hoju_rate=0,hora_rate=0,furo_rate=0,reach_rate=0,avg_final_score=0,dist_final_rank=0)
        # session.add(user_c)
        # session.commit()


class HistoryScreen(MDScreen):
    def go_back(self):
        self.parent.current = "RecordScreen"

    def update(self):
        user_d = session.query(User_database).filter(User_database.id == 1).first()
        self.ids.Hoju_rate.text = str(user_d.hoju_rate)
        self.ids.Hora_rate.text = str(user_d.hora_rate)
        self.ids.Furo_rate.text = str(user_d.furo_rate)
        self.ids.Reach_rate.text = str(user_d.reach_rate)
        self.ids.Avg_final_score.text = str(user_d.avg_final_score)
        self.ids.Dist_final_rank.text = str(user_d.dist_final_rank)

    def download(self):
        data = session.query(UserInput).all()
        with open("Mahjong_record.csv", "w", newline="") as csvfile:
            csvwriter = csv.writer(csvfile, delimiter=",")
            csvwriter.writerow(["Number of Gams", "Number of Hoju", "Number of Hora", "Number of Furo",
                                "Number of Reach", "Final Score", "Final Rank"])
            for i in data:
                csvwriter.writerow([i.num_hoju, i.num_hora, i.num_furo, i.num_reach, i.final_score, i.final_rank])

        return send_file("../Mahjong_record.csv",
                         mimetype="text/csv",
                         as_attachment=True)


MahjongApp().run()
```
