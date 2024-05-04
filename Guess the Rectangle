import turtle
from random import randint

class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def falls_in_rectangle(self, rectangle):
        if rectangle.point1.x < self.x < rectangle.point2.x \
                and rectangle.point1.y < self.y < rectangle.point2.y:
            return True
        else:
            return False

class Rectangle:
    def __init__(self, point1, point2):
        self.point1 = point1
        self.point2 = point2

    def area(self):
        return abs((self.point2.x - self.point1.x) * \
               (self.point2.y - self.point1.y))

def play_game():
    # Create rectangle object
    rectangle = Rectangle(Point(randint(0, 300), randint(0, 300)),
                          Point(randint(50, 350), randint(50, 350)))

    # Get point and area from user
    user_point = Point(float(input("Guess x: ")), float(input("Guess y: ")))
    user_area = float(input("Guess rectangle area: "))

    # Print rectangle coordinates
    print("Rectangle Coordinates: ",
          rectangle.point1.x, ",",
          rectangle.point1.y, "and",
          rectangle.point2.x, ",",
          rectangle.point2.y)

    # Print out the game result
    print("Your point was inside rectangle: ", user_point.falls_in_rectangle(rectangle))
    print("Your area was off by: ", abs(rectangle.area() - user_area))

    # Draw rectangle using turtle
    screen = turtle.Screen()
    screen.setworldcoordinates(0, 0, 400, 400)  # Adjust window dimensions
    myturtle = turtle.Turtle()
    myturtle.penup()
    myturtle.goto(rectangle.point1.x, rectangle.point1.y)
    myturtle.pendown()
    myturtle.goto(rectangle.point2.x, rectangle.point1.y)
    myturtle.goto(rectangle.point2.x, rectangle.point2.y)
    myturtle.goto(rectangle.point1.x, rectangle.point2.y)
    myturtle.goto(rectangle.point1.x, rectangle.point1.y)

    # Draw user input points
    myturtle.penup()
    myturtle.goto(user_point.x, user_point.y)
    myturtle.dot(10, "red")

    turtle.done()  # Keeps the window open

# Call the function to play the game
play_game()
