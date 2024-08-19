# Python-game
It is a game code
  #Create a game of rock, paper, scissor

import sys
import random
from enum import Enum

class RPS(Enum):  #create a class function
    ROCK = 1
    PAPER = 2
    SCISSOR = 3

  #Create a game,player,python count

def rps(Name='player one'):
    game_count = 0
    python_win = 0
    player_win = 0

    #changed  Local function

    def play_rps():
        nonlocal Name
        nonlocal python_win
        nonlocal player_win
        nonlocal game_count

        print("\n1 for Rock")
        print("2 for Paper")
        print("3 for Scissor")
        print("")

  #Create a player input

        playerchoice = input(f"\n{Name}, choose (1/2/3): ")

        if playerchoice not in ["1", "2", "3"]:
            print(f"\n{Name}, please enter 1, 2, or 3")
            return play_rps()

        player = int(playerchoice)

    #create of automati of system input

        computerchoice = random.choice("123")
        computer = int(computerchoice)

#Convert to player and computer str function

        print(f"\n{Name}, you chose {str(RPS(player)).replace('RPS.', '').title()}.")
        print(f"Computer chose {str(RPS(computer)).replace('RPS.', '').title()}.")

#create a def function and return put game....count

        def decide_winner(player, computer):
            nonlocal Name
            nonlocal player_win
            nonlocal python_win
            if player == 1 and computer == 3:
                player_win += 1
                return f"{Name} 💥 You win!"
            elif player == 2 and computer == 1:
                player_win += 1
                return f"{Name} 💥 You win!"
            elif player == 3 and computer == 2:
                player_win += 1
                return f"{Name} 💥 You win!"
            elif player == computer:
                return "💥 Match tie"
            else:
                python_win += 1
                return "💥 Python wins!"

#Create a game result

        result = decide_winner(player, computer)
        print(result)

#increased to game count

        game_count += 1
        print(f"Game count: {game_count}")
        print(f"\n{Name}'s wins: {player_win}")
        print(f"Python's wins: {python_win}")

#create player input of if and else function

        print("")

        playagain = input("\nPlay again? (Y for Yes / Q to Quit): ")
        if playagain.lower() == "y":
            return play_rps()
        else:
            print("\n🥇🏆🥇")
            print("Thank you for playing! \n")
            sys.exit("Bye! 👋")

    play_rps()

#create main file tag

if __name__ == "__main__":
    player_name = input("Enter your name: ")
    rps(player_name)
