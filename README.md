#include <iostream>
#include <vector>
#include <algorithm>

class Calculator {
public:
    int floor(double number) {
        return static_cast<int>(number);
    }

    int add(int a, int b) {
        return a + b;
    }

    double max1(double a, double b) {
        return (a > b) ? a : b;
    }

    bool find1(const std::string& str, char c) {
        return str.find(c) != std::string::npos;
    }

    int max2(const std::vector<int>& arr) {
        if (arr.empty()) {
            throw std::invalid_argument("The array is empty.");
        }
        return *std::max_element(arr.begin(), arr.end());
    }
};

int main() {
    Calculator calc;
    std::cout << "Floor of 5.7: " << calc.floor(5.7) << std::endl;
    std::cout << "Sum of 10 and 20: " << calc.add(10, 20) << std::endl;
    std::cout << "Max of 4.5 and 7.3: " << calc.max1(4.5, 7.3) << std::endl;
    std::cout << "Character 'a' in 'hello': " << (calc.find1("hello", 'a') ? "true" : "false") << std::endl;
    std::vector<int> nums = {1, 5, 9, 3, 7};
    std::cout << "Max in array {1, 5, 9, 3, 7}: " << calc.max2(nums) << std::endl;
    return 0;
}
