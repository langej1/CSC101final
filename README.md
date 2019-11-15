import sys
import random

"""

To exit any game while in the middle of playing, press Ctrl + C

"""

print("Welcome to the Super, Mega, Awesome Simulation")

user_name = input("What is your name:")

print("Hello," , user_name)



user_age = int(input("Please verify your age. How old are you? \n")) #used to verify the users age
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

def text_adventures(): #this is the code for the text adventure game.
  """

  args:
  North_direction
  south_direction
  west_direction
  east_direction

  returns:
  - They all return which direction they chose, and offer different options
  north: Go in a cave or not?
  south:Explore/leave, stay in castle/leave
  west:party, swim, leave
  east: Get a job/leave

  """
  direction = input("Which direction would you like to go? East, West, North or South \n")  #where the user wants to go.
  #coding for north grid
  if direction == "North":
    print("You have decided to go to the Northern Slopes")
    north_move1 = input("You have encountered a cave. Would you like to enter? Yes or No? \n")
    if north_move1 == "Yes": #choose to enter cave
      print("You entered the cave and encountered a", monsters[1] , "and was stabbed.")
      print("You have died")
      exit()
    elif north_move1 == "No": #not enter cave. Leave North.
      print("The path to the West and East is blocked. Returning to the start point.")
      text_adventures()
#coding for South grid
  elif direction == "South": #go South
    print("You have decided to go to the Southern Shores")
    south_move1 = input("You have not encountered any monsters. Would you like to 1. Explore, or 2. leave the area \n")
    if south_move1 == "1.": #exploring south
      castle_choice = input("Congrats! You found a castle on the water with a princess! Would you like to stay? Yes or No? \n")
      if castle_choice == "Yes": #stay at castle
        print("Congrats. You have fulfilled your destiny.")
        exit()
      else: #leave castle
        print("The path to the West and East is overrun by monsters. Returning to the start point.")
    else: #leave south
      print("The path to the West and East is overrun by monsters. Returning to the start point.")
      text_adventures()
  #code for west grid
  elif direction == "West": #travel west
    print("You have decided to go to the Western Waters.")
    west_move1 = input("You have encountered a village. Would you like to 1. Relax, and drink, 2. Go swimming in the ocean, or 3. Leave? \n")
    if west_move1 == "1.": #drink
      print("You have become bankrupt, and drunk. Due to your lack of funds, you became angry and got arrested. Game over.")
      exit()
    elif west_move1 == "2.": #Choose to swim in ocean
      print("You saw a shark in the water.")
      west_move1_1 = input("What do you do? 1. Run, or 2. Try to make it a pet \n")
      if west_move1_1 == "1.": #run away
        print("Out of fear, you ran to your starting point")
        text_adventures()
      elif west_move1_1 == "2.": #domesticate shark
        print("You have been eaten by a shark. Game over.")
        exit()
    elif west_move1 == "3.": #leave west
      print("returning to start point.")
      text_adventures()
  #Eastern grid coding
  elif direction == "East":
    print("You have decided to go to the East Woods")
    east_move1 = ("You have been requested to work in a coal mine for $30 per hour for one year. Do you join? Yes or No? \n")
    if east_move1 == "Yes":
      east_move2 = input("You have successfully earned $60,000. Do you continue working? Yes or no? \n")
      if east_move2 == "Yes":
        print("You died in a mining accident. Game over.")
        exit()
      elif east_move2 == "No":
        print("Returning to start point")
        text_adventures()
    elif east_move1 == "No":
      print("Returning to start point.")
      text_adventures()




def ball_8():
  """
  args:
  user_inputs: possible questions for the simulation to answer
  ball_response: possible response from the magic 8 ball.

  returns:
  
  """
  user_inputs = ["Will I win the lottery? \n", "Will I pass this class? \n" , "Will I die young? \n" , "Will I die alone \n" , "Should I have dropped this class? \n" , "Will I fail this project? \n" , "Is getting hit by a car worth the free tuition? \n"]
  ball_response =["Perhaps" , "No", "Yes", "Uncertain", "No one cares", "Without a doubt", "Most likely", "Probably not", "Don't count on it"]



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


