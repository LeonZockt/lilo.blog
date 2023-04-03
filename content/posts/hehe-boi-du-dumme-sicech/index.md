+++
title = "Recoding SMB1 "
date = "2023-04-03"
draft = false
pinned = false
tags = []
image = "goomba.png"
description = "\n"
footnotes = "HeHeHeHa"
+++


```
import pgzrun
import time
import random
Zielbedingung = 0
Boden = 599
WIDTH = 768
HEIGHT = 720
GRAVITY = 0.5
m_y_beschl = 0
gravity = True
TITLE = "The Super Mario Bros."
background = Actor("blue")

zähler = 0
#Zufallsvariablen
Zufall = random.randint(0,WIDTH)
Cloudhöhen = random.randint(-29, 29)
Cloudhöheneiner = random.randint(0, 50)
Buschentscheider = random.randint(1,3)


#LEVEL:
f1 = Actor("questionmark")
f1.left = WIDTH + 96
f1.y = HEIGHT - 144 - 96 -48

brick = Actor("brick")
brick.left = WIDTH + 288
brick.y = HEIGHT - 144 - 96 -48

f2 = Actor("questionmark")
f2.left = WIDTH + 288 + 48
f2.y = HEIGHT - 144 - 96 -48

brick2 = Actor("brick")
brick2.left = WIDTH + 288 + 96
brick2.y = HEIGHT - 144 - 96 -48

f3 = Actor("questionmark")
f3.left = WIDTH + 288 + 48 + 96
f3.y = HEIGHT - 144 - 96 -48

brick3 = Actor("brick")
brick3.left = WIDTH + 288 + 96 + 96
brick3.y = HEIGHT - 144 - 96 -48


f4 = Actor("questionmark")
f4.left = WIDTH + 288  + 96
f4.y = HEIGHT - 144 - 96 - 48 - 144 -48



#LOGO:
logo = Actor("logosus", center=(384,200))
cop = Actor("cop" , center= (384,340))
#Boden:
b = Actor("bottom")
b.left = 0
b.bottom = HEIGHT

#Boden 2:
b2 = Actor("bottom")
b2.left = b.right
b2.bottom = HEIGHT

#Boden 3
b3 = Actor("bottom")
b3.left = b2.right
b3.bottom = HEIGHT

#Void
void = Actor("voidi")
void.left = WIDTH/2 - 64
void.bottom = b.top

#kleiner Hügel
sh =Actor("hill_small")
sh.x = 350
sh.bottom = b.top

#grosser Hügel
h =Actor("hill")
h.left = WIDTH
h.bottom = b.top


#BUsch

bush = Actor("bush")
bush.left = 0
bush.bottom = b.top

#Zweierbusch
bush2 = Actor("bush2")
bush2.top = b.bottom
bush2.left = 0


#Dreierbusch
bush3 = Actor("bush3")
bush3.top = b.bottom
bush3.left= 0

#Wolke

cloud = Actor("cloud")
cloud.x = WIDTH + 399
cloud.y = 50

#Zweierwolke
cloud2 = Actor("cloud2")
cloud2.x = WIDTH + 666
cloud2.y = 125

#Dreierwolke
cloud3 = Actor("cloud3")
cloud3.x = WIDTH + 120
cloud3.y = 200






pipetop1 = Actor("pipetop")
pipetop1.left = brick3.right + 144
pipetop1.bottom = b.top -48

pipebottom1 = Actor("pipebottom")
pipebottom1.bottom = b.top
pipebottom1.left = pipetop1.left + 6

pipetop2 = Actor("pipetop")
pipetop2.left = pipetop1.right + 384
pipetop2.bottom = b.top -96


pipebottom2 = Actor("pipebottom")
pipebottom2.bottom = b2.top 
pipebottom2.left = pipetop2.left + 6

pipebottom32 = Actor("pipebottom")
pipebottom32.bottom = pipebottom2.top
pipebottom32.left = pipetop2.left + 6

pipetop3 = Actor("pipetop")
pipetop3.left = pipetop2.right + 288
pipetop3.bottom = b.top -144

pipebottom34 = Actor("pipebottom")
pipebottom34.bottom = b.top
pipebottom34.left = pipetop3.left + 6

pipebottom31 = Actor("pipebottom")
pipebottom31.bottom = pipebottom34.top
pipebottom31.left = pipetop3.left + 6

pipebottom33 = Actor("pipebottom")
pipebottom33.bottom = pipebottom31.top
pipebottom33.left = pipetop3.left + 6


pipetop4 = Actor("pipetop")
pipetop4.left = pipetop3.right + 384
pipetop4.bottom = b.top - 144


pipebottom44 = Actor("pipebottom")
pipebottom44.bottom = b.top
pipebottom44.left = pipetop4.left + 6

pipebottom41 = Actor("pipebottom")
pipebottom41.bottom = pipebottom44.top
pipebottom41.left = pipetop4.left + 6

pipebottom43 = Actor("pipebottom")
pipebottom43.bottom = pipebottom41.top
pipebottom43.left = pipetop4.left + 6


void1 = Actor("void1")
void1.bottom = HEIGHT
void1.left = pipetop4.right + 480

void2 = Actor("void1")
void2.bottom = HEIGHT
void2.left = void1.right + 720



#Mario:
m = Actor('mario')
m.x = WIDTH/2
m.bottom = b.top

BewegendeListe = [b,b2,b3,void,logo,cop,h,sh,bush,f1,brick,f2,f3,brick2,brick3,f4,bush2,bush3, cloud, cloud2, cloud3,pipebottom1,pipetop1,pipetop2,pipebottom2,pipebottom32,pipetop4,pipetop3,pipebottom34,pipebottom33,pipebottom31,pipebottom41, pipebottom44, pipebottom43,void1,void2 ]

HitboxListe = [f1, f2, f3 , f4 , brick2 , brick3 ,  brick, b, b2 , b3,pipebottom1,pipetop1,pipetop2,pipebottom2,pipebottom32,pipetop4, pipetop3,pipebottom34,pipebottom33,pipebottom31,pipebottom41,pipebottom43,pipebottom44, ]

def draw():
    screen.clear()
    background.draw()
    void.draw()
    cloud.draw()
    cloud2.draw()
    cloud3.draw()
    cop.draw()
    logo.draw()

    cop.draw()

    h.draw()
    b.draw()
    b2.draw()
    b3.draw()
    sh.draw()
    bush.draw()
    bush2.draw()
    bush3.draw()
    f1.draw()
    brick.draw()
    f2.draw()
    f3.draw()
    brick2.draw()
    brick3.draw()
    f4.draw()
    pipebottom1.draw()
    pipetop1.draw()
    pipetop2.draw()
    pipebottom2.draw()
    pipebottom32.draw()
    pipetop3.draw()
    pipetop4.draw()
    pipebottom33.draw()
    pipebottom34.draw()
    pipebottom31.draw()
    pipebottom43.draw()
    pipebottom44.draw()
    pipebottom41.draw()
    void1.draw()
    void2.draw()


    m.draw()


def update():
    global Boden
    global Zufall
    global Cloudhöhen
    global Cloudhöheneiner
    global Buschentscheider
    global Zielbedingung
    global gravity
    global GRAVITY
    global zähler
    global m_y_beschl
    global element
    if Zielbedingung == 0:

        #Scrolling: (Noch Listen machen )
        if keyboard[keys.RIGHT]:
            for element in BewegendeListe:
                element.x = element.x -10

        if keyboard[keys.LEFT]:
            for element in BewegendeListe:
                element.x = element.x + 10

            if m.colliderect(void):
                for element in BewegendeListe:
                    element.x = element.x - 10





        if keyboard[keys.RIGHT] and keyboard[keys.Y]:
            for element in BewegendeListe:
                element.x = element.x - 12


        if keyboard[keys.LEFT] and keyboard[keys.Y]:
            for element in BewegendeListe:
                element.x = element.x + 12

                if m.colliderect(void):
                    for element in BewegendeListe:
                        element.x = element.x - 12


    #Wiederansetzen des Bodens
    if keyboard[keys.RIGHT]:
        if b.right <= 0:
            b.left = b3.right
        if b2.right <= 0:
            b2.left = b.right
        if b3.right <= 0:
            b3.left = b2.right
    if keyboard[keys.LEFT]:
        if b.left >= WIDTH:
            b.right = b3.left
        if b2.left >= WIDTH:
            b2.right = b.left
        if b3.left >= WIDTH:
            b3.right = b2.left

    if Zielbedingung == 0:
    # Schwerkraft
        if gravity == True :
            m_y_beschl += GRAVITY
        elif keyboard[keys.UP]:
                if keyboard[keys.Y]:
                    m_y_beschl = - 17
                else:
                    m_y_beschl = -15



        m.y += m_y_beschl


        if m.colliderect(b) or m.colliderect(b2) or m.colliderect(b3):
                # VOIDS





                    gravity = False
                    m_y_beschl = 0
                    m.bottom = b.top
                    m.bottom = b2.top
                    m.bottom = b3.top





        else:
            gravity = True
    #VOIDS:
    if m.colliderect(void1) and m.left >= void1.left and m.right <= void1.right:
        Zielbedingung = 1
        animate(m, pos=(m.x, HEIGHT + 50), duration=0.075, tween="accelerate")

    if m.colliderect(void2) and m.left >= void2.left and m.right <= void2.right:
        Zielbedingung = 1
        animate(m, pos=(m.x, HEIGHT + 50), duration=0.075, tween="accelerate")




    for element in HitboxListe:
        #if m.bottom >= element.top and m.colliderect(element) and m_y_beschl > 0 :
            #gravity = False
            #m_y_beschl = 0
            #m.bottom = element.top

        if m.colliderect(element) and m.right >= element.left:
            print("hehe")
            for element in BewegendeListe:
                element.x = element.x + 10


        if m.colliderect(element) and m.left <= element.right:
            print("HIHI")
            #for element in BewegendeListe:
                #element.x = element.x - 10






    #IF ZILEBEDINUNG
    if Zielbedingung == 0:



            if keyboard[keys.RIGHT]:
                if h.right <= 0:

                    h.left = WIDTH + Zufall
                    Zufall = random.randint(0,WIDTH)

                if sh.right <= 0:

                    sh.left = WIDTH + Zufall
                    Zufall = random.randint(0,WIDTH)

            if keyboard[keys.LEFT]:
                if h.left >= WIDTH:

                    h.right = Zufall - WIDTH
                    Zufall = random.randint(0,WIDTH)


                if sh.left >= WIDTH:
                    sh.right = Zufall - WIDTH
                    Zufall = random.randint(0, WIDTH)


            #Wiederansetzen der Büsche
            if keyboard[keys.RIGHT]:
                Buschentscheider = random.randint(1, 3)
                if bush.right <= 0 and bush2.right <= 0 and bush3.right <= 0:

                    if Buschentscheider == 1:

                        bush.left = WIDTH + Zufall
                        Zufall = random.randint(0, WIDTH)
                    if Buschentscheider == 2:

                        bush2.bottom = b.top
                        bush2.left = WIDTH + Zufall
                        Zufall = random.randint(0, WIDTH)
                    if Buschentscheider == 3:

                        bush3.bottom = b.top
                        bush3.left = WIDTH + Zufall
                        Zufall = random.randint(0, WIDTH)











            if keyboard[keys.LEFT]:
                Buschentscheider = random.randint(1, 3)
                if bush.left >= WIDTH and bush2.left >= WIDTH and bush3.left >= WIDTH:
                    if Buschentscheider == 1:
                        bush.right = Zufall - WIDTH
                        Zufall = random.randint(0,WIDTH)
                    if Buschentscheider == 2:
                        bush2.bottom = b.top
                        bush2.right = Zufall - WIDTH
                        Zufall = random.randint(0, WIDTH)
                    if Buschentscheider == 3:
                        bush3.bottom = bush3.top
                        bush3.right = Zufall - WIDTH
                        Zufall = random.randint(0, WIDTH)

            if sh.colliderect(void1) or sh.colliderect(void2):
                sh.left += 300


            if h.colliderect(void1) or h.colliderect(void2):
                h.left += 300

            if bush.colliderect(void1) or bush.colliderect(void2):
                bush.left += 300

            if bush2.colliderect(void1) or bush2.colliderect(void2):
                bush2.left += 300

            if bush3.colliderect(void1) or bush3.colliderect(void2):
                bush3.left += 300









      #ZIELBEDINGUNG
    if Zielbedingung == 0:



        #Wolkenansetzen
        if keyboard[keys.RIGHT]:

            if cloud.right <= 0:
                cloud.x = WIDTH + Zufall
                Zufall = random.randint(0, WIDTH)
                cloud.top = Cloudhöheneiner

                Cloudhöheneiner = random.randint(0, 50)
            if cloud2.right <= 0:
                cloud2.x  = WIDTH + Zufall
                Zufall = random.randint(0, WIDTH)
                cloud2.y = cloud2.y + Cloudhöhen
                Cloudhöhen = random.randint(-29, 29)

            if cloud3.right <= 0:
                cloud3.x  = WIDTH + Zufall
                Zufall = random.randint(0, WIDTH)
                cloud3.y = cloud3.y + Cloudhöhen
                Cloudhöhen = random.randint(-29, 29)

        if keyboard[keys.LEFT]:

            if cloud.left >= WIDTH:
                cloud.x = Zufall - WIDTH
                Zufall = random.randint(0, WIDTH)
                cloud.top = Cloudhöheneiner

                Cloudhöheneiner = random.randint(0, 50)
            if cloud2.left >= WIDTH:
                cloud2.x = Zufall - WIDTH
                Zufall = random.randint(0, WIDTH)
                cloud2.y = cloud2.y + Cloudhöhen
                Cloudhöhen = random.randint(-29, 29)

            if cloud3.left >= WIDTH:
                cloud3.x = Zufall - WIDTH
                Zufall = random.randint(0, WIDTH)
                cloud3.y = cloud3.y + Cloudhöhen
                Cloudhöhen = random.randint(-29, 29)







    #Hitbox void = Hitbox am anfang nicht links
    if m.colliderect(void):
        m.left = void.right

    #ZILEBEDINUNG
    if Zielbedingung == 0:

        #Grenzen = Oben, Links, Unten nie aus Bild und level sterbe m
        if m.top <= 0:
            m.top = 0
            #STERBEN NOCH IMPLEMENTIEREN, ABER VORERST NUR GRENZE
        if m.bottom >= HEIGHT:
            m.bottom = HEIGHT
        if m.left <= 0:
            m.left = 0
        if m.right >= WIDTH:
            m.right = WIDTH






pgzrun.go()
```