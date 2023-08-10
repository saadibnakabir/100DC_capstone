  ############### Blackjack Project #####################


#Hint 1: Go to this website and try out the Blackjack game: 
#   https://games.washingtonpost.com/games/blackjack/
#Then try out the completed Blackjack project here: 
#   http://blackjack-final.appbrewery.repl.run

#Hint 2: Read this breakdown of program requirements: 
#   http://listmoz.com/view/6h34DJpvJBFVRlZfJvxF
#Then try to create your own flowchart for the program.

#Hint 3: Download and read this flow chart I've created: 
#   https://drive.google.com/uc?export=download&id=1rDkiHCrhaf9eX7u7yjM1qwSuyEk-rPnt

#Hint 4: Create a deal_card() function that uses the List below to *return* a random card.
#11 is the Ace.
#cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10, 10]
import random
#from replit import clear
def deal_cards():
    cards =[11,2,3,4,5,6,7,8,9,10,10,10,10]
    card  = random.choice(cards)
    return card



#Hint 6: Create a function called calculate_score() that takes a List of cards as input 
#and returns the score. 
#Look up the sum() function to help you do this.
def calculate_score(cards):
  """Takes Cards and measures score"""
  if sum(cards) == 21 and len(cards) == 2:
    return 0 
  if 11 in cards and sum(cards) > 21:
    cards.remove(11)
    cards.append(1)
  
  return sum(cards)
   
#Hint 5: Deal the user and computer 2 cards each using deal_card() and append().
def play_game():
  is_game_over = False
  user_cards = []
  computer_cards = []
  for _ in range(2):
    user_cards.append(deal_cards())
    computer_cards.append(deal_cards())
  
  def compare(user_score,computer_score):
    if user_score == computer_score:
      return "DRAW"
    elif computer_score == 0:
      return "You Lose Computer has a BlackJack"
    elif user_score == 0:
      return "You Win with a BLackJack"
    elif user_score > 21:
      return "You Bust!! You Lose!!"
    elif computer_score > 21:
      return "Computer Bust !! You Win"
    elif computer_score == 21:
      return "Computer Wins"
    elif user_score == 21:
      return "YOU WIN"
    elif user_score > computer_score:
      return "You Win"
    elif computer_score > user_score:
      return "Computer Wins"
    
    
    
  while not is_game_over:
    user_score = calculate_score(user_cards)
    computer_score = calculate_score(computer_cards)
    print(f"Your Cards: {user_cards} and Curent Score: {user_score}")
    print(f"Computer's First Card: {computer_cards[0]}")
    
    if user_score == 0 or computer_score == 0 or computer_score > 21:
      is_game_over = True
    else:
      user_should_deal = input("Type 'y' if you want to draw another cards: ")
      if user_should_deal == 'y':
        user_cards.append(deal_cards())
      else:
        is_game_over = True
        
  while computer_score != 0 and computer_score < 17:
    computer_cards.append(deal_cards())
    computer_score = calculate_score(computer_cards)
  
  print(f"Your final hand: {user_cards} and final score was : {user_score}")
  print(f"Computer Final hand was: {computer_cards} and final score was: {computer_score}")
  print(compare(user_score,computer_score)) 
    
while input("DO you want to Play the game: ") == 'y':
  #clear()
  play_game()
