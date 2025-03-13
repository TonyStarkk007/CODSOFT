# CODSOFT
# Simple Python Chatbot Implementation Using If-Else:
def chatbot_response(user_input):
    user_input = user_input.lower()
   
   if "hello" in user_input or "hi" in user_input or "hey" in user_input:
        return "Hello! How can I assist you today?"
    
   elif "how are you" in user_input:
        return "I'm just a chatbot, but I'm doing well! How can I help you?"

   elif "weather" in user_input or "forecast" in user_input:
        return "I don't have access to real-time weather data, but you can check your local weather app!"

   elif "goodbye" in user_input or "bye" in user_input or "see you" in user_input:
        return "Goodbye! It was nice chatting with you. Have a great day!"

   elif "your name" in user_input or "who are you" in user_input:
        return "I am a simple chatbot created to assist you with basic queries."

   else:
        return "I'm sorry, I didn't understand that. Could you rephrase your question?"

def chat():
    print("Chatbot: Hello! I'm a simple chatbot. Type 'exit' to end the conversation.")

   while True:
        user_input = input("You: ")
        if user_input.lower() == "exit":
            print("Chatbot: Goodbye! It was nice talking to you.")
            break
        response = chatbot_response(user_input)
        print(f"Chatbot: {response}")

chat()


![IMG-20250313-WA0006](https://github.com/user-attachments/assets/3712014a-d637-4dd2-9269-215a48728be9)
![IMG-20250313-WA0007](https://github.com/user-attachments/assets/42ec4e71-a262-4c9a-8eb3-17244e99e763)



# ..................................
# Tic Tac Toe AI vs Human Codesoft task 2
import random
def print_board(board):
    for row in board:
        print("|".join(row))
        print("-" * 5)

def check_winner(board):
    for row in board:
        if row[0] == row[1] == row[2] != ' ':
            return row[0]
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] != ' ':
            return board[0][col]
    
   if board[0][0] == board[1][1] == board[2][2] != ' ':
        return board[0][0]
    
   if board[0][2] == board[1][1] == board[2][0] != ' ':
        return board[0][2]
    
   return None

def is_draw(board):
    for row in board:
        if ' ' in row:
            return False
    return True

def is_game_over(board):
    return check_winner(board) is not None or is_draw(board)
def minimax(board, depth, is_maximizing, alpha, beta):
    winner = check_winner(board)
    if winner == 'O':
        return 1  # AI win
    if winner == 'X':
        return -1  # Human win
    if is_draw(board):
        return 0  # Draw

   if is_maximizing:
        max_eval = float('-inf')
        for row in range(3):
            for col in range(3):
                if board[row][col] == ' ':
                    board[row][col] = 'O'  # AI's move
                    eval = minimax(board, depth + 1, False, alpha, beta)
                    board[row][col] = ' '  # Undo the move
                    max_eval = max(max_eval, eval)
                    alpha = max(alpha, eval)
                    if beta <= alpha:
                        break
        return max_eval
    else:
        min_eval = float('inf')
        for row in range(3):
            for col in range(3):
                if board[row][col] == ' ':
                    board[row][col] = 'X'  # Human's move
                    eval = minimax(board, depth + 1, True, alpha, beta)
                    board[row][col] = ' '  # Undo the move
                    min_eval = min(min_eval, eval)
                    beta = min(beta, eval)
                    if beta <= alpha:
                        break
        return min_eval

def best_move(board):
    best_val = float('-inf')
    move = None
    for row in range(3):
        for col in range(3):
            if board[row][col] == ' ':
                board[row][col] = 'O'  # AI's move
                move_val = minimax(board, 0, False, float('-inf'), float('inf'))
                board[row][col] = ' '  # Undo the move
                if move_val > best_val:
                    best_val = move_val
                    move = (row, col)
    return move

def play_game():
    board = [[' ' for _ in range(3)] for _ in range(3)]
    human = 'X'
    ai = 'O'
    current_player = human

   print("Welcome to Tic-Tac-Toe! You are 'X', AI is 'O'.")

   while not is_game_over(board):
        print_board(board)
        
   if current_player == human:
            # Human player's move
            row, col = map(int, input("Enter your move (row col): ").split())
            if board[row][col] == ' ':
                board[row][col] = human
                current_player = ai
            else:
                print("Invalid move, try again.")
        else:
            # AI's move
            print("AI is making its move...")
            row, col = best_move(board)
            board[row][col] = ai
            current_player = human

   print_board(board)
    winner = check_winner(board)
    if winner == human:
        print("Congratulations! You win!")
    elif winner == ai:
        print("AI wins! Better luck next time.")
    else:
        print("It's a draw!")

play_game()

   ![IMG-20250313-WA0010](https://github.com/user-attachments/assets/12d9384b-a0f6-4860-a88d-abc9ebcac73d)
![IMG-20250313-WA0011](https://github.com/user-attachments/assets/13f40e8f-3b90-42e4-877d-6bfbd96e47ea)
![IMG-20250313-WA0012](https://github.com/user-attachments/assets/9fb3d95a-537b-4363-8840-57de3440a02d)
![IMG-20250313-WA0014](https://github.com/user-attachments/assets/414637f6-7b96-4337-bdbc-e9b9b880fb5b)
![IMG-20250313-WA0013](https://github.com/user-attachments/assets/17934a10-293b-4834-adf0-7900874d4878)
