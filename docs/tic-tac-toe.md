*link to tic-tac-toe repo*

---

```python
import time
import sys

# BOARD ================================================

positions = [1, 2, 3, 4, 5, 6, 7, 8, 9]

def print_board():
  print("")
  print("""    {one}  |  {two}  |  {three}
  _____|_____|_____
    {four}  |  {five}  |  {six}    
  _____|_____|_____
    {seven}  |  {eight}  |  {nine}   
       |     |    """.format(one = positions[0], two = positions[1], three = positions[2], four = positions[3], five = positions[4], six = positions[5], seven = positions[6], eight = positions[7], nine = positions[8]))
  print("")

def board_update(placement, symbol):
  positions[placement - 1] = symbol

# TURNS ================================================

def define_symbols():
  player_sym = input("Would you like to be X's or O's? \n")
  while player_sym != 'X' and player_sym != 'O':
    player_sym = input("Please select either an 'X' or an 'O'. Would you like to be X's or O's? \n")
  if player_sym == 'X':
    comp_sym = 'O'
  else:
    comp_sym = 'X'
  return player_sym, comp_sym

def player_move(player_sym):
  print_board()
  placement = input("Where would you like to place an {sym}? \n".format(sym = player_sym))
  while type(placement) != int:
        try:
          placement = int(placement)
        except:
          placement = input("Please select a number. Where would you like to place an {sym}? \n".format(sym = player_sym))
  while placement not in positions:
    placement = input("Please select a single, empty square. Where would you like to place an {sym}? \n".format(sym = player_sym))
    while type(placement) != int:
        try:
          placement = int(placement)
        except:
          placement = input("Please select a number. Where would you like to place an {sym}? \n".format(sym = player_sym))
  return placement

def player_turn():
  board_update(player_move(player_sym), player_sym)
  print_board()
  detect_win()

def comp_move():
  for position in positions:
    if position != 'X' and position != 'O':
      return position

def comp_turn():
  move = comp_move()
  print("")
  print("The computer is thinking...")
  time.sleep(0)
  print("The computer has decided to place an {symbol} in position {position}.".format(symbol = comp_sym, position = move))
  board_update(move, comp_sym)
  detect_win()

def detect_win():
  winner = 'winner_error'
  winner_symbol = 'symbol_error'
  if positions[0] == positions[1] and positions[1] == positions[2]:
    if positions[0] == player_sym:
      winner = 'The player'
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  elif positions[3] == positions[4] and positions[4] == positions[5]:
    if positions[3] == player_sym:
      winner = "The player"
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  elif positions[6] == positions[7] and positions[7] == positions[8]:
    if positions[6] == player_sym:
      winner = "The player"
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  elif positions[0] == positions[3] and positions[3] == positions[6]:
    if positions[0] == player_sym:
      winner = "The player"
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  elif positions[1] == positions[4] and positions[4] == positions[7]:
    if positions[1] == player_sym:
      winner = "The player"
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  elif positions[2] == positions[5] and positions[5] == positions[8]:
    if positions[2] == player_sym:
      winner = "The player"
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  elif positions[0] == positions[4] and positions[4] == positions[8]:
    if positions[0] == player_sym:
      winner = "The player"
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  elif positions[2] == positions[4] and positions[4] == positions[6]:
    if positions[2] == player_sym:
      winner = "The player"
      winner_symbol = player_sym
    else:
      winner = 'The computer'
      winner_symbol = comp_sym
      print("")
      print_board()
      print("")
  else:
    return None
  print("{winner} has 3 {symbol}'s in a row! {winner} has won the game!".format(winner = winner, symbol = winner_symbol))
  print("")
  sys.exit()

# GAME =================================================

print("")

player_sym, comp_sym = define_symbols()

player_turn()
comp_turn()
player_turn()
comp_turn()
player_turn()
comp_turn()
player_turn()
comp_turn()
```
