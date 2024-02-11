import pygame
from pygame.locals import *

# Initialize pygame and the screen
pygame.init()
screen = pygame.display.set_mode((600, 600))
pygame.display.set_caption('Snake')

# Define the colors for the game
black = (0, 0, 0)
gray = (128, 128, 128)
green = (255, 255, 0)
red = (255, 0, 0)

# Define the snake, food, and walls
snake_head = pygame.Rect(300, 300, 10, 10)
food_x = 300
food_y = random.randint(100, 600)
walls = pygame.Rect(0, 0, 700, 600)

# Define the movement keys and speed
up = False
down = False
left = False
right = False
speed = 3

# Define the game loop
running = True
while running:
    # Handle events
    for event in pygame.event.get():
        if event.type == QUIT:
            running = False
        elif event.type == KEYDOWN:
            if event.key == K_UP:
                up = True
            elif event.key == K_DOWN:
                down = True
            elif event.key == K_LEFT:
                left = True
            elif event.key == K_RIGHT:
                right = True
    # Handle the snakes movement
    if up:
        snake_head.y -= speed
    if down:
        snake_head.y += speed
    if left:
        snake_head.x -= speed
    if right:
        snake_head.x += speed
    if snake_head.left < 0:
        snake_head.left = 0
    if snake_head.right > 600:
        snake_head.right = 600
    if snake_head.
