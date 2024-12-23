#include <iostream>
#include <vector>
#include <stdexcept>
#include <cmath>
#include <cassert>
#include <limits> // Добавлено для std::numeric_limits

class Lab8 {
public:
    // Метод 1: Поиск минимального элемента массива положительных чисел
    static int findMinPositive(const std::vector<int>& arr) {
        if (arr.empty()) {
            throw std::invalid_argument("Массив пуст");
        }

        int min = std::numeric_limits<int>::max();
        bool found = false;

        for (int num : arr) {
            if (num > 0) {
                found = true;
                if (num < min) {
                    min = num;
                }
            }
        }

        if (!found) {
            throw std::runtime_error("В массиве нет положительных чисел");
        }

        return min;
    }

    // Метод 2: Расчет суммы элементов массива отрицательных чисел
    static int sumNegative(const std::vector<int>& arr) {
        int sum = 0;
        for (int num : arr) {
            if (num < 0) {
                sum += num;
            }
        }
        return sum;
    }

    // Метод 3: Расчет N-го элемента последовательности Фибоначчи
    static long long fibonacci(int n) {
        if (n < 0) {
            throw std::invalid_argument("N должно быть >= 0");
        }

        if (n == 0) return 0;
        if (n == 1) return 1;

        long long a = 0, b = 1;
        for (int i = 2; i <= n; ++i) {
            long long temp = a + b;
            a = b;
            b = temp;
        }

        return b;
    }

    // Метод 4: Расчет силы тока на участке цепи
    static double calculateCurrent(double voltage, double resistance) {
        if (resistance <= 0) {
            throw std::invalid_argument("Сопротивление должно быть > 0");
        }
        return voltage / resistance;
    }
};

void runTests() {
    try {
        std::cout << "Тесты для findMinPositive...\n";
        std::cout << "Test 1: " << (Lab8::findMinPositive({3, 7, 1, 9}) == 1 ? "Passed" : "Failed") << "\n";
        try {
            Lab8::findMinPositive({});
            std::cout << "Test 2: Failed\n";
        } catch (const std::invalid_argument&) {
            std::cout << "Test 2: Passed\n";
        }
        try {
            Lab8::findMinPositive({-1, -2, -3});
            std::cout << "Test 3: Failed\n";
        } catch (const std::runtime_error&) {
            std::cout << "Test 3: Passed\n";
        }

        std::cout << "\nТесты для sumNegative...\n";
        std::cout << "Test 4: " << (Lab8::sumNegative({-5, -3, -8}) == -16 ? "Passed" : "Failed") << "\n";
        std::cout << "Test 5: " << (Lab8::sumNegative({3, 7, 1}) == 0 ? "Passed" : "Failed") << "\n";

        std::cout << "\nТесты для fibonacci...\n";
        std::cout << "Test 6: " << (Lab8::fibonacci(0) == 0 ? "Passed" : "Failed") << "\n";
        std::cout << "Test 7: " << (Lab8::fibonacci(1) == 1 ? "Passed" : "Failed") << "\n";
        std::cout << "Test 8: " << (Lab8::fibonacci(10) == 55 ? "Passed" : "Failed") << "\n";
        try {
            Lab8::fibonacci(-1);
            std::cout << "Test 9: Failed\n";
        } catch (const std::invalid_argument&) {
            std::cout << "Test 9: Passed\n";
        }

        std::cout << "\nТесты для calculateCurrent...\n";
        std::cout << "Test 10: " << (std::abs(Lab8::calculateCurrent(10, 5) - 2.0) < 1e-9 ? "Passed" : "Failed") << "\n";
        try {
            Lab8::calculateCurrent(10, 0);
            std::cout << "Test 11: Failed\n";
        } catch (const std::invalid_argument&) {
            std::cout << "Test 11: Passed\n";
        }
    } catch (const std::exception& ex) {
        std::cerr << "Ошибка в тестах: " << ex.what() << std::endl;
    }
}

int main() {
    try {
        runTests();
        std::cout << "\nВсе тесты завершены." << std::endl;
    } catch (const std::exception& ex) {
        std::cerr << "Ошибка: " << ex.what() << std::endl;
    }

    return 0;
}
