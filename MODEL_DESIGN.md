# Model Design

Except for the Game class, every class should be abstract, and to create a board game, subclasses should be implemented

## Game

Responsibility :
Represents the game as a haul with it's rules it's board it's state etc

Data :
- Board
- Ruleset
- PlayerToPlay variable 
- Move history array

## Board

Responsibility :
Represents the logical game board.

Data :
- 2D array of the pieces (board)

Methods :
- Method to move a piece.

## Ruleset

Respondibility :
Represent the specific set of rules that the game must follow.

Data :
- Number of players
- Array of special rules
- Gamestate injected from the GameClass that it can modify

Methods :
- Method to enforce rules present in the rule array

## Piece

Responsibility :
Represents a piece

Data : 
- 2D array of the movement set
- Position
- Material value

## Position

Responsibility :
Represents a position on the board

Data :
- x
- y

## Move

Responsibility :
Represents a move that has been performed or is being performed

Data :
- initial position
- new position
- piece moved
- bool capture
- piece captured