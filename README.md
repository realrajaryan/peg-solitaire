# Documentation

## `public class PegSolitaireGame`

This class simulates the Peg Solitaire game. Peg solitaire is a board game (or puzzle) in which a single player takes turns removing pegs from a board until either: they have removed all but the final peg to win the game, or they have lost because there are no legal moves left for them to make despite more than one peg remaining on the board. The number of pegs and board-shapes vary, but these pegs are always set into holes arranged in a grid on the board. A legal move involves jumping one peg over a neighboring peg to rest in a hole on the other side, and then removing the peg that was jumped over. Diagonal jumps are not allowed.

 * **Author:** Raj Aryan Singh

     <p>

## `public static void main(String[] args)`

This method is responsible for everything from displaying the opening welcome message to printing out the final thank you. It will clearly be helpful to call several of the following methods from here, and from the methods called from here. See the Sample Runs below for a more complete idea of everything this method is responsible for.

 * **Parameters:** `args` — - any command line arguments may be ignored by this method.

## `public static int readValidInt(Scanner in, String prompt, int min, int max)`

This method is used to read in all inputs from the user. After printing the specified prompt, it will check whether the user�s input is in fact an integer within the specified range. If the user�s input does not represent an integer or does not fall within the required range, print an error message asking for a value within that range before giving the user another chance to enter valid input. The user should be given as many chances as they need to enter a valid integer within the specified range. See the Sample Runs to see how these error messages should be phrased, and to see how the prompts are repeated when multiple invalid inputs are entered by the user.

 * **Parameters:**
   * `in` — - user input from standard in is ready through this.
   * `prompt` — - message describing what the user is expected to enter.
   * `min` — - the smallest valid integer that the user may enter.
   * `max` — - the largest valid integer that the user may enter.
 * **Returns:** - the valid integer between min and max entered by the user.

## `public static char[][] createBoard(int boardType)`

This method creates, initializes, and then returns a rectangular two dimensional array of characters according to the specified boardType. Initial configurations for each of the possible board types are depicted below. Note that pegs are displayed as @s, empty holes are displayed as -s, and extra blank positions that are neither pegs nor holes within each rectangular array are displayed as #s.

 * **Parameters:** `boardType` — - 1-4 indicating one of the following initial patterns: 1) Cross ###@@@###

     ###@@@###
 * **Returns:** - the fully initialized two dimensional array.

## `public static void displayBoard(char[][] board)`

This method prints out the contents of the specified board using @s to represent pegs, -s to represent empty hole, and #s to represent empty positions that are neither pegs nor holes. In addition to this, the columns and rows of this board should be labelled with numbers starting at one and increasing from left to right (for column labels) and from top to bottom (for row labels). See the Sample Runs for examples of how these labels appear next to boards with different dimensions.

 * **Parameters:** `board` — - the current state of the board being drawn.

## `public static int[] readValidMove(Scanner in, char[][] board)`

This method is used to read in and validate each part of a user�s move choice: the row and column that they wish to move a peg from, and the direction that they would like to move/jump that peg in. When the player�s row, column, and direction selection does not represent a valid move, your program should report that their choice does not constitute a legal move before giving them another chance to enter a different move. They should be given as many chances as necessary to enter a legal move. The array of three integers that this method returns will contain: the user�s choice of column as the first integer, their choice of row as the second integer, and their choice of direction as the third.

 * **Parameters:**
   * `in` — - user input from standard in is ready through this.
   * `board` — - the state of the board that moves must be legal on.
 * **Returns:** - the user's choice of column, row, and direction representing a valid move and store

     in that order with an array.

## `public static boolean isValidMove(char[][] board, int row, int column, int direction)`

This method checks whether a specific move (column + row + direction) is valid within a specific board configuration. In order for a move to be a valid: 1)there must be a peg at position row, column within the board, 2)there must be another peg neighboring that first one in the specified direction, and 3)there must be an empty hole on the other side of that neighboring peg (further in the specified direction). This method only returns true when all three of these conditions are met. If any of the three positions being checked happen to fall beyond the bounds of your board array, then this method should return false. Note that the row and column parameters here begin with one, and may need to be adjusted if your programming language utilizes arrays with zero-based indexing.

 * **Parameters:**
   * `board` — - the state of the board that moves must be legal on.
   * `row` — - the vertical position of the peg proposed to be moved.
   * `column` — - the horizontal position of the peg proposed to be moved.
   * `direction` — - the direction proposed to move/jump that peg in.
 * **Returns:** - true when the proposed move is legal, otherwise false.

## `public static char[][] performMove(char[][] board, int row, int column, int direction)`

The parameters of this method are the same as those of the isValidMove() method. However this method changes the board state according to this move parameter (column + row + direction), instead of validating whether the move is valid. If the move specification that is passed into this method does not represent a legal move, then do not modify the board.

 * **Parameters:**
   * `board` — - the state of the board will be changed by this move.
   * `row` — - the vertical position that a peg will be moved from.
   * `column` — - the horizontal position that a peg will be moved from.
   * `direction` — - the direction of the neighbor to jump this peg over.
 * **Returns:** - the updated board state after the specified move is taken.

## `public static int countPegsRemaining(char[][] board)`

This method counts up the number of pegs left within a particular board configuration, and returns that number.

 * **Parameters:** `board` — - the board that pegs are counted from.
 * **Returns:** - the number of pegs found in that board.

## `public static int countMovesAvailable(char[][] board)`

This method counts up the number of legal moves that are available to be performed in a given board configuration.

 * **Parameters:** `board` — - the board that possible moves are counted from.
 * **Returns:** - the number of legal moves found in that board.
