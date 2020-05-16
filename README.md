#include <iostream>
#include <Windows.h>
#include <ctime>
#include <conio.h>
#include <string>
using namespace std;

int main()
{
	setlocale(0, "Rus");
	srand(time(0));
	rand();
	HANDLE h = GetStdHandle(STD_OUTPUT_HANDLE);
	COORD pA;
	COORD cA;
	system("cls");
	cout << "Добро пожаловать в игру \"Камень, ножницы, бумага\"   " << endl;
	cout << "Выберите уровень сложности: " << endl;
	cout << "1 - изи-пизи;  ";
	cout << "2 - попаболь;" << endl;
	int difficulty;
	cin >> difficulty;
	string playerAnswer;
	string computerAnswer;
	int objectCount;

	if (difficulty == 1) //легко
	{
		cout << "На простом уровне сложности есть только Stone, Scissors и Paper";
		cout << "Ваша задача выбрать что-то одно и молиться на победу :)";
		cout << "Удачи! :)" << endl;
		Sleep(1000);
		system("cls");
		objectCount = 3;
		Sleep(1000);
		cout << "Введите наименование вашего предмета: " << endl;
		cin >> playerAnswer;
		int c_answ = rand() % objectCount + 1;
		if (c_answ == 1)
		{
			computerAnswer = "Paper";
		}
		else if (c_answ == 2)
		{
			computerAnswer = "Stone";
		}
		else if (c_answ == 3)
		{
			computerAnswer = "Scissors";
		}
		cout << "Please, wait! We are computing ^_^" << endl;
		Sleep(3000);
		system("cls");
		Sleep(1000);

		/////////////ответ игрока
		pA.X = 30;
		pA.Y = 15;
		SetConsoleCursorPosition(h, pA);
		SetConsoleTextAttribute(h, 3);
		cout << "Ваш выбор: " << playerAnswer << endl;
		////////////////////////////////

		///////////ответ компьтера
		cA.X = 60;
		cA.Y = 15;
		SetConsoleCursorPosition(h, cA);
		SetConsoleTextAttribute(h, 3);
		cout << "Выбор компьтера: " << computerAnswer << endl;
		////////////////////////////////

		COORD result;
		if (playerAnswer == computerAnswer)
		{
			while (true)
			{
				result.X = 45;
				result.Y = 18;
				SetConsoleCursorPosition(h, result);
				SetConsoleTextAttribute(h, 3);
				cout << "У вас ничья :0";
				Sleep(2000);
				result.Y++;
				cout << "Если хотите начать заново нажмите Пробел (Space) ";
				result.Y++;
				cout << "Если хотите выйти нажмите Escape ";
				result.Y++;
				int code = _getch();
				if (code == 32)
				{
					main();
				}
				else if (code == 27)
				{
					exit(0);
				}
				else
				{
					cout << "Такого выбора нет :(";
				}
				system("cls");
			}
		}
		else if (playerAnswer == "Paper")
		{
			if (computerAnswer == "Stone")
			{
				while (true)
				{
					result.X = 45;
					result.Y = 18;
					SetConsoleCursorPosition(h, result);
					SetConsoleTextAttribute(h, 3);
					cout << "Вы победили :0 :0 :0";
					result.Y++;
					cout << "Если хотите начать заново нажмите Пробел (Space) ";
					result.Y++;
					cout << "Если хотите выйти нажмите Escape ";
					result.Y++;
					int code = _getch();
					if (code == 32)
					{
						main();
					}
					else if (code == 27)
					{
						exit(0);
					}
					else
					{
						cout << "Такого выбора нет :(";
					}
					system("cls");
				}
			}
			else if (computerAnswer == "Scissors")
			{
				while (true)
				{
					result.X = 45;
					result.Y = 18;
					SetConsoleCursorPosition(h, result);
					SetConsoleTextAttribute(h, 6);
					cout << "Вы проигали :(";
					result.Y++;
					Sleep(2000);
					SetConsoleTextAttribute(h, 3);
					cout << "Если хотите начать заново нажмите Пробел (Space) ";
					result.Y++;
					cout << "Если хотите выйти нажмите Escape ";
					result.Y++;
					int code = _getch();
					if (code == 32)
					{
						main();
					}
					else if (code == 27)
					{
						exit(0);
					}
					else
					{
						cout << "Такого выбора нет :(";
					}
					system("cls");
				}
			}
		}
		else if (playerAnswer == "Scissors")
		{
			if (computerAnswer == "Paper")
			{
				while (true)
				{
					result.X = 45;
					result.Y = 18;
					SetConsoleCursorPosition(h, result);
					SetConsoleTextAttribute(h, 3);
					cout << "Вы победили :0 :0 :0";
					result.Y++;
					cout << "Если хотите начать заново нажмите Пробел (Space) ";
					result.Y++;
					cout << "Если хотите выйти нажмите Escape ";
					result.Y++;
					int code = _getch();
					if (code == 32)
					{
						main();
					}
					else if (code == 27)
					{
						exit(0);
					}
					else
					{
						cout << "Такого выбора нет :(";
					}
					system("cls");
				}
			}
			else if (computerAnswer == "Stone")
			{
				while (true)
				{
					result.X = 45;
					result.Y = 18;
					SetConsoleCursorPosition(h, result);
					SetConsoleTextAttribute(h, 6);
					cout << "Вы проигали :(";
					result.Y++;
					Sleep(2000);
					SetConsoleTextAttribute(h, 3);
					cout << "Если хотите начать заново нажмите Пробел (Space) ";
					result.Y++;
					cout << "Если хотите выйти нажмите Escape ";
					result.Y++;
					int code = _getch();
					if (code == 32)
					{
						main();
					}
					else if (code == 27)
					{
						exit(0);
					}
					else
					{
						cout << "Такого выбора нет :(";
					}
					system("cls");
				}
			}
		}
		else if (playerAnswer == "Stone")
		{
		if (computerAnswer == "Scissors")
		{
			while (true)
			{
				result.X = 45;
				result.Y = 18;
				SetConsoleCursorPosition(h, result);
				SetConsoleTextAttribute(h, 3);
				cout << "Вы победили :0 :0 :0";
				result.Y++;
				cout << "Если хотите начать заново нажмите Пробел (Space) ";
				result.Y++;
				cout << "Если хотите выйти нажмите Escape ";
				result.Y++;
				int code = _getch();
				if (code == 32)
				{
					main();
				}
				else if (code == 27)
				{
					exit(0);
				}
				else
				{
					cout << "Такого выбора нет :(";
				}
				system("cls");
			}
		}
		else if (computerAnswer == "Paper")
		{
			while (true)
			{
				result.X = 45;
				result.Y = 18;
				SetConsoleCursorPosition(h, result);
				SetConsoleTextAttribute(h, 6);
				cout << "Вы проигали :(";
				result.Y++;
				Sleep(2000);
				SetConsoleTextAttribute(h, 3);
				cout << "Если хотите начать заново нажмите Пробел (Space) ";
				result.Y++;
				cout << "Если хотите выйти нажмите Escape ";
				result.Y++;
				int code = _getch();
				if (code == 32)
				{
					main();
				}
				else if (code == 27)
				{
					exit(0);
				}
				else
				{
					cout << "Такого выбора нет :(";
				}
				system("cls");
			}
		}
		}

	}
	else if (difficulty == 2) // не легко
	{
	  Sleep(2000);
	  system("cls");
	  cout << "Вы выбрали средний уровень сложности. В данном уровне присутствуют предметы: " << endl <<
		  "Stone, Paper, Scissors, Well" << endl << "Желаем Вам удачи :)" << endl;
	  Sleep(10000);
	  objectCount = 4;
	  cout << "Введите наименование вашего предмета: " << endl;
	  cin >> playerAnswer;
	  int c_answ = rand() % objectCount + 1;
	  if (c_answ == 1)
	  {
		  computerAnswer = "Paper";
	  }
	  else if (c_answ == 2)
	  {
		  computerAnswer = "Stone";
	  }
	  else if (c_answ == 3)
	  {
		  computerAnswer = "Scissors";
	  }
	  else if (c_answ == 4)
	  {
		  computerAnswer = "Well";
	  }

	  cout << "Please, wait! We are computing ^_^" << endl;
	  Sleep(3000);
	  system("cls");
	  Sleep(1000);

	  /////////////ответ игрока
	  pA.X = 30;
	  pA.Y = 15;
	  SetConsoleCursorPosition(h, pA);
	  SetConsoleTextAttribute(h, 3);
	  cout << "Ваш выбор: " << playerAnswer << endl;
	  ////////////////////////////////

	  ///////////ответ компьтера
	  cA.X = 60;
	  cA.Y = 15;
	  SetConsoleCursorPosition(h, cA);
	  SetConsoleTextAttribute(h, 3);
	  cout << "Выбор компьтера: " << computerAnswer << endl;
	  ////////////////////////////////

	  COORD result;
	  if (playerAnswer == computerAnswer)
	  {
		  while (true)
		  {
			  result.X = 45;
			  result.Y = 18;
			  SetConsoleCursorPosition(h, result);
			  SetConsoleTextAttribute(h, 3);
			  cout << "У вас ничья :0";
			  Sleep(2000);
			  result.Y++;
			  cout << "Если хотите начать заново нажмите Пробел (Space) ";
			  result.Y++;
			  cout << "Если хотите выйти нажмите Escape ";
			  result.Y++;
			  int code = _getch();
			  if (code == 32)
			  {
				  main();
			  }
			  else if (code == 27)
			  {
				  exit(0);
			  }
			  else
			  {
				  cout << "Такого выбора нет :(";
			  }
			  system("cls");
		  }
	  }
	  else if (playerAnswer == "Paper")
	  {
		  if (computerAnswer == "Stone")
		  {
			  while (true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Вы победили :0 :0 :0";
				  result.Y++;
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
		  else if (computerAnswer == "Scissors")
		  {
			  while (true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 6);
				  cout << "Вы проигали :(";
				  result.Y++;
				  Sleep(2000);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
		  else if (computerAnswer == "Well")
		  {
			  result.X = 45;
			  result.Y = 18;
			  SetConsoleCursorPosition(h, result);
			  SetConsoleTextAttribute(h, 3);
			  cout << "Вы победили :0 :0 :0";
			  result.Y++;
			  cout << "Если хотите начать заново нажмите Пробел (Space) ";
			  result.Y++;
			  cout << "Если хотите выйти нажмите Escape ";
			  result.Y++;
			  int code = _getch();
			  if (code == 32)
			  {
				  main();
			  }
			  else if (code == 27)
			  {
				  exit(0);
			  }
			  else
			  {
				  cout << "Такого выбора нет :(";
			  }
			  system("cls");
		  }
	  }
	  else if (playerAnswer == "Scissors")
	  {
		  if (computerAnswer == "Paper")
		  {
			  while (true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Вы победили :0 :0 :0";
				  result.Y++;
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
		  else if (computerAnswer == "Stone")
		  {
			  while(true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 6);
				  cout << "Вы проигали :(";
				  result.Y++;
				  Sleep(2000);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
		  else if (computerAnswer == "Well")
		  {
			  while (true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 6);
				  cout << "Вы проигали :(";
				  result.Y++;
				  Sleep(2000);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
	  }
	  else if (playerAnswer == "Stone")
	  {
		  if (computerAnswer == "Scissors")
		  {
			  while(true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Вы победили :0 :0 :0";
				  result.Y++;
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
		  else if (computerAnswer == "Paper")
		  {
			  while(true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 6);
				  cout << "Вы проигали :(";
				  result.Y++;
				  Sleep(2000);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
		  else if (computerAnswer == "Well")
		  {
			  while (true)
			  {
				  result.X = 45;
				  result.Y = 18;
				  SetConsoleCursorPosition(h, result);
				  SetConsoleTextAttribute(h, 6);
				  cout << "Вы проигали :(";
				  result.Y++;
				  Sleep(2000);
				  SetConsoleTextAttribute(h, 3);
				  cout << "Если хотите начать заново нажмите Пробел (Space) ";
				  result.Y++;
				  cout << "Если хотите выйти нажмите Escape ";
				  result.Y++;
				  int code = _getch();
				  if (code == 32)
				  {
					  main();
				  }
				  else if (code == 27)
				  {
					  exit(0);
				  }
				  else
				  {
					  cout << "Такого выбора нет :(";
				  }
				  system("cls");
			  }
		  }
	  }
	  else if (playerAnswer == "Well")
	  {
	    if (computerAnswer == "Stone")
	    {
			while (true)
			{
				result.X = 45;
				result.Y = 18;
				SetConsoleCursorPosition(h, result);
				SetConsoleTextAttribute(h, 3);
				cout << "Вы победили :0 :0 :0";
				result.Y++;
				cout << "Если хотите начать заново нажмите Пробел (Space) ";
				result.Y++;
				cout << "Если хотите выйти нажмите Escape ";
				result.Y++;
				int code = _getch();
				if (code == 32)
				{
					main();
				}
				else if (code == 27)
				{
					exit(0);
				}
				else
				{
					cout << "Такого выбора нет :(";
				}
				system("cls");
			}
		}
		else if (computerAnswer == "Paper")
		{
			while (true)
			{
				result.X = 45;
				result.Y = 18;
				SetConsoleCursorPosition(h, result);
				SetConsoleTextAttribute(h, 6);
				cout << "Вы проигали :(";
				result.Y++;
				Sleep(2000);
				SetConsoleTextAttribute(h, 3);
				cout << "Если хотите начать заново нажмите Пробел (Space) ";
				result.Y++;
				cout << "Если хотите выйти нажмите Escape ";
				result.Y++;
				int code = _getch();
				if (code == 32)
				{
					main();
				}
				else if (code == 27)
				{
					exit(0);
				}
				else
				{
					cout << "Такого выбора нет :(";
				}
				system("cls");
			}
		}
		else if (computerAnswer == "Scissors")
		{
			while (true)
			{
				result.X = 45;
				result.Y = 18;
				SetConsoleCursorPosition(h, result);
				SetConsoleTextAttribute(h, 3);
				cout << "Вы победили :0 :0 :0";
				result.Y++;
				cout << "Если хотите начать заново нажмите Пробел (Space) ";
				result.Y++;
				cout << "Если хотите выйти нажмите Escape ";
				result.Y++;
				int code = _getch();
				if (code == 32)
				{
					main();
				}
				else if (code == 27)
				{
					exit(0);
				}
				else
				{
					cout << "Такого выбора нет :(";
				}
				system("cls");
			}
		}
      }
	}
	else //если игрок тупой
	{
		cout << "Вы выбрали не соответствующую цифру, пожалуйста, НЕ НАДО ТАК";
		system("cls");
		Sleep(1000);
		main();
	}

	system("pause>NUL");
}
