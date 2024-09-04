# rock-paper-scissor
# Description: A simple Rock, Paper, Scissors game
import random

Rock_accii = '''
   _______
---'   ____)
      (_____)
      (_____)
      (____)
---.__(___)
'''

Paper_accii = '''
    _______
---'    ____)____
           ______)
          _______)
         _______)
---.__________)
'''

scissor_accii = '''
   _______
---'   ____)____
          ______)
       __________)
      (____)
---.__(___)
'''

#start the game
print('Welcome to the Rock, Paper, Scisssors game!')
#ask the user : do you want to continue? or need help?
confirm = input('press enter to continue or type (Help) for the rules:').lower()

#rules of the game
if confirm == 'help':
    print('''
          ******* RULES *******  
          1) You choose and the computer chooses.  
          2) Rock smashes Scissors -> Rock wins.  
          3) Scissors cuts Paper -> Scissors wins.  
          4) Paper covers Rock -> Paper wins.''')
    

#ask the user to choose rock, paper or scissors
player_choice = input('Enter your choice (rock , paper , scissors ):').lower()

if player_choice not in ['rock', 'paper', 'scissors']:
    print('Invalid choice. Please run the app again and choose from rock , paper , scissors ')
#display the choices   
else:

    if player_choice == 'rock':
        print('\nyou chose: \n'+ Rock_accii)
    elif player_choice == 'paper':
        print('\nyou chose: \n'+ Paper_accii)    
    else:
        print('\nyou chose: \n'+ scissor_accii)    

#computer will choose randomly
computer_choice = random.choice(['rock', 'paper', 'scissors'])    

if computer_choice == 'rock':
    print('\ncomputer chose: \n'+ Rock_accii)
elif computer_choice == 'paper':
    print('\ncomputer chose: \n'+ Paper_accii)
else:
    print('\ncomputer chose: \n'+ scissor_accii)        

#compare the choices
if player_choice == computer_choice:
    print('It is a tie!')
elif(
    (player_choice == 'rock' and computer_choice == 'scissors') or 
    (player_choice == 'scissors' and computer_choice == 'paper') or
    (player_choice == 'paper' and computer_choice == 'rock')
):
    print(f'You win! your {player_choice} beats computer\'s {computer_choice}')
else:
    print(f'You lose! computer\'s {computer_choice} beats your {player_choice}')        
