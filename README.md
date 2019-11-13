# CSCfinal
This is my code for my CSC101 final project.

I will be adding descriptions from here, and updating code.

import sys
import random

"""

To exit any game while in the middle of playing, press Ctrl + C

"""

print("Welcome to the Super, Mega, Awesome Simulation")

user_name = input("What is your name:")

print("Hello," , user_name)



user_age = int(input("Please verify your age. How old are you?"))
if user_age >= 25:
  print("Welcome to the simulation.")

while user_age < 25:
  print("You aren't old enough. Please leave the simulation.")
  exit()
  
print("\n")
#defines all the games/activities
def hangman():
  print("hangman")

def tictactoe():
  print("hi")

def text_adventures():
  
  direction = input("Which direction would you like to go? East, West, North or South \n")
  #coding for north grid
  if direction == "North":
    print("You have decided to go to the Northern Slopes")
    north_move1 = input("You have encountered a cave. Would you like to enter? Yes or No? \n")
    if north_move1 == "Yes": #choose to enter cave
      print("You entered the cave and encountered a", monsters[1] , "and was stabbed.")
      print("You have died")
      exit()
    elif north_move1 == "No":
      print("The path to the West and East is blocked. Returning to the start point.")
      text_adventures()
#coding for South grid
  if direction == "South":
    print("You have decided to go to the Southern Shores")
    south_move1 = input("You have not encountered any monsters. Would you like to 1. Explore, or 2. leave the area \n")
    if south_move1 == "1.":
      castle_choice = input("Congrats! You found a castle on the water with a princess! Would you like to stay? Yes or No?")
      if castle_choice == "Yes":
        print("Congrats. You have fulfilled your destiny.")
        exit()
      else:
        print("The path to the West and East is overrun by monsters. Returning to the start point.")
    else:
      print("The path to the West and East is overrun by monsters. Returning to the start point.")
      text_adventures()
  #code for west grid
  if direction == "West":
    print("You have decided to go to the Western Waters.")
    west_move1 = input("You have encountered a village. Would you like to 1. Relax, and drink, 2. Go swimming in the ocean, or 3. Leave? \n")
    if west_move1 == "1.":
      print("You have become bankrupt, and drunk. Due to your lack of funds, you became angry and got arrested. Game over.")
      exit()
    if west_move1 == "2.":
      west_move1. = input("You saw a shark in the water. What do you do? 1. Run, or 2. Try to make it a pet")
      if west_move. == "1.":
        print("Out of fear, you ran to your startin point")
        text_adventures()



def ball_8():
  user_inputs = ["Will I win the lottery? \n"]



def user_choice():
  print("To exit any game, press Ctrl + C")
  print("Which game would you like to play?")
  games = ['1. Hangman' , '2. Tic-Tac Toe' , '3. Text-Based Adventure', '4. Magic-8Ball']
  
  #prints out game options
  for game in games:
    print(game)
  
  print("\n")
  
  #gives the user a choice in the game
  game_choice = input("Which game would you like to play? 1., 2., 3., or 4.? \n")
  # calls up the game choice the user chooses
  if game_choice == "1.":
    hangman()
  
  elif game_choice == "2.":
    tictactoe()
  
  elif game_choice == "3.":
    text_adventures()
  
  elif game_choice == "4.":
    ball_8()

user_choice()


