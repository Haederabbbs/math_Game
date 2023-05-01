# math_Game
// project 2_Quation_Mathec.cpp : This file contains the 'main' function. Program execution begins and ends there.
//
ا

#include <iostream>
#include<cstdlib>
using namespace std;

enum EnuQuastionLvel
{
	Easy = 1, Mad = 2, Hard = 3, mix = 4
};
enum EnuOprationTyepe
{
	add = 1, Sub = 2, Mullt = 3, Dived = 4, Mix = 5
};

enum EnColoers
{
	Read = 1, Grean = 2, Yallo = 3, Blacke = 4
};


struct StrGameROUNDInfo
{

	int NumberQuastion;
	int Number1, number2;
	int ResultOfNumber;
	EnuQuastionLvel QuastionLevel;
	EnuOprationTyepe OprationTyepe;

};
struct StrResultGame
{
	int NumberQuastion;
	string QuastionLevel;
	string OprationTyepe;
	int NumberRightAnnser;
	int NumberWoringAnnser;
};

struct StQuestion
{
	int number1=0;
	int number2=0;
	EnuOprationTyepe QuestionType;
	EnuQuastionLvel QuestionLevel;
	int CorrectAnnser=0;
	int PlayerAnnser=0;
	bool AnnserResult=0;
};
struct StQuiezz
{
	StQuestion QuestionLest[100];
	short NumberOfQuestion;
	EnuOprationTyepe EnimQuestonType;
	EnuQuastionLvel EnuQuestionLevel;
	short NumberWoringAnser=0;
	short NumberwrighetAnnser=0;
	bool IPass = false;
};
int RandmNumber(int From, int To) {
	return  rand() % (To - From + 1) + From;

}
int ReadNumber(string comint) {
	int Number = 0;
	do
	{
		cout << comint << endl;
		cin >> Number;
	} while (Number <= 0);

	return Number;

}
int HowManyQuestionDoYouWaintPly() {
	int NumberQuation = 0;
	do
	{
		cout << "How Many Quastion Do You Waint Annser\n";
		cin >> NumberQuation;
	} while (NumberQuation <= 0);
	return NumberQuation;



}

int ReadNumberFromUser() {
	int NumberToCombaring = 0;


	cin >> NumberToCombaring;

	return NumberToCombaring;
}



EnuQuastionLvel ReadQuationLevel() {
	int ChoesLevel = 0;
	cout << "enter Quaston Level [1]: Easy [2]:Med [3]:Hard [4]:Mix ? \n";
	cin >> ChoesLevel;
	return (EnuQuastionLvel)ChoesLevel;
}
EnuOprationTyepe ReadQuationTyepe() {
	int TyepOraratoin = 0;
	cout << "enter Tyeps  Quaston  [1]: Add [2]:Sub [3]:Multb [4]:Dived [5]:Mix ? \n";
	cin >> TyepOraratoin;
	return (EnuOprationTyepe)TyepOraratoin;
}


string ShowTyepOpration(EnuOprationTyepe ShowOpration) {
	string Opration[5] = { "+","-","*","/","Mix" };

	return Opration[ShowOpration - 1];
}

string ShowTyepOprationToPrint(EnuOprationTyepe ShowOpration) {
	string Opration[4] = { "+","-","*","/" };

	return Opration[ShowOpration - 1];
}
string ShowTyeLevels(EnuQuastionLvel ShowLevels) {
	string Opration[4] = { "Easy", "Mad", "Hard", "Mix" };

	return Opration[ShowLevels - 1];
}


void  ShoNumbersInSiedOpration(int Number1, int Number2, EnuOprationTyepe TypeOpration) {


	cout << "\n" << Number1 << "  " << "\n" << Number2 << " "  << endl << "_____" << endl;











	// Plan (B)StrGameROUNDInfo FillNumberInciedFunation;
		//FillNumberInciedFunation.Number1 = Number1;
		//FillNumberInciedFunation.number2 = Number2;
		//FillNumberInciedFunation.OprationTyepe = TypeOpration;
}
EnuQuastionLvel MixChoesRandomOfLevelGame() {
	int RandomChoesLevel = 0;
	RandomChoesLevel = RandmNumber(1, 3);
	return (EnuQuastionLvel)RandomChoesLevel;
}
EnuOprationTyepe MixChoesRandomOfOprationType() {
	int RandomChoesOpration = 0;
	RandomChoesOpration = RandmNumber(1, 4);
	return (EnuOprationTyepe)RandomChoesOpration;
}



int SumpleCaloueted(int Number1, int Number2,EnuOprationTyepe OpType) {

	switch (OpType)
	{
	case EnuOprationTyepe::add:
	
		return Number1 + Number2;
		break;
	case  EnuOprationTyepe::Sub:
	

		return Number1 - Number2;
		break;
	case EnuOprationTyepe::Mullt:
	

		return Number1 * Number2;
		break;
	case EnuOprationTyepe::Dived:

		return Number1 / Number2;
		break;

	}
}

StrGameROUNDInfo ChoesLevelYouWinted(EnuOprationTyepe TyepOfOpration, EnuQuastionLvel LevelGame) {

	StrGameROUNDInfo InfGame;


	if (LevelGame == ::mix) {
		LevelGame= MixChoesRandomOfLevelGame();
	}

	if (LevelGame == ::Easy) {
		if (TyepOfOpration == ::Mix) {
			TyepOfOpration = MixChoesRandomOfOprationType();
		}
		//RandomHeere useed it
		int Number1 = 0, Number2 = 0;
		Number1 = RandmNumber(1, 10);
		Number2 = RandmNumber(1, 10);
		


		switch (TyepOfOpration)
		{
		case EnuOprationTyepe::add:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber=InfGame.Number1 + InfGame.number2;
			InfGame.OprationTyepe =TyepOfOpration;
			InfGame.QuastionLevel=LevelGame;
			return InfGame;
			
			break;
		case EnuOprationTyepe::Sub:
			//(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 - InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

		case  EnuOprationTyepe::Mullt:

			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 * InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

		case EnuOprationTyepe::Dived:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 / InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

			break;
	
		
			


		}


	}


		if (LevelGame == ::Mad) {
			//RandomHeere useed it
			int Number1 = 0, Number2 = 0;
			Number1 = RandmNumber(20, 50);
			Number2 = RandmNumber(20, 50);

			if (TyepOfOpration == ::Mix) {
				TyepOfOpration = MixChoesRandomOfOprationType();
			}
			
		switch (TyepOfOpration)
		{
		case EnuOprationTyepe::add:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 + InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

			break;
		case EnuOprationTyepe::Sub:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 - InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

		case  EnuOprationTyepe::Mullt:

			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 * InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

		case EnuOprationTyepe::Dived:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 / InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

			break;
	
		}


	}



		if (LevelGame == ::Hard) {
			//RandomHeere useed it
			int Number1 = 0, Number2 = 0;
			Number1 = RandmNumber(50, 100);
			Number2 = RandmNumber(50, 100);

			if (TyepOfOpration == ::Mix) {
				TyepOfOpration = MixChoesRandomOfOprationType();
			}
			
		switch (TyepOfOpration)
		{
		case EnuOprationTyepe::add:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 + InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

			break;
		case EnuOprationTyepe::Sub:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 - InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

		case  EnuOprationTyepe::Mullt:

			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 * InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

		case EnuOprationTyepe::Dived:
			//ShoNumbersInSiedOpration(Number1, Number2, TyepOfOpration);
			InfGame.Number1 = Number1;
			InfGame.number2 = Number2;
			InfGame.ResultOfNumber = InfGame.Number1 / InfGame.number2;
			InfGame.OprationTyepe = TyepOfOpration;
			InfGame.QuastionLevel = LevelGame;
			return InfGame;

			break;
	

		}

	}


}

StrGameROUNDInfo MixLevel(EnuOprationTyepe TyepOfOpration, EnuQuastionLvel LevelGame) {

	EnuQuastionLvel LevelGameMix = MixChoesRandomOfLevelGame();
	return ChoesLevelYouWinted(TyepOfOpration, LevelGameMix);

}
StrGameROUNDInfo MixOprationl(EnuOprationTyepe TyepOfOpration, EnuQuastionLvel LevelGame) {
	EnuQuastionLvel LevelGameMix = MixChoesRandomOfLevelGame();
	return ChoesLevelYouWinted(TyepOfOpration, LevelGameMix);


}

/*
StrGameROUNDInfo   UserChoesLevelAndOprationType(EnuQuastionLvel LevelGame, EnuOprationTyepe TypeOpration) {

	StrGameROUNDInfo Info;
	int Result = 0;

	switch (LevelGame)
	{
	case  EnuQuastionLvel::Easy:
		 Info=ChoesLevelYouWinted(TypeOpration, Easy);
		
		 return Info;
		break;
	case EnuQuastionLvel::Mad:
		Info = ChoesLevelYouWinted(TypeOpration, Mad);
		return Info;
		break;
	case  EnuQuastionLvel::Hard:
		Info = ChoesLevelYouWinted(TypeOpration, Hard);
		return Info;
		break;
	case EnuQuastionLvel::mix:
		EnuQuastionLvel LevelGameMix = MixChoesRandomOfLevelGame();
		Info = ChoesLevelYouWinted(TypeOpration,LevelGameMix );
		return Info;


		break;
	}
}

*/

void  ColorOfResultGame(bool Quess) {

	if (Quess) {
		system("color 2F");
	}
	else
		system("color 4F");
}

string PrintSpaceYouWianted(int Number) {
	string Space = "";
	for (int i = 0; i < Number; i++) {

		Space += "\t";
	}
	return Space;

}

string PrintTapeSpace(int length) {
	string space = "";
	for (int i = 0; i < length; i++)
	{
		space += "__";
	}
	return space;
}
string GeatFinalResultText(bool Pass) {
	if (Pass)
		return "Pass";
	else
		return "Filled";
}

/*
void PassOrNot(StrResultGame CorrectAnsser) {


	if (CorrectAnsser.NumberRightAnnser > CorrectAnsser.NumberWoringAnnser) {
		ColorOfResultGame(EnColoers::Grean);

		cout << "\n\n" << PrintTapeSpace(20) << endl;
		cout << "\n Final Result Game Is Passe :)\n";
		cout << PrintTapeSpace(10) << endl;
	}
	else if (CorrectAnsser.NumberRightAnnser == CorrectAnsser.NumberWoringAnnser) {
		ColorOfResultGame(EnColoers::Yallo);

		cout << "\n\n" << PrintTapeSpace(20) << endl;
		cout << "\n Final Result Game Is equal :)\n";
		cout << PrintTapeSpace(10) << endl;
	}
	else
	{
		ColorOfResultGame(EnColoers::Read);

		cout << "\n\n" << PrintTapeSpace(20) << endl;
		cout << " \n Final Result Game Is Failld  :(\n";
		cout << PrintTapeSpace(20) << endl;
	}

}

StrResultGame FillFinalGame(int numberQuastion, string levelgame, EnuOprationTyepe  typeOpration, int NumberCorrectAnnser, int NumberFasAnnser) {
	StrResultGame FillFinal;
	FillFinal.NumberQuastion = numberQuastion;
	FillFinal.NumberRightAnnser = NumberCorrectAnnser;
	FillFinal.NumberWoringAnnser = NumberFasAnnser;
	FillFinal.QuastionLevel = levelgame;
	//NameOfOpration Correct
	FillFinal.OprationTyepe =typeOpration;
	PassOrNot(FillFinal);
	return FillFinal;
}


bool ChektWrigheAnsserWoringAnnser(StrGameROUNDInfo ResultGame, int NumberFromUser) {

	if (ResultGame.ResultOfNumber == NumberFromUser) {
		ColorOfResultGame(EnColoers::Grean);
		cout << "\nWrighet Answers  :)\n";
		return true;
	}
	else
	{

		cout << " Woring Answer :( \n" << endl;
		cout << "The Right Answer is :  " << ResultGame.ResultOfNumber << "\n";
		ColorOfResultGame(EnColoers::Read);
		return false;
	}
}


void PrintLestOfMathe(int NumberOfround, StrGameROUNDInfo FillInfoRoindGame,int FillRoundGame) {

	


	cout << "Quatoin [ " << FillRoundGame << "/" <<NumberOfround << " ] \n\n";


	cout << FillInfoRoindGame.Number1 << "\n" << FillInfoRoindGame.number2 << " " <<ShowTyepOpration( FillInfoRoindGame.OprationTyepe )<< endl;

	cout << "__________\n";


}
StrResultGame   FillGameInfoRound() {
	// Most Return Value  StrResultGame
	int NumberFromUser = 0;
	StrGameROUNDInfo FillRoundGame;
	int NumberQustionToPly = HowManyQuestionDoYouWaintPly();
	EnuQuastionLvel AnyLevel = QuationLevel();
	EnuOprationTyepe TyepOpration = QuationTyepe();
	string NameLavelQuastion = ShowTyeLevels(AnyLevel);

	int ReadNumberToComparingResult = 0;
	int ResultGame = 0;
	int numberQuastion; string levelgame; EnuOprationTyepe  typeOpration; int NumberCorrectAnnse = 0;  int NumberFasAnnser = 0;
	for (int i = 1; i <= NumberQustionToPly; i++) {

	
		FillRoundGame = ChoesLevelYouWinted( TyepOpration,AnyLevel);

		PrintLestOfMathe(NumberFromUser, FillRoundGame,i);
		NumberFromUser = ReadNumberFromUser();
		if (ChektWrigheAnsserWoringAnnser(FillRoundGame, NumberFromUser)) {
			NumberCorrectAnnse++;
		}
		else
		{
			NumberFasAnnser++;
		}

	}

	numberQuastion = NumberQustionToPly;
	levelgame = NameLavelQuastion;
	typeOpration = TyepOpration;


	return FillFinalGame(numberQuastion, levelgame, typeOpration, NumberCorrectAnnse, NumberFasAnnser);
}

*/

StQuestion GenratedQuestion(EnuOprationTyepe TyepOfOpration, EnuQuastionLvel LevelGame) {
	StQuestion Question;

	int Number1 = 0;
	int Number2 = 0;

	if (LevelGame == ::mix) {
		LevelGame = MixChoesRandomOfLevelGame();
	}

	if (TyepOfOpration == ::Mix) {
		TyepOfOpration = MixChoesRandomOfOprationType();
	}

		switch (LevelGame)
		{

		case Easy:
			 Number1 = RandmNumber(1, 10);
			 Number2 = RandmNumber(1, 10);
			Question.QuestionType = TyepOfOpration;

			Question.QuestionType = TyepOfOpration;
			Question.number1 = Number1;
			Question.number2 = Number2;
			 Question.CorrectAnnser= SumpleCaloueted(Number1, Number2, TyepOfOpration);
			
			 return Question;
			break;
		case Mad:
		 Number1 = RandmNumber(20, 50);
		 Number2 = RandmNumber(20, 50);
			Question.QuestionType = TyepOfOpration;

			Question.QuestionType = TyepOfOpration;
			Question.number1 = Number1;
			Question.number2 = Number2;
			Question.CorrectAnnser = SumpleCaloueted(Number1, Number2, TyepOfOpration);

			return Question;
			break;
		case Hard:
			 Number1 = RandmNumber( 50,100);
			 Number2 = RandmNumber(50,100);
			Question.QuestionType = TyepOfOpration;

			Question.QuestionType = TyepOfOpration;
			Question.number1 = Number1;
			Question.number2 = Number2;
			Question.CorrectAnnser = SumpleCaloueted(Number1, Number2, TyepOfOpration);

			return Question;
			break;
	
		}


	}



 
void GenaretQueszQuestion(StQuiezz &Queszz) {
	for (int Question  = 0; Question <Queszz.NumberOfQuestion ;Question ++)
	{
		Queszz.QuestionLest[Question] = GenratedQuestion(Queszz.EnimQuestonType, Queszz.EnuQuestionLevel);
	}
 }
void PrintQuestion(StQuiezz Queszz, short QueastionNumber) {
	cout << "\n";
	cout << "Question [" << QueastionNumber + 1 << "/" << Queszz.NumberOfQuestion << "] \n\n";
	cout << Queszz.QuestionLest[QueastionNumber].number1 << endl;
	cout << Queszz.QuestionLest[QueastionNumber].number2 << "  ";
	cout << ShowTyepOpration(Queszz.QuestionLest[QueastionNumber].QuestionType);
	cout << "\n__________\n";
}
void QurrectTheQuestionAnnser(StQuiezz &Quieszz, int NumberQuestion) {

	if (Quieszz.QuestionLest[NumberQuestion].PlayerAnnser != Quieszz.QuestionLest[NumberQuestion].CorrectAnnser) {
		Quieszz.QuestionLest[NumberQuestion].AnnserResult = false;
		Quieszz.NumberWoringAnser++;
		cout << "The Woring Annser :-( \n";
		cout << "The righet Annser Is : ";
		cout<<Quieszz.QuestionLest[NumberQuestion].CorrectAnnser << endl;
		cout << "\n";
	}
	else
	{

		Quieszz.QuestionLest[NumberQuestion].AnnserResult = true;
		Quieszz.NumberwrighetAnnser++;
		cout << "Righet Answer :-)";
	}
	ColorOfResultGame(Quieszz.QuestionLest[NumberQuestion].AnnserResult);
}
void AskAndCorrectQuestionListAnnser(StQuiezz &Queaszz) {

	for (int QueszzNumber = 0; QueszzNumber < Queaszz.NumberOfQuestion; QueszzNumber++)
	{
		PrintQuestion(Queaszz, QueszzNumber);
		Queaszz.QuestionLest[QueszzNumber].PlayerAnnser = ReadNumberFromUser();
		QurrectTheQuestionAnnser(Queaszz,QueszzNumber);
	}
	 Queaszz.IPass = (Queaszz.NumberwrighetAnnser >= Queaszz.NumberWoringAnser);
}
void PrintLestGameResult(StQuiezz Quessz) {
	cout << "\n";
	cout << PrintTapeSpace(15) << endl;
	cout << "Finale Result is " << GeatFinalResultText(Quessz.IPass);
	cout << "\n Number Of Question : " << Quessz.NumberOfQuestion << endl;
	cout << "Question  Level   : " << ShowTyepOpration(Quessz.EnimQuestonType)<<endl;
	cout << "Opration Tyepe    : " <<ShowTyeLevels(Quessz.EnuQuestionLevel)<<endl;
	cout << "Number Of Righet Answer : " << Quessz.NumberwrighetAnnser << endl;
	cout << "Number Of wrong : " << Quessz.NumberWoringAnser;
}
void PlyGame() {
	StQuiezz Quesz;
	Quesz.NumberOfQuestion = HowManyQuestionDoYouWaintPly();
	Quesz.EnimQuestonType = ReadQuationTyepe();
	Quesz.EnuQuestionLevel = ReadQuationLevel();
	GenaretQueszQuestion(Quesz);
	AskAndCorrectQuestionListAnnser(Quesz);
	PrintLestGameResult(Quesz);
}

void ClearScreen() {
	system("cls");
	system("color 0F");

}


void StartGame() {



	char PlyeAgeinAnsserYOrN = 'y';
	do {

		ClearScreen();
		PlyGame();
		cout << "\n Do You Weent Ply Agean \n";
		cin >> PlyeAgeinAnsserYOrN;


	} while (PlyeAgeinAnsserYOrN == 'y');
}



int main()
{
	srand((unsigned)time(NULL));
	StartGame();
	//ChoesLevelYouWinted((EnuOprationTyepe)4, (EnuQuastionLvel)4);
}

// Run program: Ctrl + F5 or Debug > Start Without Debugging menu
// Debug program: F5 or Debug > Start Debugging menu

// Tips for Getting Started: 
//   1. Use the Solution Explorer window to add/manage files
//   2. Use the Team Explorer window to connect to source control
//   3. Use the Output window to see build output and other messages
//   4. Use the Error List window to view errors
//   5. Go to Project > Add New Item to create new code files, or Project > Add Existing Item to add existing code files to the project
//   6. In the future, to open this project again, go to File > Open > Project and select the .sln file
