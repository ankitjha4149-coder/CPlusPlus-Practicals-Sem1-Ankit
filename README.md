All C++ practical programs for Semester 1

// 1. Print "Hello World" 5 times
#include <iostream>
using namespace std;
int main() {
    for(int i = 1; i <= 5; i++) {
        cout << "Hello World" << endl;
    }
    return 0;
}


// 2. Test whether a given number is Odd or Even
#include <iostream>
using namespace std;
int main() {
    int num;
    cout << "Enter a number: ";
    cin >> num;

    if(num % 2 == 0)
        cout << num << " is Even";
    else
        cout << num << " is Odd";
    return 0;
}


// 3. Print a simple pattern (right-angled triangle)
#include <iostream>
using namespace std;
int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for(int i = 1; i <= n; i++) {
        for(int j = 1; j <= i; j++) {
            cout << "* ";
        }
        cout << endl;
    }
    return 0;
}

// 4. Check if a string is Palindrome
#include <iostream>
#include <string>
using namespace std;
int main() {
    string str, rev = "";
    cout << "Enter a string: ";
    cin >> str;

    for(int i = str.length() - 1; i >= 0; i--) {
        rev += str[i];
    }

    if(str == rev)
        cout << "Palindrome String";
    else
        cout << "Not a Palindrome";
    return 0;
}
// 5. Simple Calculator using switch case
#include <iostream>
using namespace std;
int main() {
    double a, b;
    char op;
    cout << "Enter first number: ";
    cin >> a;
    cout << "Enter operator (+, -, *, /): ";
    cin >> op;
    cout << "Enter second number: ";
    cin >> b;

    switch(op) {
        case '+': cout << "Result = " << a + b; break;
        case '-': cout << "Result = " << a - b; break;
        case '*': cout << "Result = " << a * b; break;
        case '/': 
            if(b != 0)
                cout << "Result = " << a / b;
            else
                cout << "Division by zero error!";
            break;
        default: cout << "Invalid operator!";
    }
    return 0;
}
// 6. Print Prime Numbers in a Given Range
#include <iostream>
using namespace std;
int main() {
    int start, end;
    cout << "Enter range (start end): ";
    cin >> start >> end;

    cout << "Prime numbers between " << start << " and " << end << " are: ";

    for(int num = start; num <= end; num++) {
        bool isPrime = true;
        if(num < 2) continue;
        for(int i = 2; i*i <= num; i++) {
            if(num % i == 0) {
                isPrime = false;
                break;
            }
        }
        if(isPrime)
            cout << num << " ";
    }
    return 0;
}

// 7. Print Factors of a Number
#include <iostream>
using namespace std;
int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;

    cout << "Factors of " << n << " are: ";
    for(int i = 1; i <= n; i++) {
        if(n % i == 0)
            cout << i << " ";
    }
    return 0;
}

// 8. Find Roots of a Quadratic Equation
#include <iostream>
#include <cmath>
using namespace std;
int main() {
    double a, b, c, d, root1, root2;
    cout << "Enter coefficients a, b and c: ";
    cin >> a >> b >> c;

    d = b*b - 4*a*c;

    if(d > 0) {
        root1 = (-b + sqrt(d)) / (2*a);
        root2 = (-b - sqrt(d)) / (2*a);
        cout << "Roots are real and different.\n";
        cout << "Root 1 = " << root1 << ", Root 2 = " << root2;
    }
    else if(d == 0) {
        root1 = -b / (2*a);
        cout << "Roots are real and equal.\n";
        cout << "Root 1 = Root 2 = " << root1;
    }
    else {
        double realPart = -b / (2*a);
        double imagPart = sqrt(-d) / (2*a);
        cout << "Roots are complex and different.\n";
        cout << "Root 1 = " << realPart << " + " << imagPart << "i, ";
        cout << "Root 2 = " << realPart << " - " << imagPart << "i";
    }
    return 0;
}

// 9. Remove Duplicates from an Array
#include <iostream>
using namespace std;
int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;

    int arr[100];
    cout << "Enter array elements: ";
    for(int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    cout << "Array after removing duplicates: ";
    for(int i = 0; i < n; i++) {
        bool duplicate = false;
        for(int j = 0; j < i; j++) {
            if(arr[i] == arr[j]) {
                duplicate = true;
                break;
            }
        }
        if(!duplicate)
            cout << arr[i] << " ";
    }
    return 0;
}
