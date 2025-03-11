# Tic-Tac-Toe_202401100300244
TIC TAC TOE SOLVER:-
Imports and Initialization
•	import random: The random module is used to make the AI move randomly among available cells. This ensures unpredictability in the AI's gameplay.
1. Printing the Board
•	print_board(board): This function visually represents the game board in the terminal.
o	It loops through each row of the board, joins cell values with " | " to create columns, and displays horizontal dividers ("-" * 9) after each row.
o	Example Output:
o	X | O | X
o	---------
o	O | X | O
o	---------
o	X |   | O
2. Checking for a Winner
•	check_winner(board, player): This function determines if a player has won the game.
o	Rows Check: Uses all() to verify if all cells in a row match the player's symbol.
o	Columns Check: Iterates through each column index and checks if all values in that column match the player's symbol.
o	Diagonal Checks:
	The first diagonal (top-left to bottom-right) is checked using board[i][i].
	The second diagonal (top-right to bottom-left) is checked using board[i][2 - i].
o	If any of these conditions are true, the player has won, and the function returns True.
3. Checking if the Board is Full
•	is_full(board): This function determines if the game ends in a tie by verifying whether all cells are filled.
o	It uses a nested comprehension to check every cell in the board and returns True if no cell contains a blank space (" ").
o	This ensures the game stops if there is no winner and the board is fully occupied.
4. AI Move
•	ai_move(board): Implements simple AI logic to decide the AI’s move.
o	It first identifies all empty cells by iterating through the board and collecting the indices of unoccupied cells into a list empty_cells.
o	It then randomly selects one of these cells using random.choice(empty_cells) and returns its coordinates (row, col).
5. Main Game Loop
•	tic_tac_toe(): This is the core function that manages the flow of the game.
o	Board Setup:
	A 3x3 game board is initialized as a list of lists with empty spaces (" ").
	Two players (User and AI) and their respective symbols ("X" for User and "O" for AI) are defined.
	The game starts with the User as the current_player.
o	Game Loop:
	The game continues indefinitely (while True) until a win or a tie condition is met.
	User Turn:
	Prompts the user to input a row and column.
	Validates the input to ensure it falls within bounds (0-2) and the chosen cell is not already taken. If invalid, it prompts again.
	AI Turn:
	The AI picks a random empty cell using ai_move and updates the board.
	Updating the Board:
	The chosen cell is filled with the current_player's symbol (X for the User or O for the AI).
	The updated board is printed after every move.
	Checking Win/Tie:
	After each move, the check_winner function is called to see if the current player has won. If so, the winner is announced, and the loop breaks.
	If the board is full and no one has won, it's a tie, and the loop breaks.
	Switching Turns:
	Alternates the current_player between User and AI.
Key Features
1.	Interactive Gameplay: Users can interactively input their moves, and the game provides feedback such as "Cell already taken" or "Invalid input" when needed.
2.	Basic AI: The AI makes random moves, which provides an easy challenge for the User. This could be expanded to a more sophisticated decision-making process.
3.	Win/Tie Conditions: Comprehensive checks ensure the game ends appropriately if a player wins or if the board is full (resulting in a tie).
4.	User-Friendly Interface: The game is displayed in a clear and readable format, making it easy for users to follow the board's state.
Possible Improvements
1.	Smarter AI: Instead of random moves, AI could use strategies like blocking the User’s winning moves or using the minimax algorithm for unbeatable gameplay.
2.	Input Validation: Could improve error messages or handle edge cases more gracefully.
3.	Replay Option: After a game ends, ask if the User wants to play another round.
4.	Custom Board Size: Allow users to play on boards larger than 3x3.
5.	Graphical Interface: Use a library like Tkinter or Pygame to create a GUI version of the game.

