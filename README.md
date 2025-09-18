## SOS Game
### Using AI

You can play an "SOS" game with the computer!

The rules:

A short explanation of the code:

The purpose of this exercise is to become more familiar with AI algorithms.
The following is a description of the structures and functions that were constructed.

Move class: Keeps information about the player's movement.
Node class: Keeps information about the possible board states and other structures.

E.g.
The children ArrayList contains the states that can arise from the current state, 
Boolean player which shows us which player has a turn in each state, 
Node nextMove which is a field that we update as we compare the costs in the minimax function to find the next move more easily.

- isMoveLeft function: which checks whether the board table is full and there are no available moves.

- evaluate function: in which we check whether an SOS has been formed in the table and return 1 if it has been formed, otherwise it returns 0.

- DFS function: which fully expands the game tree, putting the costs of the possible final states on its leaves. In these final states, if an SOS is formed resulting from a move by the computer, the cost is +1, otherwise if it results from a move by the player, then it is -1. If, again, the table is filled without creating an SOS, then the cost is 0 and we have a draw.

- minimax function: so that it traverses the tree recursively from the leaves to the root, comparing the costs and updating them, also updating the nextMove field of each node.

- printBoard function: which will print our table and printTree which simply for our convenience when debugging the code, prints the tree.

- findcur function: that we use immediately afterwards, which, taking a node and a board as arguments, returns to which of the children of this node this board corresponds. It is used, essentially, to use the information of the player's movement in order to inform the computer about the node that will be found in his next move.

- In the main program function, DFS and minimax are called to create and update the game tree. Then, a char variable is initialized at the root of the tree and will be used below for the current state of the game and a board variable that stores the table. On this table, the changes that arise as a result of each player's movement will be stored.

Finally, within a while-loop, the game is implemented. The computer's movement is to move from the current state to the next, using the nextMove field. Then, using the board field of the nextMove node,
we update the board. In turn, the player enters the elements of his movement, based on which the board changes, and by calling findcur, we inform the node to which the computer has been transferred about its next move. This process is repeated until the game ends.


