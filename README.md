# CS112_A2_T1_S13_20220871
the best project i did so far
#include <iostream>
#include <vector>

int main() {
    std::vector<std::string> ls1;
    std::vector<std::string> ls2;

    while (true) {
        std::string x;
        std::cout << "Enter a value to list1: ";
        std::cin >> x;
        ls1.push_back(x);

        char conts;
        std::cout << "If you want to stop, press Y or y: ";
        std::cin >> conts;
        if (conts == 'y' || conts == 'Y') {
            break;
        }
    }

    while (true) {
        std::string x;
        std::cout << "Enter a value to list2: ";
        std::cin >> x;
        ls2.push_back(x);

        char conts;
        std::cout << "If you want to stop, press Y or y: ";
        std::cin >> conts;
        if (conts == 'y' || conts == 'Y') {
            break;
        }
    }

    bool flag = true;

    for (size_t i = 0; i < ls1.size(); ++i) {
        for (size_t j = 0; j < ls2.size(); ++j) {
            if (ls1[i] == ls2[j]) {
                break;
            } else if (ls1[i] != ls2[j] && j == ls2.size() - 1) {
                flag = false;
            }
        }
        if (!flag) {
            break;
        }
    }

    for (size_t i = 0; i < ls2.size(); ++i) {
        for (size_t j = 0; j < ls1.size(); ++j) {
            if (ls1[j] == ls2[i]) {
                break;
            } else if (ls1[j] != ls2[i] && j == ls1.size() - 1) {
                flag = false;
            }
        }
        if (!flag) {
            break;
        }
    }

    if (flag) {
        std::cout << "Same list" << std::endl;
    } else {
        std::cout << "Not Same" << std::endl;
    }

    return 0;
}
