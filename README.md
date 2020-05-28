# LAN-Chess
This project allows two computers on the same LAN network to play Chess against each other through the command line.

![LAN Chess](https://github.com/Robbyswimmer/LAN-Chess/blob/master/images/chess-pic.png)

## How it works

This project is composed of two components: (1) the server, and (2) the client. For every "game" of chess that is played, only one computer must be running the server. The client file for the game is merely in charge of receiving information from the server, displaying that information to the user, and then accepting a valid move from the user and transmitting it back to the server. The client does not handle any decision making, or any logistics of the game, it is simply in charge of translating the information from the server into something understandable for the client. 

The server handles the following:
* Updating the board with user moves 
* Telling each player when it is their turn
* Determining if someone has won the game
* Creating the board and transforming it from a string to an array of bytes
* Sending the board to the correct player

To handle player moves a hash map is used. The keys of this map respond to the alphanumeric index of that spot on the chess board. Thus there are 64 indices in the hash table – a1 to h8. The values of the map respond to the piece that is being stored at that index. Given that there are only 32 pieces in a game of chess, there is at least 32 empty spaces on the board at all times. Empty spaces are just stored as empty strings in the map, and when a piece is captured its place in the map is replaced with an empty string so that it is not included in the next iteration of the board. 

Checking for a winner in chess can be very difficult, so in order to improve on this, a winner is declared when the opposing king has been captured. 

When a player makes a move, that move is sent to the server where the board is updated with the new move and then the board is converted into a string, and then finally into an array of bytes so that the operation time of the server is maintained. Initially, the chess board was being sent over the server as an actual object, but the performance of that was poor and the current solution of creating the board as a string was found to be much better.

## How to use

* Download the zip for this project
* Unzip the package
* Open Terminal or your favored command line
* Play



TEST TEST
