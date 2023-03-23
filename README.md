# Ping-pong-game-python-


from turtle import Turtle


class Ball(Turtle):

    def __init__(self):
        super().__init__()
        self.shape('circle')
        self.color('white')
        self.penup()
        self.y_move = 10
        self.x_move = 10
        self.move_speed = 0.1

    def move(self):
        new_x = self.xcor() + self.x_move
        new_y = self.ycor() + self.y_move
        self.goto(new_x, new_y)

    def y_bounce(self):
        self.y_move *= -1


    def x_bounce(self):
        self.move_speed *= 0.3
        self.x_move *= -1

    def reset_position(self):
        self.goto(0, 0)
        self.move_speed = 1
        self.x_bounce()
