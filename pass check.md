# I. BÀI LÀM BẰNG C++

### Bước 1: Tạo file và thêm thư viện

\-Tạo và đặt tên file C++ trong VScode

\-Sử dụng các thư viện:

\#include <iostream>

\#include <string>

using namespace std;

### Bước 2: Sử dụng chuỗi

\-Tạo biến chuỗi.

string secret = "GMBH|D0ef\_Cb4t1d\~";

string input;

\-string là chuỗi.

\-secret là một chuỗi được gán giá trị sẵn.

### Bước 3: Sử dụng cout và cin

\-Dùng cout để in chữ "nhập mật khẩu"và cin đê cho người

dùng nhập:

cout << "Nhap mat khau: ";

cin >> input;

### Bước 4: Sử dụng lệnh lặp, chiều dài chuỗi, chuỗi truy cập

### và toán từ gán (For loop, string length, access string, operator)

\-Dòng lệnh như sau:

for(int i = 0; i < input.length(); i++)

{

input\[i] = input\[i] + 1;

}

##For loop: for ở đây là lệnh lặp trong C++ For loop, for ở

đây có vai trò khi bạn biết chính xác mình muốn lặp qua

một khối bao nhiêu lần mã, sử dụng for vòng lặp thay vì một

while vòng lặp.

+Cú pháp

for (statement 1; statement 2; statement 3){   }.



* Tuyên bố 1 được thực thi (một lần) trước khi khối mã được thực thi.



* Tuyên bố 2 Xác định điều kiện để thực thi khối mã.



* Tuyên bố 3 được thực thi (mỗi lần) sau khi khối mã đã được thực thi xong.



\-Đầu tiên khởi tạo i = 0 ở statement 1 vì nó bắt đầu từ kí tự đầu tiên trong bảng ASCII tức là kí tự "NUL".Nếu cho i = 1 tức i = 0 sẽ không có, ví dụ cho một chuỗi "HOANG" thì:

Ký tự	H	O	A      N     G
Chỉ số	0	1	2      3     4
==> Vì vậy cần xuất phát từ 0.


\-Tiếp đến là statement 2, i < input.length() là điều kiện lặp, i nhỏ hơn độ dài chuỗi. Nếu i còn nhỏ hơn độ dài chuỗi thì tiếp tục lặp:

+Nếu đúng thì chạy tiếp, sai thì dừng lại.

+i là biến đếm, input.length() là độ dài, tổng số kí tự của chuỗi. Ví dụ chạy input = "abcd" thì tức độ dài bằng 3. Khi đó i= 0, 1, 2; vòng lặp chạy 3 lần thì dừng lại ==> i phải nhỏ hơn độ dài chuỗi, mà GMBH|D0ef_Cb4t1d~ có 17 kí tự nên i chỉ chạy đên i = 16 là dừng.
*) length() cho biết có bao nhiêu ký tự,(5 đối với HOANG) ==> i < 5. tức i lúc này chạy từ 0 đến 4 thì dừng
\-Cuối cùng là i++: tăng đơn vị thêm 1, là statement 3. i = 0, đi qua statement 2, nếu đủ điều kiện thì đến statement 3, tăng thêm 1 đơn vị rồi quay lại statement 1, lặp lại đến khi nào nó không thỏa mãn statement 2 nữa thì dừng lại

##Toán tử
Giả sử i = 0 và input = "HOANG".

Đọc: lấy input[0], được ký tự 'H'.
Tính: 'H' thực chất là số 72, cộng 1 thành 73.
Ghi: đưa 73 trở lại vị trí input[0]. Vì input[i] là kiểu char, số 73 được hiểu là ký tự 'I'.

Sau đó khi xong vòng 1 thì ta sẽ có chuỗi "IOANG", vòng 'for' lặp lại dòng này với i = 1 , i = 2,.. i = 4. để ra "IPBOH".
Có thể sử dụng cách viết khác: 

input[i] = input[i] + 1;
input[i] += 1;
input[i]++;

-Tương tự với chuỗi "GMBH|D0ef_Cb4t1d~" khi nhập vào dòng lệnh: (tìm pass)

 for(int i = 0; i < input.length(); i++){ 
      input[i] = input[i] + 1;
     
    }
    cout << input;


-Tuy nhiên khi in dòng lệnh "GMBH|D0ef_Cb4t1d~" vào thì ra "HNCI}E1fg`Dc5u2e" chỉ có 16 kí tự chứ không phải 17 nên sai.

Khi in ra sẽ bị thiếu mất 1 kí tự cuối, tức "~" bị thiếu, do bảng ASCII chỉ đến 126 kí hiệu có thể in ra trên terminal nên khi đó ta sử dụng lệnh trừ. Ngoài ra, vì chương trình cộng 1 rồi mới so sánh với secret, nên ta dùng phép trừ để khôi phục mật khẩu gốc:

for(int i = 0; i < input.length(); i++){ 
      input[i] = input[i] - 1;
     
    }
    cout << input;

Khi đó nhập "GMBH|D0ef_Cb4t1d~" thì ta sẽ có chuỗi pass là "FLAG{C/de^Ba3s0c}".

### Bước 5: IF & ELSE:
-Để nhập chuỗi mới tạo ra với chuỗi secret mà máy trả true thì ta cần sử dụng toán tử so sánh bằng (==) :


    if(input == secret){
       cout << "Chinh xac! Ban da tim ra Flag.";
    
    }
    else{ 
        cout << "Sai mat khau!";
    }
-Tức nếu cái input người dùng nhập vào là pass "FLAG{C/de^Ba3s0c}" thì máy sẽ báo Mat khau chinh xac, input lúc này cộng 1 cả chuỗi để từ "FLAG{C/de^Ba3s0c}" thành "GMBH|D0ef_Cb4t1d~".
Vậy chương trình C++ mà ta có là: 

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






# II. Bài làm bằng python (solve.py)
### Bước 1: Khai báo biến secret:
secret = "GMBH|D0ef_Cb4t1d~"

###Bước 2: Sử dụng lệnh for loop:
for a in secret:

-Ở đây secret là chuỗi được duyệt. Vòng for lấy lần lượt từng ký tự của secret từ trái sang phải, gán vào biến a. Chuỗi có 17 ký tự nên vòng lặp chạy 17 lần.

-Vậy nên khi thử in ra:

for a in secret:
    print(a)

-Thì kết quả sẽ là:
G
M
B
H
|
D
0
e
f
_
C
b
4
t
1
d
~

-Khi đó ta sử dụng lệnh end = ' ' để không bị cách dòng:

for a in secret:
    
    print(a, end = ' ')

Output:
G M B H | D 0 e f _ C b 4 t 1 d ~ 

###Bước 3: Sử dụng ord() và chr()
-Ta sử dụng ord() để biến chuỗi kí tự từ kí tự về số tương đương trong bảng mã ASCII. Khi đó kết quả sẽ là:

for a in secret:
    print(ord(a), end = ' ')

Output: 71 77 66 72 124 68 48 101 102 95 67 98 52 116 49 100 126 

-Vì đề bài yêu cầu chuyển về kí tự nên sử dụng chr():

for a in secret:
    
    print(chr(ord(a)), end = ' ')

-Chương trình C++ cộng 1 vào mã ASCII của từng ký tự rồi so với secret, nên secret là mật khẩu thật đã bị dịch lên 1. Để khôi phục, ta làm ngược lại: duyệt từng ký tự a của secret, dùng ord(a) lấy mã ASCII, trừ 1, rồi dùng chr() đổi về ký tự. Mà nếu đi theo chiều cộng thì ký tự ~ (126) thành 127, là ký tự không in được, nên cũng cho thấy chiều đúng là trừ:

secret = "GMBH|D0ef_Cb4t1d~"
for a in secret:
    print(chr(ord(a) - 1), end = '')

Output: FLAG{C/de^Ba3s0c}
