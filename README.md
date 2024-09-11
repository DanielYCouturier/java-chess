# Chess (Java)
[Download Jar](https://github.com/DanielCouturier/java-chess/blob/main/Chess.jar)

The purpose of this project was to create some large project to demonstrate principles of software engineering. Our group decided to implement chess, since it has very clear requirements we all understood, a moderate complexity and scope, and would would be fun and challenging. 

Chess is a two-player strategy board game dating back to the 6th century, where players take turns moving various pieces around an 8x8 board. Each type of piece has its own rules about how it can move and "capture" opponents pieces. The game ends when a player captures the opponents King piece, and declares "Checkmate". This can be difficult, since players have to declare a "Check" when their next move would capture the opponent's king, creating an opportunity for the opponent to evade defeat. 

![image](https://github.com/user-attachments/assets/365c8101-3a0d-4114-90b1-cf73d2097f41)

The game requirements for the software was to implement the standard ruleset of chess:
* Players take turns.
* Each piece has trivial constraints for how it moves, and additional constraints depending on board state.
* A piece cannot be moved if it puts the player in check.
* The game ends when players reach checkmate or stalemate.
* ETC

We also outlined several non-game requirments regarding user responsivness, accessiblity, and clarity:
* The user should not be able to make illegal moves.
* The user should be able to see the selected piece and its legal moves.
* The user should be able to see the previous piece the opponent made.
* ETC

# Basic Design
Over the course of the semester, we developed the software using a Model-View-Controller (MVC) design pattern. In this architecture, the Model encapsulated the chess rules, such as the restricted movement of each piece (e.g., bishops moving diagonally, pawns advancing forward, and kings castling). The View was responsible for rendering everything on the screen, including the board, chess pieces, highlights, and animations. Finally, the Controller managed the user's interactions with the game, tracking whose turn it was, whether a piece was selected, and facilitating communication between the Model and View to ensure user inputs were properly reflected in both. Each of these components requires several different classes, so the first half of the semester was spent diagramming the relationship between each class within each component, and mapping the communication between components. 

Model
* ChessBoard.java - stores position of chess pieces, determines if the board (itself) is in check, checkmate, stalemate, or would be if a hypothetical move was made. 
* ChessPiece.java - abstract class; each implementing chess piece has its own file which calculates piece movement rules.  

View 
* GamePanel.java - handles all UI calls to draw sprites, highlight, or get recent inputs.
* GameFrame.java, MouseHandler.java - Override Swing classes.

Controller
* LogicController.java - implements all player control logic, all relavent calls to update the UI, and all calls to the Model to update the state of the game.
* Game.java, EntryPoint.java  - code for main game loop and replay loop respectively.

For the implementation, my primary responsibility was developing the View, but after completing it early, I also contributed significantly to the Controller. 

This project was originally submitted as a final project for CSE 2410 (Into to Software Engineering) (2023)

Targeted for Java 17

[Original Final Report](https://docs.google.com/document/d/1g7eUl1c2WTUHv4xkL3X7aRBG7_2IugKUwbCIGI7oRf4/edit)
