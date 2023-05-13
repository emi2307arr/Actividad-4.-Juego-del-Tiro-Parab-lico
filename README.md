# Actividad-4.-Juego-del-Tiro-Parab-lico

speed.y -= 0.35 a speed.y -= 0.5 o speed.y -= 1.0

aumentar la velocidad de los objetivos ajustando el valor de la coordenada x en la línea target.x -= 0.5

target.x -= 1.0 o target.x -= 2.0

# Definimos el movimiento del proyectil y objetivos
    
def move():
    "Move ball and targets."
    if randrange(40) == 0:
        y = randrange(-150, 150)
        target = vector(200, y)
        targets.append(target)

    for target in targets:
        target.x -= 0.5

  # Reposiciona el  objetivo al otro lado de la ventana si toca el borde
        if not inside(target):
            target.x = 200

    if inside(ball):
        speed.y -= 0.35
        ball.move(speed)

   # Reposicionar bola al otro lado de la ventana cuando toque el borde
    if not inside(ball):
        ball.x *= -1
        ball.y *= -1
