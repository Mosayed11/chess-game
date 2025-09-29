# chess-game

import chess

board = chess.Board()

while not board.is_game_over():
    print(board)  
    print("Legal moves:", [move for move in board.legal_moves])

    move = input("Enter your move (e.g., e2e4 or Nf3): ")
    try:
        board.push_san(move)  
    except:
        try:
            board.push_uci(move)  
        except:
            print("Invalid move, please try again.")

print("\nGame Over!")
print("Result:", board.result())
