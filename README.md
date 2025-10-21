
#include <string>
#include <sstream>
#include <cstdlib>
#include <ctime>

using namespace std;

// Function 1: Decimal to Binary
string decimalToBinary(int n) {
    if (n == 0) return "0";
    string binary = "";
    while (n > 0) {
        binary = (n % 2 == 0 ? "0" : "1") + binary;
        n /= 2;
    }
    return binary;
}

// Function 2: Binary to Decimal
int binaryToDecimal(const string& binary) {
    int decimal = 0;
    for (char c : binary)
        decimal = decimal * 2 + (c - '0');
    return decimal;
}

// Function 3: Decimal to Hexadecimal
string decimalToHex(int n) {
    stringstream ss;
    ss << hex << uppercase << n;
    return ss.str();
}

// Function 4: Hexadecimal to Decimal
int hexToDecimal(const string& hexStr) {
    int decimal;
    stringstream ss;
    ss << hex << hexStr;
    ss >> decimal;
    return decimal;
}

// Demo: Generate random number and convert to binary
void demo() {
    srand(time(0));
    int n = rand() % 100; // Random number between 0 and 99
    cout << "\nRandom Number: " << n << endl;
    cout << "Binary: " << decimalToBinary(n) << endl;
}

// Main Menu
int main() {
    int choice;
    do {
        cout << "\n=== NUMBER CONVERTER MENU ===\n";
        cout << "1. Convert Decimal to Binary\n";
        cout << "2. Convert Binary to Decimal\n";
        cout << "3. Convert Decimal to Hexadecimal\n";
        cout << "4. Convert Hexadecimal to Decimal\n";
        cout << "5. Demo (Random Number to Binary)\n";
        cout << "6. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        if (choice == 1) {
            int n;
            cout << "Enter decimal number: ";
            cin >> n;
            cout << "Binary: " << decimalToBinary(n) << endl;
        }
        else if (choice == 2) {
            string b;
            cout << "Enter binary number: ";
            cin >> b;
            cout << "Decimal: " << binaryToDecimal(b) << endl;
        }
        else if (choice == 3) {
            int n;
            cout << "Enter decimal number: ";
            cin >> n;
            cout << "Hexadecimal: " << decimalToHex(n) << endl;
        }
        else if (choice == 4) {
            string h;
            cout << "Enter hexadecimal number: ";
            cin >> h;
            cout << "Decimal: " << hexToDecimal(h) << endl;
        }
        else if (choice == 5) {
            demo();
        }
        else if (choice == 6) {
            cout << "Exiting program. Goodbye!\n";
        }
        else {
            cout << "Invalid choice! Try again.\n";
        }

    } while (choice != 6);

    return 0;
}
