Set library is used to create sets in c++.
You can create set data type in such fashion:- 
`set<char> c = {'a','b','c'}`
you can mention the type of data you will input in set between `<>` 

printing set example:-
`#include <set>`
`using namespace std;`
`#include <iostream>`
`int main () {`
`set<char> c = {'a', 'b'};`
`set<int> a = {1,2,3,4,5,};`
`cout << "Set a: ";`
`for (int x : a) {`
`cout << x << " ";`
`}`
`cout << endl;`
`cout << "Set c: ";`
`for (char ch : c) {`
`cout << ch << " ";`
`}`
`cout << endl;`
`return 0;`
`}`

Functions:- 
- `s.insert(x);`  
    → Adds `x` to the set (only if not already present)
    
- `s.size();`  
    → Returns the number of elements in the set
    
- `s.count(x);`  
    → Returns 1 if `x` is present, otherwise 0
    
- `s.find(x);`  
    → Returns an iterator to `x`, or `s.end()` if not found
    
- `s.erase(x);`  
    → Removes `x` from the set if it exists
    
- `s.clear();`  
    → Removes all elements from the set
    
- `s.empty();`  
    → Returns `true` if the set is empty
    
- `*s.begin();`  
    → Returns the smallest element
    
- `*s.rbegin();`  
    → Returns the largest element (reverse begin)
    
- `for (auto x : s)`  
    → Loop through all elements in sorted order