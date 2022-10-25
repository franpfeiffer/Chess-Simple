#include <iostream>
#include <ctype.h>
#define FOR(var)  for(var = 0; var < 8; var++)

using namespace std;

enum color {WHITE, BLACK, EMPTY};

char board[8][8];
enum color turn;

void initializeBoard();
void printBoard();
void movePiece(int , int , int , int);
void readPlay(int *, int *, int *, int *);
int gameEnd();
enum color colorPiece(int , int);

int main(){

	int initial_i, initial_j;
	int final_i, final_j;

	initializeBoard();
	

	do{
		printBoard();
		readPlay(&initial_i, &initial_j, &final_i, &final_j);
		movePiece(initial_i, initial_j, final_i, final_j);
		int turn = 1 - turn;
	} while (!gameEnd());
	
	return 0;
}


void movePiece(int i0 , int j0 , int i1 , int j1){
	board[i1][j1] = board[i0][j0];
	board[i0][j0] = '.';
}

void initializeBoard() {
	int i, j;
	char first_row[] = "tcadract";
	
	FOR (j) {
		board[0][j] = first_row[j];
		board[1][j] = 'p';
		
		for(i = 2; i < 6; i++)
			board[i][j] = '.';
			
		board[6][j] = 'P';
		board[7][j] = toupper(first_row[j]);
	}
}


void printBoard(){
	int i, j;
	
	cout << endl;
	FOR(j)
		cout << " " << j << endl;
	cout << "  +---------------+\n";
	
	FOR(i){
		cout << " |" << 'a' + i;
		FOR(j)
			cout << " " << board[i][j];
		cout << "\b|\n";
	}
	cout << "  +---------------+\n";
}
	
	
enum color colorPiece(int i , int j){
	if(isupper(board[i][j]))
		return WHITE;
	else if(islower(board[i][j]))
		return BLACK;
	else
		return EMPTY;
}
	
void readPlay(int *initial_i , int *initial_j , int *final_i , int *final_j) {
	
	char from[5], to[5];
	
	if(turn == WHITE)
		cout << "White plays: ";
	else if(turn == BLACK)
		cout << "Black plays: ";
	cin >> from >> to;
	
	*initial_i = from[0] - 'a';
	*initial_j = from[1] - '0';
	*final_i = to[0] - 'a';
	*final_j = to[1] - '0';
}
	
int gameEnd(){
	return 0;
}
