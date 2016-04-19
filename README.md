#include "dork.h"
#include "game.h"

void Load(){
  string file_name;
  printw("Please enter the name of your file: ");
  getstr(file_name);
}

void Save(){
  string file_name;
  printw("Please enter what you want to call your file: ")
  getstr(file_name);
}

void gameData(Display object){
	printw("Do You Wish To Start A New Game? (Y/N)");
	char s=getch();
	if (s==Y||y)
		object.SetName();
		object.SetSurName();
		object.SetCountry();
		object.SetAge();
		Save();
	else if (s==N||n)
		Load();
	else
		printw("Invalid response");
}
