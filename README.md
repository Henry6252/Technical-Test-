// Write a C++ program that prints the numbers from 1 to 100. For multiples of 3, print "Fizz";
// for multiples of 5, print "Buzz"; and for numbers that are multiples of both 3 and 5, print "FizzBuzz"
#include <iostream>

int main() {
    for (int i = 1; i <= 100; ++i) {
        if (i % 3 == 0 && i % 5 == 0) {
            std::cout << "FizzBuzz ";
        } else if (i % 3 == 0) {
            std::cout << "Fizz ";
        } else if (i % 5 == 0) {
            std::cout << "Buzz ";
        } else {
            std::cout << i << " ";
        }
    }
    std::cout << std::endl;
    return 0;
}




// Program to generate the Fibonacci sequence up to 100

#include <iostream>

int main() {
    int num1 = 0, num2 = 1, nextTerm = 0;

    std::cout << "Fibonacci Series up to 100: " << std::endl;

    while (nextTerm <= 100) {
        std::cout << nextTerm << " ";
        num1 = num2;
        num2 = nextTerm;
        nextTerm = num1 + num2;
    }

    return 0;
}


#include <iostream>

// Write a program that takes an integer as input and returns true if the input is a power of two

bool isPowerOfTwo(int n) {
    // A power of two has only one bit set in its binary representation.
    // So, if we bitwise AND n with n - 1, it should result in 0 if n is a power of two.
    return (n > 0) && ((n & (n - 1)) == 0);
}

int main() {
    int num;
    std::cout << "Enter an integer: ";
    std::cin >> num;

    if (isPowerOfTwo(num)) {
        std::cout << num << " is a power of two." << std::endl;
    } else {
        std::cout << num << " is not a power of two." << std::endl;
    }

    return 0;
}



#include <iostream>
#include <string>
#include <cctype> // for std::toupper

// Write a C++ program that accepts a string as input, capitalizes the first letter of each word in the string, and then returns the result string.

std::string capitalizeWords(const std::string& input) {
    std::string result = input;
    bool capitalizeNext = true;

    for (char& c : result) {
        if (std::isspace(c)) {
            capitalizeNext = true;
        } else if (capitalizeNext) {
            c = std::toupper(c);
            capitalizeNext = false;
        }
    }

    return result;
}

int main() {
    std::string input;
    std::cout << "Enter a string: ";
    std::getline(std::cin, input);

    std::string capitalized = capitalizeWords(input);

    std::cout << "Capitalized string: " << capitalized << std::endl;

    return 0;
}



#include <iostream>

// Function to reverse the digits of an integer
int reverseInteger(int num) {
    int reversed = 0;
    while (num != 0) {
        int digit = num % 10; // Extract the last digit of the number
        reversed = reversed * 10 + digit; // Add the digit to the reversed number
        num /= 10; // Remove the last digit from the number
    }
    return reversed; // Return the reversed number
}

int main() {
    int num;
    std::cout << "Enter an integer: ";
    std::cin >> num; // Read an integer from the user
    int reversedNum = reverseInteger(num); // Reverse the digits of the input integer
    std::cout << "Reversed integer: " << reversedNum << std::endl; // Print the reversed integer
    return 0;
}


#include <iostream>
#include <string>
#include <cctype>

// Function to count the number of vowels in a sentence
int countVowels(const std::string& sentence) {
    int vowelCount = 0;
    // Iterate through each character in the sentence
    for (char ch : sentence) {
        // Convert character to lowercase
        char lowercaseCh = std::tolower(ch);
        // Check if the character is a vowel
        if (lowercaseCh == 'a' || lowercaseCh == 'e' || lowercaseCh == 'i' ||
            lowercaseCh == 'o' || lowercaseCh == 'u') {
            vowelCount++; // Increment the vowel count
        }
    }
    return vowelCount; // Return the total count of vowels in the sentence
}

int main() {
    std::string sentence;
    std::cout << "Enter a sentence: ";
    std::getline(std::cin, sentence); // Read a sentence from the user
    int numVowels = countVowels(sentence); // Count the number of vowels
    std::cout << "Number of vowels in the sentence: " << numVowels << std::endl; // Print the count
    return 0;
}
