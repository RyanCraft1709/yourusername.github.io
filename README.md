import turtle

def draw_escher_square(x, y, size, depth):
    if depth == 0:
        # Desenhar um quadrado simples
        turtle.penup()
        turtle.goto(x, y)
        turtle.pendown()
        for _ in range(4):
            turtle.forward(size)
            turtle.right(90)
    else:
        # Dividir o quadrado em quatro sub-quadrados
        draw_escher_square(x, y, size/2, depth-1)
        draw_escher_square(x+size/2, y, size/2, depth-1)
        draw_escher_square(x, y+size/2, size/2, depth-1)
        draw_escher_square(x+size/2, y+size/2, size/2, depth-1)

# Inicializar a turtle
turtle.speed(0)
turtle.hideturtle()

# Desenhar o quadrado de Escher
draw_escher_square(-200, -200, 400, 4)

# Mostrar o resultado
turtle.done()
