import random

"""

To exit any game while in the middle of playing, press Ctrl + C

"""

print("Welcome to the Time Killing Module")

user_name = input("What is your name:")

print("Hello," , user_name)



user_age = int(input("Please verify your age. How old are you? \n")) #used to verify the users age
if user_age >= 20:
  print("Welcome to the simulation.")

while user_age < 20:
  print("You aren't old enough. Goodbye")
  exit()
  
print("\n")
#defines all the games/activities


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
  direction = input("Which direction would you like to go? East, West, North or South \n").lower()  #where the user wants to go.
  #coding for north grid
  if direction == "north":
    print("You have decided to go to the Northern Slopes")
    north_move1 = input("You have encountered a cave. Would you like to enter? Yes or No? \n").lower()
    if north_move1 == "yes": #choose to enter cave
      print("You entered the cave and encountered a goblin and was stabbed.")
      print("You have died")
      exit()
    elif north_move1 == "no": #not enter cave. Leave North.
      print("The path to the West and East is blocked. Returning to the start point.")
      text_adventures()
#coding for South grid
  elif direction == "south": #go South
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
  elif direction == "west": #travel west
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
  elif direction == "east":
    print("You have decided to go to the East Woods")
    east_move1 = input("You have been requested to work in a coal mine for $30 per hour for one year. Do you join? Yes or No? \n").lower()
    if east_move1 == "yes":
      east_move2 = input("You have successfully earned $60,000. Do you continue working? Yes or no? \n").lower()
      if east_move2 == "yes":
        print("You died in a mining accident. Game over.")
        exit()
      elif east_move2 == "no":
        print("Returning to start point")
        text_adventures()
    elif east_move1 == "no":
      print("Returning to start point.")
      text_adventures()




def ball_8():
  """
  args:
  ball_response: possible response from the magic 8 ball.
  user_question: What the user asks
  redo_question: Gives user option to ask another question

  returns:
  returns a random response much like a magic 8-ball
  
  """
  #list of responses the computer can give
  ball_response =["Perhaps" , "No", "Yes", "Uncertain", "No one cares", "Without a doubt", "Most likely", "Probably not", "Don't count on it"] 
  #promps user to ask a question
  user_question = input("What questions do you have? \n")
  #response from computer
  print(ball_response[random.randint(0, len(ball_response)-1)])
  #option to ask another question
  redo_question = input("Do you have another question? Yes or No? \n")
  if redo_question == "Yes":
    ball_8()
  else:
    exit()

def bad_counseling():
  """
  components:
  1. questions_dictionary: list of possible trigger words for certain problems and their different options for a response
  2. default_response: Response for anything not includes in the dictionary.
  3. random_response: generates a random response response from the dictionary
  4. user_text: What the user says
  5. Response: Randomly generated response from the dictionary
  6.next_response:Gives option for another question

  """
  print("What is your issue?")
  questions_dictionary = {
    "dead" : ["That sucks" , "Just move on." , "Don't be a baby" , "Sounds like a personal problem."],

    "divorce" : ["Oh well" , "There's other fish in the sea." , "Don't be a wuss" , "You're gonna die alone anyways."],
    "left" : ["Oh well" , "There's other fish in the sea." , "Don't be a wuss" , "You're gonna die alone anyways."],

    "depressed" : ["Just be happy" , "You and every teen out there." , "Yeah, no one cares." , "Not worth my time, next"],
    "depression":["Just be happy" , "You and every teen out there." , "Yeah, no one cares." , "Not worth my time, next"],

    "friends" : ["Who needs anyone anyways" , "Ha LONER" , "Loser!" , "LOL"],

    "life" : ["No one cares." , "Tragic" , "Oof"],

    "bully" : ["Just beat them up" , "So has everyone." , "Grow up." ],
    "bullied" : ["Just beat them up" , "So has everyone." , "Grow up." ],
    "bullying" : ["Just beat them up" , "So has everyone." , "Grow up." ],

    "food" : ["Just don't eat so much" , "Go on a diet" , "Fatty" , "Dang you ARE fat."],
    "eat" : ["Just don't eat so much" , "Go on a diet" , "Fatty" , "Dang you ARE fat."],
    "food" : ["Just don't eat so much" , "Go on a diet" , "eating" , "Dang you ARE fat."],

    "addicted": ["Just stop doing drugs" , "Well, the cops are on their way..." , "Don't overdose I guess."],
    "addiction" : ["Just stop doing drugs" , "Well, the cops are on their way..." , "Don't overdose I guess."],

    "broke" : ["Broke ass." , "Get a job." , "Bum.", "Guess you're going to be homeless."],
    "debt" : ["Broke ass." , "Get a job." , "Bum." , "Guess you're going to be homeless."],
    "Homeless" : ["Broke ass." , "Get a job." , "Bum." , "Guess you're going to be homeless."],

    "sick" : ["Get some meds" , "Pull the plug" , "Buy the coffin now"]
  }
  #in case they ask a question I didn't think of.
  default_response = ["I'm not sure I can help you with that."]
  #gives a random response from the list of responses
  def random_response(words):
    responses = []
    for word in words:
      if word in questions_dictionary:
        responses += questions_dictionary[word]

    if len(responses) == 0:
      responses = default_response
    
    return random.choice(responses)

  user_text = ""
  user_text = input("You: ").strip().lower()
  split_words = user_text.split(' ')
  response = random_response(split_words)
  print("Counselor: " , response)
  #gives the user the option to ask another question
  next_response = input("Do you have another issue, Y/N?\n").upper()
  if next_response == "Y":
    bad_counseling()
    print("Counselor: " , response)
  if next_response =="N":
    exit()


def hangman():
  """
  I took the hangman 'graphic' from a code I found on codereview.stackexchange.com

  args:
  words - list of words to be used for the game. Returns word
  max_guesses- determines max guesses based on word length
  word_since_guess: How many spaces there are for the word, after last guess
  guess: user guice for a letter


  """
  HANGMAN = (
"""
 ------
 |    |
 |
 |
 |
 |
 |
 |
 |
----------
""",
"""
 ------
 |    |
 |    O
 |
 |
 |
 |
 |
 |
----------
""",
"""
 ------
 |    |
 |    O
 |   -+-
 | 
 |   
 |   
 |   
 |   
----------
""",
"""
 ------
 |    |
 |    O
 |  /-+-
 |   
 |   
 |   
 |   
 |   
----------
""",
"""
 ------
 |    |
 |    O
 |  /-+-/
 |   
 |   
 |   
 |   
 |   
----------
""",
"""
 ------
 |    |
 |    O
 |  /-+-/
 |    |
 |   
 |   
 |   
 |   
----------
""",
"""
 ------
 |    |
 |    O
 |  /-+-/
 |    |
 |    |
 |   | 
 |   | 
 |   
----------
""",
"""
 ------
 |    |
 |    O
 |  /-+-/
 |    |
 |    |
 |   | |
 |   | |
 |  
----------
""")

  words = ("apple", "computer", "program", "grade" , "fail" , "help" , "words" , "calculator" , "hang" , "man" , "games" , "awesome" )
  #randomly chooses word from list
  word = random.choice(words)
  #total number iof guesses allowed
  max_guesses = len(word) - 1
  #how many spaces based on length of word
  word_since_guess = ("-") * len(word)
  #letters used
  used = []
  wrong = 0

  print("\t \t Welcome to Hangman! \n")


  while wrong < max_guesses and word_since_guess != word:
      print()
      print(HANGMAN[wrong])
      print("Word so far: ", word_since_guess)
      print("Letters used: ", used)

      guess = input("Guess a letter: ").lower()
      print()

      while guess in used:
          print("Try again... You've already used this letter")
          guess = input("Guess a letter: ").upper()
          print()
      used.append(guess)
      
      if guess in word:

          new = ""
          for i in range(len(word)):
              if guess == word[i]:
                  new += guess

              else:
                  new += word_since_guess[i]
          word_since_guess = new 

      else:
          print("INCORRECT! Try again!")
          wrong += 1



  if wrong == max_guesses:
    print("UNLUCKY! Better luck next time!")
    exit()

  else:
    print("WINNER! Congratulations!")
    exit()


#gives user the choice of what game to play
def user_choice():
  print("To exit any game, press Ctrl + C")
  print("What activity would you like to do?")
  games = [ '1. Text-Based Adventure', '2. Magic-8Ball' , "3. Counselor", "4. Hangman"]
    
  #prints out game options
  for game in games:
    print(game)
    
  print("\n")



  
  #gives the user a choice in the game
  game_choice = input("Which game would you like to play? 1., 2., 3. or 4.? \n")
  # calls up the game choice the user chooses
  
  #launches text adventure game
  if game_choice == "1." or game_choice == "1":
    text_adventures()

  #launches 8-ball predition game
  elif game_choice == "2." or game_choice == "2":
    ball_8()

  #launches the counseling helper
  elif game_choice == "3." or game_choice == "3":
    bad_counseling()

#launches the hangman game
  elif game_choice == "4." or game_choice == "4":
      hangman()
    
  
user_choice()


"""
Works Cited:
Hangman: https://codereview.stackexchange.com/questions/95997/simple-game-of-hangman
"""
