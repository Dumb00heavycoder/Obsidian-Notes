#Include <iostream> 
using namespace std;

int main () {
	int marks[4]= {0,23,44,8,};
	int *P = &marks;
	cout <<  P << endl;
	cout << *P << endl;
	cout << *(P+1) << endl;
	cout << *(P+2)<< endl;
	return 0;
}