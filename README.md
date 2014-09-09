#Clock.py
#========
#
#Modded clock to understanding codeing
#using python
#
##!/usr/bin/env python
#!/home/pi/Python/Project001
# -*- Pi Time -*-
#
#  myclock.py
#

import time,pygame
pygame.init()

theFont=pygame.font.Font(None,72)
clock = pygame.time.Clock() #Clock to limit speed

screen = pygame.display.set_mode([320, 200])
pygame.display.set_caption('The Time is...')

#adding backgroundimages
#
background_image = pygame.image.load("/home/pi/Python/Project001/day.png").convert()
screen.blit(background_image, [0,0])

#showing background behide clock aswell
#
#adding a sun & moon to spin around to so AM & PM
# if hours are from 6 to 21 sun
# else moon
#
#get local weather temp
#
while True:
	clock.tick(1)
	theTime=time.strftime("%H:%M:%S",time.localtime())
	timeText=theFont.render(str(theTime), True,(255,255,255),(0,0,0))
	screen.blit(timeText,(80,60))
	pygame.display.update()
