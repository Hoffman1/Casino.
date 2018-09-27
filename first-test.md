#include <iostream>
#include <cstdlib>
#include <string>
#include <ctime>
#include <locale>
using namespace std;
void drawLine(int n, char symbol);
int main()
{
setlocale(LC_ALL, "RUSSIAN");
srand(time(0));



int x, c, v;
char choice;
int a = 10000;
int  s, one;
drawLine(80, '_');
cout << "\n\n\n\n\t Здравствуйте, приветствуем вас в казино Голубая Лагуна \n\n\n\n" << endl;
drawLine(80, '_');

int g = 1;
do {
cout << "Ваш счёт:" <<endl;
drawLine(80, '=');
cout << a << "$ \n\n";
drawLine(80, '=');
do {

cout << "Сделайте пожалуйста ставку и нажмите Enter \n";
cin >> s ;
if(s > a)
cout << "Ваша ставка больше чем ваш счёт \n"
      << "\nRe-Enter data\n ";
}while (s > a);

do {
cout <<  " \n\n Чтобы крутить барабан нажмите 1 и затем Enter" <<endl;
cin >> one ;
if(one <= 0 || one >1)
cout << " 1 надо было нажать\ n"
           << "\nRe-Enter data\n " ;
} while(one <=0 || one > 1);



x = (rand () % 3) + 1;
c = (rand () % 3) + 1;
v = (rand () % 3) + 1;
cout << "xx" << x << "xx" << c << "xx" << v << "xx" << endl;
if (x == c && x == v ) {
        drawLine(80, '$');
cout << " Вы выиграли" << s * 15 <<"\n Поздравляем!!!";
drawLine(80, '$');
a = a + s * 15;
}
else {
cout << " Вы проиграли" << s <<" $ \n попрбуйте еще раз ";
a = a - s;}
cout << "Вы имеете:" << a << "$ \n";
if (a == 0){
cout << " Вы не имеете денежных средств";
        break;
}

cout << "\n\n--> Вы хотите играть ещё (y/n)? ";
cin >> choice;

}while(choice == 'y'|| choice == 'Y');


cout << "\n\n\n";

cout << "\n\nСписибо за игру. Ваш счёт:"<< a << "$ \n\n";

return 0;
}
void drawLine(int n, char symbol)
{
    for(int i = 0; i<n; i++)
    cout << symbol;
    cout << "\n" ;

}
