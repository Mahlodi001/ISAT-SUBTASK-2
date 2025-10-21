# ISAT-SUBTASK-2
#include &lt;iostream> #include &lt;string> #include &lt;sstream> #include &lt;cstdlib> #include &lt;ctime>  using namespace std;  // Function 1: Decimal to Binary string decimalToBinary(int n) {     if (n == 0) return "0";     string binary = "";     while (n > 0) {         binary = (n % 2 == 0 ? "0" : "1") + binary;         n /= 2;     }     
