#include "dork.h"
#include "game.h"

void Load(){
	printw("Please Enter Your First Name: ")
	getstr(x); 
	ifstream infile(x);
	if (!infile) {
		cerr<<"Could not open file" << endl;
		return -1;
	}
	getline();
	infile>>obj.GetName;
	infile>>obj.GetSurName;
	infile>>obj.GetAge;
	infile>>obj.GetCountry;
	infile>>obj.GetLevel;
	infile>>obj.GetEnergy;
	infile>>obj.GetSteps;
}
}
void Save(Display obj){
	string x= obj.GetName;
	ofstream outfile(x);
	if (!outfile) {
		cerr<<"Could not open file" << endl;
		return -1;
	}
	outfile<<obj.GetName;
	outfile<<obj.GetSurName;
	outfile<<obj.GetAge;
	outfile<<obj.GetCountry;
	outfile<<obj.GetLevel;
	outfile<<obj.GetEnergy;
	outfile<<obj.GetSteps;
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
