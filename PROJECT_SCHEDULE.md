# PROJECT SCHEDULE

This document defines the development roadmap for the project.

The project is divided into three major stages, each producing a usable MVP:

1. **Console Chess Game**
2. **Graphic Chess App**
3. **Survival Chess**

The main development principle throughout the project is to keep the core engine **generic, modular, and independent from any specific user interface**.

---

# STAGE 1 — CONSOLE CHESS GAME

## Goal

Create a fully functional console application in which two players can play a complete game of standard chess.

This stage will establish the core systems of the board game engine.

---

## 1. Project Foundation

- [ ] Create the project structure
- [ ] Define the separation between engine, game logic, and user interface
- [ ] Create the console application entry point
- [ ] Create the main application/game loop
- [ ] Define basic project conventions
- [ ] Set up Git repository structure
- [ ] Add basic project documentation

---

## 2. Generic Board System

- [ ] Create a generic board representation
- [ ] Create a position/coordinate system
- [ ] Support conversion between internal coordinates and chess notation
- [ ] Implement board boundaries
- [ ] Implement placement of pieces on the board
- [ ] Implement removal of pieces from the board
- [ ] Implement movement of pieces between positions
- [ ] Implement board occupancy checks
- [ ] Implement queries for retrieving pieces from positions
- [ ] Ensure the board system is not dependent on chess-specific rules

---

## 3. Generic Piece System

- [ ] Create a base piece representation
- [ ] Define piece ownership/team
- [ ] Define piece position
- [ ] Define generic movement data
- [ ] Define piece material/value information
- [ ] Support different movement behaviors
- [ ] Support reusable movement definitions
- [ ] Separate piece data from board logic
- [ ] Ensure new piece types can be added without modifying the board system

---

## 4. Movement System

- [ ] Define movement directions
- [ ] Define movement distance
- [ ] Implement single-tile movement
- [ ] Implement sliding movement
- [ ] Implement jumping movement
- [ ] Implement movement path validation
- [ ] Implement collision/blocking detection
- [ ] Implement destination validation
- [ ] Implement friendly-piece collision rules
- [ ] Implement enemy-piece capture rules
- [ ] Separate generic movement rules from chess-specific movement rules

---

## 5. Chess Piece Implementation

### Pawn

- [ ] Implement normal pawn movement
- [ ] Implement initial two-square movement
- [ ] Implement diagonal capture
- [ ] Implement promotion
- [ ] Implement en passant

### Rook

- [ ] Implement horizontal movement
- [ ] Implement vertical movement

### Bishop

- [ ] Implement diagonal movement

### Knight

- [ ] Implement knight movement
- [ ] Verify that knights can jump over pieces

### Queen

- [ ] Implement rook-like movement
- [ ] Implement bishop-like movement

### King

- [ ] Implement king movement
- [ ] Implement castling

---

## 6. Generic Turn System

- [ ] Create a turn manager
- [ ] Track the active player
- [ ] Switch between players
- [ ] Prevent inactive players from moving
- [ ] Track turn count
- [ ] Define hooks/events for the beginning of a turn
- [ ] Define hooks/events for the end of a turn
- [ ] Keep the turn system reusable for games with different turn structures

---

## 7. Chess Rules

- [ ] Create the standard chess starting position
- [ ] Detect attacked tiles
- [ ] Detect check
- [ ] Prevent moves that leave the king in check
- [ ] Detect checkmate
- [ ] Detect stalemate
- [ ] Implement castling restrictions
- [ ] Implement en passant restrictions
- [ ] Implement promotion rules
- [ ] Implement draw by insufficient material
- [ ] Implement threefold repetition
- [ ] Implement fifty-move rule
- [ ] Define game victory conditions
- [ ] Define game draw conditions

---

## 8. Move Execution System

- [ ] Create a representation for a move
- [ ] Validate a requested move
- [ ] Execute a valid move
- [ ] Reject an invalid move
- [ ] Handle captures
- [ ] Handle special moves
- [ ] Update game state after a move
- [ ] Store move history
- [ ] Support undoing a move internally
- [ ] Ensure simulations can be performed without permanently modifying the game state

---

## 9. Game State System

- [ ] Track all active pieces
- [ ] Track captured pieces
- [ ] Track current player
- [ ] Track move history
- [ ] Track special-rule state
- [ ] Track game status
- [ ] Track victory/draw state
- [ ] Define initialization of a new game
- [ ] Define game reset behavior

---

## 10. Console Interface

- [ ] Create the main menu
- [ ] Add "New Game" option
- [ ] Add "Options" option
- [ ] Add "Quit" option
- [ ] Display the chess board in the console
- [ ] Display piece symbols clearly
- [ ] Display board coordinates
- [ ] Display the active player
- [ ] Ask the player for a move
- [ ] Parse console move input
- [ ] Display invalid-input messages
- [ ] Display illegal-move messages
- [ ] Display captures
- [ ] Display check
- [ ] Display checkmate
- [ ] Display draws
- [ ] Allow the player to quit an active game
- [ ] Return to the main menu after a game

---

## 11. Console MVP Validation

- [ ] A complete chess game can be started
- [ ] Both players can move all six piece types
- [ ] Illegal moves are rejected
- [ ] Captures work correctly
- [ ] Check is detected correctly
- [ ] Checkmate is detected correctly
- [ ] Draw conditions work correctly
- [ ] Castling works correctly
- [ ] En passant works correctly
- [ ] Promotion works correctly
- [ ] A complete game can be played entirely through the console
- [ ] Core engine code does not depend on console-specific code

---

# MILESTONE — CONSOLE CHESS MVP

- [ ] **Stage 1 complete**

At this point, the project should contain a complete chess engine usable through a console application.

---

# STAGE 2 — GRAPHIC CHESS APP

## Goal

Create a graphical application capable of playing a complete chess game using the same core engine developed during Stage 1.

No chess rule should have to be rewritten specifically for the graphical application.

---

## 12. GUI Foundation

- [ ] Select the graphical framework
- [ ] Create the graphical application entry point
- [ ] Connect the GUI application to the existing engine
- [ ] Create the main application window
- [ ] Create a screen/state management system
- [ ] Ensure UI code remains separate from engine code

---

## 13. Main Menu

- [ ] Create main menu screen
- [ ] Add "New Game" button
- [ ] Add "Options" button
- [ ] Add "Quit" button
- [ ] Add navigation between menus

---

## 14. Game Creation Menu

- [ ] Create game setup screen
- [ ] Allow selection of player settings
- [ ] Allow selection of basic game options
- [ ] Add "Start Game" button
- [ ] Add "Back" button
- [ ] Initialize the engine using selected settings

---

## 15. Graphical Board

- [ ] Render the chess board
- [ ] Render board coordinates
- [ ] Render chess pieces
- [ ] Synchronize rendered pieces with engine state
- [ ] Support different board sizes if possible
- [ ] Support scalable board rendering

---

## 16. Mouse Interaction

- [ ] Detect board tile under mouse cursor
- [ ] Allow a piece to be selected
- [ ] Highlight selected piece
- [ ] Highlight legal moves
- [ ] Allow destination tile selection
- [ ] Send requested moves to the engine
- [ ] Display rejected moves correctly
- [ ] Update graphics after successful moves

---

## 17. Game Interface

- [ ] Display current player
- [ ] Display captured pieces
- [ ] Display move history
- [ ] Display check status
- [ ] Display game-over status
- [ ] Add resign option
- [ ] Add return-to-menu option
- [ ] Add restart-game option

---

## 18. Options Menu

- [ ] Create options screen
- [ ] Add basic graphical settings
- [ ] Add basic audio settings if audio is implemented
- [ ] Add gameplay/interface preferences
- [ ] Save settings
- [ ] Load saved settings

---

## 19. Engine/UI Decoupling Validation

- [ ] Console app still works
- [ ] Graphic app uses the same board system
- [ ] Graphic app uses the same piece system
- [ ] Graphic app uses the same movement system
- [ ] Graphic app uses the same chess rules
- [ ] Graphic app uses the same game state
- [ ] No chess rule exists exclusively inside GUI code
- [ ] Engine can operate without any graphical components

---

## 20. Graphic App MVP Validation

- [ ] New game can be created from the GUI
- [ ] Full chess board is rendered correctly
- [ ] Pieces can be moved using the mouse
- [ ] Legal moves are enforced
- [ ] Captures work
- [ ] Special chess rules work
- [ ] Check and checkmate are displayed
- [ ] Games can end normally
- [ ] Player can return to the menu
- [ ] Full chess game can be played without using the console

---

# MILESTONE — GRAPHIC CHESS MVP

- [ ] **Stage 2 complete**

At this point, the same chess engine should support both a console interface and a graphical interface.

---

# STAGE 3 — SURVIVAL CHESS

## Goal

Create a functional prototype of **Survival Chess**, a single-player survival/tower-defense game based on chess mechanics.

This stage will also serve as the primary test of the engine's modularity.

The new game should reuse existing engine systems while adding new rules, pieces, entities, objectives, and board mechanics.

---

## 21. Survival Chess Foundation

- [ ] Define the core Survival Chess rules
- [ ] Define player victory conditions
- [ ] Define player defeat conditions
- [ ] Define wave progression
- [ ] Define enemy spawning rules
- [ ] Define player turn structure
- [ ] Define enemy turn structure
- [ ] Define board size requirements
- [ ] Determine which standard chess rules remain active
- [ ] Determine which standard chess rules are removed or modified

---

## 22. Single-Player Game System

- [ ] Support player-versus-environment games
- [ ] Remove dependency on two human players
- [ ] Add enemy-controlled turns
- [ ] Add automated enemy actions
- [ ] Add enemy target selection
- [ ] Add enemy movement behavior
- [ ] Add enemy attack behavior

---

## 23. Wave System

- [ ] Create wave representation
- [ ] Create wave manager
- [ ] Define wave start conditions
- [ ] Define wave completion conditions
- [ ] Spawn enemies during waves
- [ ] Increase difficulty between waves
- [ ] Track current wave
- [ ] Display wave information
- [ ] Add downtime between waves if necessary

---

## 24. Zombie Pieces

- [ ] Create zombie pawn
- [ ] Create zombie knight
- [ ] Create zombie bishop
- [ ] Create zombie rook
- [ ] Create zombie queen
- [ ] Create zombie king if required
- [ ] Define zombie piece behavior
- [ ] Define differences between zombie and normal pieces
- [ ] Add visual distinction for zombie pieces
- [ ] Balance zombie piece strength

---

# ECONOMIC LAYER

## 25. Resource System

- [ ] Define primary resource/currency
- [ ] Track player resources
- [ ] Add resource gain
- [ ] Add resource spending
- [ ] Display available resources
- [ ] Define resource generation per turn
- [ ] Define resource generation per wave

---

## 26. Building Layer

- [ ] Add a second board layer for buildings
- [ ] Allow pieces and buildings to occupy the same tile when appropriate
- [ ] Create building representation
- [ ] Create building placement rules
- [ ] Create building removal/destruction rules
- [ ] Display buildings independently from pieces
- [ ] Ensure the building system is generic enough for future building types

---

## 27. Farm

- [ ] Implement farm building
- [ ] Define farm construction cost
- [ ] Define farm income
- [ ] Define farm placement restrictions
- [ ] Add farm graphics
- [ ] Balance farm economy

---

## 28. Barracks

- [ ] Implement barracks building
- [ ] Define barracks construction cost
- [ ] Define barracks placement restrictions
- [ ] Allow pieces to be created from barracks
- [ ] Define piece recruitment costs
- [ ] Define recruitment restrictions
- [ ] Add barracks graphics

---

## 29. Defensive Buildings

### Barricades

- [ ] Implement barricades
- [ ] Define placement rules
- [ ] Define defensive behavior
- [ ] Define destruction rules

### Fortresses

- [ ] Implement fortresses
- [ ] Define placement rules
- [ ] Define defensive behavior
- [ ] Define destruction rules

---

## 30. Kingdom Progression

- [ ] Player starts with only a king
- [ ] King can construct basic buildings
- [ ] Buildings generate resources
- [ ] Resources can create new pieces
- [ ] Player can expand their controlled territory
- [ ] New defensive options become available over time
- [ ] Enemy waves scale with player progression

---

# LAST STAND MODE

## 31. Last Stand Rules

- [ ] Create Last Stand game mode
- [ ] Start with standard chess formation
- [ ] Disable creation of new pieces
- [ ] Disable economy if appropriate
- [ ] Disable building system if appropriate
- [ ] Spawn enemy waves
- [ ] Track number of survived waves
- [ ] Track score
- [ ] Define defeat conditions

---

## 32. Survival Chess Interface

- [ ] Create Survival Chess game setup menu
- [ ] Add game mode selection
- [ ] Display current wave
- [ ] Display resources
- [ ] Display buildings
- [ ] Display available construction options
- [ ] Display available recruitment options
- [ ] Add building placement interactions
- [ ] Add piece recruitment interactions
- [ ] Display defeat screen
- [ ] Display survival score

---

## 33. Survival Chess MVP Validation

- [ ] Survival Chess can be launched independently from standard chess
- [ ] Player can start with a king
- [ ] Enemy waves spawn correctly
- [ ] Enemy pieces can act automatically
- [ ] Player can survive multiple waves
- [ ] Player can construct buildings
- [ ] Farms generate resources
- [ ] Barracks can create pieces
- [ ] Defensive buildings function correctly
- [ ] Player can lose the game
- [ ] Wave progression functions correctly
- [ ] Last Stand mode functions correctly
- [ ] Standard Chess still functions correctly
- [ ] Console Chess still functions correctly

---

# MILESTONE — SURVIVAL CHESS MVP

- [ ] **Stage 3 complete**

At this point, the engine should support both traditional chess and a substantially different chess-based game.

---

# ENGINE MODULARITY REVIEW

After completing the three MVPs, review the architecture to determine whether the original engine goals were achieved.

## Board

- [ ] Board size can be changed without major rewrites
- [ ] Additional board layers can be added
- [ ] New tile mechanics can be introduced

## Pieces

- [ ] New piece types can be created easily
- [ ] New movement patterns can be defined easily
- [ ] Pieces are not tightly coupled to chess-specific rules

## Rules

- [ ] Game rules can be replaced or extended
- [ ] Victory conditions can be replaced
- [ ] Turn structures can be modified
- [ ] Special rules can be added without modifying unrelated systems

## Players

- [ ] Human players are supported
- [ ] Computer-controlled players are supported
- [ ] Different numbers of players can theoretically be supported

## User Interfaces

- [ ] Engine operates independently from the console
- [ ] Engine operates independently from the graphical interface
- [ ] Multiple interfaces can use the same engine

## Game Modes

- [ ] Standard Chess works
- [ ] Survival Chess works
- [ ] Last Stand works
- [ ] Adding another game mode would not require rewriting the core engine

---

# FINAL PROJECT MILESTONE

- [ ] Console Chess MVP complete
- [ ] Graphic Chess MVP complete
- [ ] Survival Chess MVP complete
- [ ] Core engine architecture reviewed
- [ ] Major technical debt documented
- [ ] Project documentation updated
- [ ] Future features documented
- [ ] **Project initial development roadmap complete**