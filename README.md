# Final-Project-Task-4

# Task 4

#include <iostream>
#include <string>
#include <unordered_map>

char firstNonRepeatingChar(const std::string& s) {
    std::unordered_map<char, int> count;
    //count occurrences on the first pass through
    for (char c : s) {
        count[c]++;
    }
    // Second pass: find first unique
    for (char c : s) {
        if (count[c] == 1) {
            return c;
        }
    }
    return ' '; // Return null char if none found
}

int main() {
    std::string s = "swiss";
    char result = firstNonRepeatingChar(s);
    if (result != ' ') {
        std::cout << "First non-repeating character: " << result << std::endl;
    } else {
        std::cout << "No non-repeating character found." << std::endl;
    }
    return 0;
}
