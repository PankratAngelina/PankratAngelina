#include <iostream>
#include <vector>
#include <random>

// Функция для вычисления суммы отрицательных чисел в массиве
int sumOfNegatives(const std::vector<int>& arr) {
    int sum = 0;
    for (int num : arr) {
        if (num < 0) {
            sum += num;
        }
    }
    return sum;
}

int main() {
    int size;
    std::cout << "Enter the size of the array: ";
    std::cin >> size;

    std::vector<int> array(size);
    std::random_device rd;
    std::mt19937 gen(rd());
    std::uniform_int_distribution<int> dis(-100, 100);

    for (int i = 0; i < size; ++i) {
        array[i] = dis(gen);
    }

    int sumNegatives = sumOfNegatives(array);
    std::cout << "Sum of negative numbers in the array: " << sumNegatives << std::endl;

    return 0;
}
