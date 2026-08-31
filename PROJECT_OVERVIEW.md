# CHESS GAME

## PROJECT OVERVIEW

The goal of this project is to develop a modular board game engine, using chess as its primary game implementation.

Although chess is the main focus of the project, the engine should be designed in a generic and extensible way so that new mechanics, pieces, rules, game modes, and potentially entirely new games can be added with minimal changes to existing systems.

The project will be developed in three major stages. Each stage will produce a usable MVP and will build upon the systems developed during the previous stages.

The three main stages are:

1. Console Chess Game
2. Graphic Chess App
3. Survival Chess

---

# DESIGN GOALS

## MODULARITY

The engine should be divided into independent systems with clearly defined responsibilities.

Systems such as board management, pieces, movement, turns, players, game state, and rule validation should interact through well-defined interfaces rather than being tightly coupled together.

Changes made to one system should require as few changes as possible to unrelated systems.

---

## EXTENSIBILITY

The engine should make it possible to add new features without requiring major rewrites of existing code.

Examples include:

- New piece types
- New movement patterns
- New board sizes
- New board layers
- New game rules
- New victory and defeat conditions
- New player types
- New game modes
- New user interfaces
- New games using the same engine foundations

Whenever possible, new content should be added by extending existing systems rather than modifying their internal behavior.

---

## ENGINE AND GAME SEPARATION

The project should conceptually be divided into two main layers:

### Engine

The engine contains generic systems that are not directly tied to chess.

Examples include:

- Board representation
- Position and coordinate systems
- Piece or entity management
- Movement systems
- Turn management
- Player management
- Game state management
- Rule execution infrastructure
- Board layers

### Game Implementation

The game implementation contains rules and content specific to a particular game.

For standard chess, this includes:

- Standard chess pieces
- Chess starting positions
- Check
- Checkmate
- Castling
- En passant
- Promotion
- Chess-specific draw conditions

For Survival Chess, this may include:

- Enemy waves
- Zombie pieces
- Buildings
- Economy
- Recruitment
- Survival-specific victory and defeat conditions

The graphical and console interfaces should also remain independent from the core engine.

---

## PROJECT SCOPE

The engine is not intended to support every possible type of board game.

Its primary focus is on turn-based, grid-based strategy games involving movable entities and configurable game rules.

Games significantly outside this model may require systems beyond the intended scope of the engine.

---

# DEVELOPMENT STAGES

# STAGE 1 — CONSOLE CHESS GAME

## GOAL

The first stage aims to create a fully functional console application in which two players can play a complete game of standard chess.

This stage will contain the first implementation of the engine's major systems.

These systems will form the technical foundation for the graphical application and Survival Chess.

---

## MAIN SYSTEMS

This stage should establish systems for:

- Board representation
- Board positions
- Piece management
- Piece movement
- Move validation
- Captures
- Turn management
- Players
- Game state
- Rule validation
- Victory and draw conditions
- Move history
- Game initialization

The systems should be implemented with future reuse in mind rather than being built exclusively around the requirements of standard chess.

---

## CHESS IMPLEMENTATION

The console version should support all standard chess pieces:

- Pawn
- Rook
- Knight
- Bishop
- Queen
- King

It should also support all major standard chess rules, including:

- Legal piece movement
- Captures
- Check
- Checkmate
- Stalemate
- Castling
- En passant
- Pawn promotion
- Standard draw conditions

---

## CONSOLE INTERFACE

The console application should provide a simple interface allowing players to:

- Start a new game
- View the board
- Enter moves
- View the active player
- Receive feedback for invalid moves
- View check and game-ending states
- Return to the main menu
- Quit the application

The console interface should only display and collect information. Chess rules should remain inside the game or engine systems rather than being implemented directly in the console code.

---

## MVP DEFINITION

Stage 1 is complete when a full standard chess game can be played from beginning to end entirely through the console.

The application must correctly enforce the game's rules and detect valid game-ending conditions.

The core engine should also function independently from the console interface.

---

# STAGE 2 — GRAPHIC CHESS APP

## GOAL

The second stage aims to create a fully functional graphical application in which a complete game of chess can be played.

The graphical application should use the same engine and chess implementation developed during Stage 1.

No major chess rule should need to be rewritten specifically for the graphical application.

---

## GRAPHICAL INTERFACE

The graphical application should include a basic user interface containing:

- Main menu
- Game creation menu
- Options menu
- Chess board
- Graphical chess pieces
- Basic game information
- Game-over screen

---

## BOARD INTERACTIONS

The player should be able to interact with the board using the mouse.

Basic interactions should include:

- Selecting pieces
- Selecting destination tiles
- Highlighting the selected piece
- Highlighting valid moves
- Executing moves
- Displaying captures
- Displaying invalid move feedback

---

## QUALITY-OF-LIFE FEATURES

The application may include basic quality-of-life features such as:

- Move history
- Captured piece display
- Active player indicator
- Restart game option
- Return to menu option
- Basic graphical settings
- Basic sound settings

These features are secondary to the main goal of creating a functional graphical chess game.

---

## ENGINE VALIDATION

Stage 2 should serve as the first major validation of the separation between the engine and the user interface.

The console and graphical applications should both be able to interact with the same underlying engine and chess systems.

Changes to graphical code should not affect chess rules, and changes to the console interface should not affect the graphical application.

---

## MVP DEFINITION

Stage 2 is complete when a full standard chess game can be played entirely through the graphical application using mouse interactions.

The console version should continue to function using the same core engine.

---

# STAGE 3 — SURVIVAL CHESS

## GOAL

The third stage aims to create a functional prototype of a new board game called **Survival Chess**.

Survival Chess will reuse the engine and many of the chess systems developed during the previous stages while significantly modifying the structure and objectives of the game.

This stage will act as the primary practical test of the engine's extensibility.

If Survival Chess can be implemented without requiring major rewrites of the original engine, the engine will have successfully achieved one of its main design goals.

---

# SURVIVAL CHESS

## CORE CONCEPT

Survival Chess is a single-player survival strategy game based on chess mechanics.

Instead of fighting another player in a traditional chess match, the player must defend against increasingly dangerous waves of enemy pieces.

The player controls chess pieces and uses familiar chess-inspired movement and capture rules to survive.

---

## CORE GAME LOOP

A typical game should follow a repeating cycle:

1. The player develops their position.
2. Resources are generated or collected.
3. The player spends resources on buildings, defenses, or new pieces.
4. An enemy wave enters the board.
5. The player fights the enemy pieces using chess-inspired mechanics.
6. Surviving the wave gives the player an opportunity to strengthen their position.
7. The next wave becomes progressively more difficult.

The exact structure of turns and wave progression may evolve during prototyping.

---

## TURN STRUCTURE

Survival Chess should remain primarily turn-based in order to preserve the strategic nature of chess.

The exact relationship between player turns, enemy turns, and wave progression will need to be determined during development.

Possible structures include:

- Player turn followed by enemy turn
- Multiple player actions followed by an enemy phase
- Wave-based rounds containing several alternating turns

This system should ideally use or extend the turn system already created for standard chess.

---

## DEFEAT CONDITION

The player's king should act as the central objective of the game.

If the king is captured or otherwise defeated, the game ends.

Additional defeat conditions may eventually be introduced if they improve the game.

---

# SURVIVAL CHESS BRAINSTORM

## LAST STAND

Last Stand is a simplified Survival Chess game mode.

The player begins with the standard chess starting formation and must survive as many enemy waves as possible.

Unlike the full Survival Chess mode:

- New pieces cannot be created
- The player's army is limited to the pieces available at the beginning of the game
- Lost pieces are permanently lost
- Economy and building systems may be disabled

The objective is simply to survive for as long as possible.

Last Stand could also serve as the first Survival Chess prototype because it requires only the wave and enemy systems without requiring the complete economy.

A possible development order would therefore be:

1. Standard Chess
2. Enemy AI
3. Enemy waves
4. Last Stand
5. Economy
6. Buildings
7. Full Survival Chess

---

## ENEMY WAVES

Enemy pieces should enter the board through waves.

Each wave may define:

- Number of enemies
- Enemy piece types
- Spawn positions
- Spawn timing
- Difficulty
- Special behaviors

Wave difficulty should increase as the game progresses.

Possible difficulty increases include:

- More enemies
- Stronger piece combinations
- New enemy types
- More aggressive behavior
- Multiple spawn locations
- Reduced preparation time

---

## ZOMBIE PIECES

The enemies making up most waves could be zombie versions of standard chess pieces.

Examples include:

- Zombie Pawn
- Zombie Rook
- Zombie Knight
- Zombie Bishop
- Zombie Queen

Zombie pieces should generally reuse the movement behavior of their standard chess counterparts.

For example, a Zombie Knight and a normal Knight could use the same underlying knight movement implementation while using different visual representations and behaviors.

Zombie pieces may eventually receive unique abilities or altered rules if required for gameplay.

---

# ECONOMIC LAYER

## CONCEPT

The economic layer expands Survival Chess beyond simple wave survival.

Instead of beginning with the standard chess army, the player begins with only a king and gradually develops a kingdom.

The player collects resources and uses them to:

- Construct buildings
- Recruit new pieces
- Build defensive structures
- Expand their ability to survive future waves

---

## RESOURCES

The game should contain at least one primary resource representing the player's wealth.

Resources may be generated through:

- Buildings
- Surviving waves
- Capturing enemies
- Controlling territory
- Other game mechanics

The exact economy should remain simple during the initial prototype.

---

# BUILDING LAYER

## CONCEPT

Buildings should exist on a separate logical layer from pieces.

A board tile could therefore contain:

- A piece
- A building
- Both, when permitted by game rules

Conceptually, the board may contain multiple layers:

```text
Board
├── Piece Layer
└── Building Layer
```

This layered system could later support other mechanics without requiring major changes to the basic board representation.

---

## BUILDING CONSTRUCTION

The player's king may be responsible for constructing buildings.

A basic construction interaction could work as follows:

1. The king moves to or controls a tile.
2. The player selects a building.
3. The required resources are spent.
4. The building is placed on the building layer of that tile.

Exact construction rules will be determined during prototyping.

---

## FARMS

Farms generate resources for the player.

Possible characteristics include:

- Construction cost
- Resource generation per turn
- Resource generation per wave
- Placement restrictions
- Vulnerability to enemy attacks

Farms would form the basic foundation of the player's economy.

---

## BARRACKS

Barracks allow the player to create new chess pieces.

Different pieces may have different recruitment costs.

Possible recruitment rules include:

- Pieces spawn directly on the barracks
- Pieces spawn on adjacent tiles
- Recruitment requires several turns
- Only one piece can be recruited per barracks during a given period

The initial prototype should use the simplest functional implementation.

---

## DEFENSIVE STRUCTURES

Defensive structures could help the player control or protect important tiles.

Possible structures include:

### Barricades

Barricades could block or restrict movement through a tile.

### Fortresses

Fortresses could provide stronger protection or modify how pieces occupying the tile interact with enemies.

Their exact mechanics should be determined through gameplay experimentation.

---

# KINGDOM DEVELOPMENT

The full Survival Chess mode should allow the player to gradually transform the board.

A typical game may begin with:

```text
King
```

and gradually develop into something resembling:

```text
Kingdom
├── King
├── Pawns
├── Knights
├── Bishops
├── Rooks
├── Farms
├── Barracks
├── Barricades
└── Fortresses
```

The player should constantly balance economic development against immediate military survival.

Investing heavily in the economy may improve long-term strength but leave the player vulnerable to current waves.

Investing heavily in pieces and defenses may improve immediate survival but slow future growth.

This tradeoff should form one of the central strategic elements of Survival Chess.

---

# SURVIVAL CHESS MVP

The initial Survival Chess prototype does not need to contain every brainstormed feature.

The minimum viable version should include:

- Single-player gameplay
- Player-controlled chess pieces
- Enemy-controlled pieces
- Enemy waves
- Increasing wave difficulty
- A king that must be protected
- A clear defeat condition
- Multiple playable waves
- Reuse of the existing board and movement systems

The economy and building systems may be introduced incrementally after the basic survival loop has been proven functional.

A more complete Survival Chess MVP could later include:

- Resource generation
- Farms
- Barracks
- Piece recruitment
- Defensive structures
- Kingdom development

---

# FUTURE POSSIBILITIES

The following ideas may be explored after the primary project goals have been completed:

- Additional zombie piece types
- Unique enemy pieces
- Boss waves
- Larger boards
- Different maps
- Terrain
- Additional board layers
- New buildings
- Technology or upgrade systems
- Different playable factions
- Additional Survival Chess modes
- Procedurally generated waves
- Difficulty settings
- Save and load systems
- Computer-controlled standard chess opponents
- Online multiplayer
- Mod support
- Completely new games using the same engine

These features are not required for the initial project and should not interfere with the completion of the three main development stages.

---

# PROJECT SUCCESS CRITERIA

The project can be considered successful if:

- A complete chess game can be played through the console application.
- A complete chess game can be played through the graphical application.
- Both applications use the same underlying engine.
- Standard chess rules remain separated from generic engine systems where appropriate.
- Survival Chess can reuse major systems from standard chess.
- New pieces and mechanics can be introduced without major modifications to unrelated systems.
- Survival Chess can significantly alter the original chess structure without requiring the engine to be rewritten.
- The architecture remains understandable and maintainable throughout development.

The ultimate technical objective of the project is not simply to implement chess, but to demonstrate that the systems used to implement chess can serve as a foundation for significantly different games.