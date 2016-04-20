#include "dork.h"
#include "game.h"

void Load(Display& obj){
	string x;
	printw("Please Enter Your First Name: ");
	scanw("%s", x.c_str()); 
	ifstream infile(x);
	if (!infile) {
		cerr<<"Could not open file" << endl;
	}
	getline(infile);
	infile>>obj.SetName();

	getline(infile);
	infile>>obj.SetSurName();

	getline(infile);
	infile>stol(obj.SetAge(x));

	getline(infile);
	infile>>obj.SetCountry();

	getline(infile);
	infile>>obj.SetLevel();

	getline(infile);
	infile>>stol(obj.SetEnergy());

	getline(infile);
	infile>>stol(obj.SetSteps());

	infile.close();
};

void Save(Display& obj){
	string x= obj.GetName();
	ofstream outfile(x);
	if (!outfile) {
		cerr<<"Could not open file" << endl;
	}
	outfile<<obj.GetName();
	outfile<<obj.GetSurName();
	outfile<<obj.GetAge();
	outfile<<obj.GetCountry();
	outfile<<obj.GetLevel();
	outfile<<obj.GetEnergy();
	outfile<<obj.GetSteps();
	outfile.close();
}

void gameData(Display& object){
	printw("Do You Wish To Start A New Game? (Y/N)");
	char s=getch();
	if (s=='Y'||'y'){
		object.SetName();
		object.SetSurName();
		object.SetCountry();
		object.SetAge();
		Save(object);
	}
	else if (s=='N'||'n'){
		Load(object);
	}
	else{
		printw("Invalid response");
	}
}
