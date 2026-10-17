# check-_pass

### C++


#include <iostream>
#include <string>
using namespace std;

int main() {

    string secret = "GMBH|D0ef_Cb4t1d~";
    string input;
    cout << "Nhap mat khau: ";
    cin >> input;
    
    for(int i = 0; i < input.length(); i++){ 
      input[i] = input[i] + 1;
     
    }
  

    if(input == secret){
       cout << "Chinh xac! Ban da tim ra Flag.";
    
    }
    else{ 
        cout << "Sai mat khau!";
    }
  
    return 0;
}

### Python

secret = "GMBH|D0ef_Cb4t1d~"
for a in secret:
    print(chr(ord(a) - 1), end = '')

