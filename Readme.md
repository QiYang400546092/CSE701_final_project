## <center> Final Project Instructions

### 1.  instructions of calss and functions
In this project, I have three files including "bigint hpp", "demon.cpp" and this "Readme.md".

"bigint.hpp" has a class named "bigint", I define all the functions in this head file, the details are following:

#### 1.1 functions statements
<span style="color:red;">"bigint()"</span> : initial function, the default is "0";

<span style="color:red;">"bigint(const string)"</span> : define an integer with an input string;

<span style="color:red;">"bool is_negative() const"</span> : test if an integer is negative;

<span style="color:red;">"string get_integer() const"</span> : get the string of an integer;

<span style="color:red;">"string get_pure_figures() const"</span> : get the string without sign of an integer;

<span style="color:red;">"void set(const string)"</span> : test if input is an integer, detect the numbers of invalid "0" and give a new string to existed value;

<span style="color:red;">"string two_positives_max_minus_min(const bigint min_number) const"</span> : a bigger integer minus a smaller integer, return a string;

<span style="color:red;">"string two_positives_max_plus_min(const bigint min_number) const"</span> : a bigger integer plus a smaller integer, return a string;

<span style="color:red;">"bigint& operator +=(const bigint&)"</span> : function "+=" ;

<span style="color:red;">"bigint& operator -=(const bigint&)"</span> : function "-=";

<span style="color:red;">"bigint& operator *=(const bigint&)"</span> : function "*=";

<span style="color:red;">"bigint& operator /=(const bigint&)"</span> : function "/=";

<span style="color:red;">"bigint& operator =(const bigint&)"</span> : give a new integer to an existed integer;

<span style="color:red;">"bigint operator -() const"</span> : add "-" or delete "-";

<span style="color:red;">"friend ostream& operator<<(ostream&, const bigint&)"</span> : overload "<<";

<span style="color:red;">"friend bool operator >(bigint, const bigint&)"</span> : test if an integer ">" another integer;

<span style="color:red;">"friend bool operator >=(bigint, const bigint&)"</span> : test if an integer ">=" another integer;

<span style="color:red;">"friend bool operator ==(bigint, const bigint&)"</span> : test if an integer "==" another integer;

<span style="color:red;">"friend bool operator !=(bigint, const bigint&)"</span> : test if an integer "!=" another integer;

<span style="color:red;">"friend bool operator <(bigint, const bigint&)"</span> : test if an integer "<>" another integer;

<span style="color:red;">"friend bool operator <=(bigint, const bigint&)"</span> : test if an integer "<=" another integer;

<span style="color:red;">"bigint operator +(bigint first_number, const bigint& second_number)"</span> : add one integer to another integer and store the result in a new integer, return this new integer;

<span style="color:red;">"bigint operator -(bigint first_number, const bigint& second_number)"</span> : substract one integer by another integer and store the result in a new integer, return this new integer;

<span style="color:red;">"bigint operator *(bigint first_number, const bigint& second_number)"</span> : multiple one integer with another integer and store the result in a new integer, return this new integer;

<span style="color:red;">"bigint operator /(bigint first_number, const bigint& second_number)"</span> : divide one integer by another integer and store the result in a new integer, return this new integer;

#### 1.2 details of main functions and examples to demonstrate them

">" : I use "for" loop to compare two integers. for example, "123" > "120": at first, I test the sign and length ,they are same so that I can start "for" loop, then I compare "1" with "1", then I compare "2" with "2", after that I compare "3" with "0", here I break the loop because they are different. 

"<" : "123" < "120" -> "120" > "123";

"==" : "123" == "120" ->   ! "123" > "120" and ! "123" < "120";

">=" : combine ">" and "==";

"<=" : combine "<" and "==";

"!=" : "123" != "120" -> ! "123" == "120";

"+=" : I use "for" loop to add integers. for example, "123" += "20", they are not negative, so I also use function "two_positives_max_plus_min(const bigint min_number) const" to add two non-negative integers; "123" += "-20" will be operated by function "two_positives_max_minus_min(const bigint min_number) const"; "-123" += "20" -> "-" ("123" += "-20"), and
"-123" += "-20" -> "-" ("123" += "20");

"-=" : I only consider the second integer's sign. for example, "123" -= "-20" -> "123" += "20",  and "123" -= "20" -> "123" += "-20";

"*=" : I only process strings which needs a good algorithm, I find that if I want compute "12"*="21", I should use "12"*"1" + "120" * "2". so after every loop, I will add a "0" behind "12". for example, "156842" *= "235", I firstly compute "156842"+="156842" for 5 times as A, secondly compute "1568420"+="1568420" for 3 times as B, then I calculate "15684200"+="15684200" for 2 times as C. Finally A+=B, then A+=C, I get the result. This is very fast by only operating strings;

"/=" : This is very complex, I remember the dividing numbers lessons I learned whwen I was in primary school, it process the calculation by times of substracting and remianing number. For instance, "12463" /= "2", firstly I use "1"-="2", I know it cannot substract directly ,so result is "0", and remaining is "1", secondly the number I use combine remaining and the second figure, so I use "12"-=2, I can do that 6 times, so the result now is "06" and remaining is "0", thirdly I use "04"-="2", so the result now is "062" and remaining is "0", forthly I use "06"-= "2", so the result now is "0623" and remaining is "0", finally I use "03"-="2", so the result is "06231" and remaining is "1". Now the loop is over,so the final result string is "06231", because of definition of "set()", the invalid "0" will be deleted, so the output result is "6231";

"+" : using "+=";

"-" : using "-=";

"*" : using "*=";

"/" : using "/=";

"- ("1" -> "-1")" : directly using function "is_negative()" to know if I should add "-" or delete "-"; 

## 2.  Test (demon.cpp)
I have add too many details in my demon.cpp, you can check it and directly use it.
