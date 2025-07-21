Setw is a cpp manipulator which exists in iomanip library. it is used to set width or give spaces when a text is displayed. 
eg:- 
`#include <iostream>`
`#include <iomanip>`
`using namespace std;`
`int main () {`
`int a = 4;`
`cout << setw(4) << a << endl;`
`}`

output:- `_____ 4`
