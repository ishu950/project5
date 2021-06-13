# project5
turtle race
import random
from turtle import Turtle,Screen

screen=Screen()
is_race_on=False
screen.setup(width=500,height=400)
user_bet=screen.textinput(title="Make your bet",prompt="which turtle will win the race? red or green")
color=["red","green","orange","pink","purple","black","yellow"]

y_pos=[-70,-40,-10,20,50,80]
all_turtle=[]
for i in range (0,6):
    tom=Turtle(shape="turtle")
    tom.color(color[i])
    tom.penup()
    tom.goto(x=-230,y=y_pos[i])
    all_turtle.append(tom)
if user_bet:
    is_race_on=True
while is_race_on:
    for i in all_turtle:
        if i.xcor() > 230:
            is_race_on=False
            winning_color=i.pencolor()
            if winning_color==user_bet:
                print(f"you win {winning_color}is winner")
            else:
                print(f"you lost and winner is {winning_color}")




        random_dis=random.randint(0, 10)
        i.forward(random_dis)





screen.exitonclick()
