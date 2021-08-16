#TicTacToeGame
import random
#This will be used to find a random integer later
import sys
#sys will be used later to end the program
print ("Press 1 to play rock, 2 to play paper, and three to play scissors")
losing_counter = 0
winning_counter = 0
tie_counter = 0
#These counters are given a value so that they may have values added on later
play_again = input("Do you want to play (y/n)")
while play_again == "n":
#This while loop deals with the occurrence that the user picks to not play on the first try
    print("How about you select y next time?")
    sys.exit()
     #Essentially kills the program
while play_again == "y":
#While the user would still like to play, the game will still run
    choice = int(input("Rock(1),Paper(2), or Scissors(3)"))
    #When user chooses R,P or S, he is actually assigning a value to the variable "choice"
    computer_num = random.randint(1, 3)
    if computer_num == 1:
        print("computer has chosen rock")
    if computer_num == 2:
        print("computer has chosen paper")
    if computer_num == 3:
        print("computer has chosen scissors")
    # The computer's choice of rock paper or scissors is decided here as an integer
    if choice != computer_num:
        #Essentially if the game isn't a draw
        if (choice-computer_num) == 2:
            #Only one possible combination of values from 1-3 that = 2, 3(scissors) and 1(rock)
            print("You've lost!")
            #I think this is self-explanatory
            losing_counter = losing_counter + 1
            #adds a value of 1 to the losing_counter
            play_again = input("Do you want to play(y/n)")
#Asks whether the player wants to play again. If yes, while loop repeats. If no, then the win/loss ratio is printed.
        elif (choice-computer_num) == -2:
            print("You've won!")
            winning_counter = winning_counter + 1
            play_again = input("Do you want to play(y/n)")
        elif (choice-computer_num) == 1:
            print("You've won!")
            winning_counter = winning_counter + 1
            play_again = input("Do you want to play(y/n)")
        elif (choice-computer_num) != -2:
            if choice < computer_num:
                print ("You've lost!")
                losing_counter = losing_counter + 1 
                play_again = input("Do you want to play(y/n)")
        elif (choice-computer_num) != 2:
            if choice > computer_num:
                print ("You've won!")
                winning_counter = winning_counter + 1
                play_again =input("Do you want to play(y/n)")
    if choice == computer_num:
        print("tie game!")
        play_again = input("Do you want to play(y/n)")
        tie_counter = tie_counter + 1
print("")
print("You have won " + str(winning_counter) + " time(s), lost " + str(losing_counter) + " time(s) and tied " + str(tie_counter) + " time(s)")
#Counters must be converted to string or the program attempts to add the "" and the counter
print("")
print("Your win/loss ratio is " + str(winning_counter/(losing_counter)) + " wins per loss")
#Simple division is used to calculate the win/loss ratio(still converted to a string




        
