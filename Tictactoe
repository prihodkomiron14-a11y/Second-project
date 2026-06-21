import turtle

screen = turtle.Screen()
screen.bgcolor("#FFFFFF")
screen.setup(0.5, 0.5)
screen.title("Хрестики Нулики")

pen = turtle.Turtle()
pen.color("black")
pen.pensize(4)
pen.speed(0)
pen.hideturtle()

cells = [
    None, None, None, 
    None, None, None, 
    None, None, None
]

def draw_square():
    for i in range (4) :
        pen.forward(100)
        pen.right(90)

def draw_line():
    for i in range (3):
        draw_square()
        pen.forward(100)

def draw_field():
    y = 150
    for i in range(3):
        pen.penup()
        pen.goto(-150, y)
        pen.pendown()
        draw_line()
        y -= 100  
            
draw_field()

def cross(x, y):
    pen.color("#FB0148")
    pen.penup()
    pen.goto(x, y)
    pen.pendown()
    pen.goto(x + 100, y - 100)
    pen.penup()
    pen.goto(x + 100, y)
    pen.pendown()
    pen.goto(x, y - 100)

def zero(x, y):
    pen.color("blue")
    pen.penup()
    pen.goto(x + 50, y - 100)
    pen.pendown()
    pen.circle(50)

turn = ['cross']

def winner_check(object):
    winner = False
    if cells[0] == object and cells[1] == object and cells[2] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(-150, 100)
        pen.pendown()
        pen.goto(150, 100)
    
    elif cells[3] == object and cells[4] == object and cells[5] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(-150, 0)
        pen.pendown()
        pen.goto(150, 0)
    elif cells[6] == object and cells[7] == object and cells[8] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(-150, -100)
        pen.pendown()
        pen.goto(150, -100)        
    elif cells[0] == object and cells[3] == object and cells[6] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(-100, 150)
        pen.pendown()
        pen.goto(-100, -150)
    elif cells[1] == object and cells[4] == object and cells[7] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(0, -150)
        pen.pendown()
        pen.goto(0, -150)
    elif cells[2] == object and cells[5] == object and cells[8] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(100, 150)
        pen.pendown()
        pen.goto(100, -150)
    elif cells[0] == object and cells[4] == object and cells[8] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(-150, 150)
        pen.pendown()
        pen.goto(150, -150)
    elif cells[2] == object and cells[4] == object and cells[6] == object:
        winner = True
        pen.color("black")
        pen.penup()
        pen.goto(150, 150)
        pen.pendown()
        pen.goto(-150, -150)
    if winner:
        pen.penup()
        pen.goto(0, 220)
        pen.pendown()
        pen.write(f'{object} wining', font=('Arial', 24, 'bold'))
    

def click(x, y):
    
    cell_x = None
    cell_y = None
    
    if x > -150 and x < -50:
        cell_x = -150
        cell_index = 0
    elif x > -50 and x < 50:
        cell_x = -50
        cell_index = 1
    elif x > 50 and x < 150:
        cell_x = 50
        cell_index = 2
        
    if y > 50 and y < 150:
        cell_y = 150
    elif y > -50 and y < 50:
        cell_y = 50
        cell_index += 3
    elif y > -150 and y < -50:
        cell_y = -50
        cell_index += 6

    if cell_x != None and cell_y != None:
        if cells[cell_index] == None:
            if turn[0] == 'cross':
                cells[cell_index] = 'cross'
                cross(cell_x, cell_y)
                winner_check('cross')
                turn[0] = 'zero'
                
            else:
                cells[cell_index] = 'zero'
                zero(cell_x, cell_y)
                winner_check('zero')
                turn[0] = 'cross'
                



screen.onclick(click)
screen.mainloop()
