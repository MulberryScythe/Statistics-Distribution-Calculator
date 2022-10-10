#include <iostream>
#include <vector>

int main()
{
    std::cout << "Enter values here followed by 'E' or some character and hit ENTER: ";
    
    //Inputs values
    double input;
    std::vector<double> list;
    while (std::cin >> input) {
        list.push_back(input);
    }

    //Puts values in order from least to greatest
    for (int a = 0; a < list.size(); a++) {
        for (int i = 0; i < list.size() - 1; i++) {
            if (list[i] > list[i + 1]) {
                std::swap(list[i], list[i + 1]);
            }
        }
    }

    std::cout << "\n--------------------------\n";

    //Determines and prints range
    double range = list[list.size() - 1] - list[0];
    std::cout << "\nRange: " << range;

    //Determines and Prints Mean
    double listmean;
    double listsum = 0;
    for (int i = 0; i < list.size(); i++) {
        listsum = listsum + list[i];
    }
    listmean = listsum / list.size();
    std::cout << "\nMean: " << listmean << "\n";

    //Determines and Prints Median
    double listnumeven = (list[list.size() / 2] + list[(list.size() / 2) - 1]) / 2;
    double listnumodd = list[(list.size() / 2) + 0.5];
    if (list.size() % 2 == 0) {
        std::cout << "Median: " << listnumeven;
    }
    else {
        std::cout << "Median: " << listnumodd;
    }
    
    //Determines and Prints Mode(s)

        //Determines the frequency of each value and puts into a new string
        std::vector<double> modeone(list.size(), 0);
        for (int a = 0; a < list.size(); a++) {
            for (int i = 0; i < list.size(); i++) {
                if (list[a] == list[i]) {
                    modeone[a]++;
                }
            }
        }
    
        //Determines which frequency is the highest
        std::cout << "\n";
        double mostfre{};
        for (int a = 0; a < list.size(); a++) {
            for (int i = 0; i < list.size(); i++) {
                if (modeone[a] > modeone[i] && modeone[a] > mostfre) {
                    mostfre = modeone[a];
                }
            }
        }
        
        if (mostfre > 1) {
            
            //Determines which values in the origional list are the most frequent
            std::vector<double> modetwo;
            for (int i = 0; i < modeone.size(); i++) {
                if (modeone[i] == mostfre) {
                    modetwo.push_back(list[i]);
                }
            }

            //Deletes Extra Values
            for (int a = 0; a < modetwo.size(); a++) {
                for (int i = 0; i < modetwo.size(); i++) {
                    if (modetwo[a] == modetwo[i]) {
                        modetwo.erase(modetwo.begin() + i);
                    }
                }
            }

            //Prints mode(s)
            std::cout << "Mode(s): ";
            for (int i = 0; i < modetwo.size(); i++) {
                if (i < modetwo.size() - 1) {
                    std::cout << modetwo[i] << ", ";
                }
                else {
                    std::cout << modetwo[i];
                }
            }
            std::cout << "\n";

        }
        else {
            std::cout << "Mode(s): N/A\n";
        }

// THANK GOD THIS IS OVER

    //Determines and prints mean absolute deviation
    std::vector<double> MAD;
    for (int i = 0; i < list.size(); i++) {
        if (list[i] - listmean < 0) {
            MAD.push_back((list[i] - listmean) * -1);
        }
        else {
            MAD.push_back(list[i] - listmean);
        }
    }
    double MADsum = 0;
    for (int i = 0; i < MAD.size(); i++) {
        MADsum = MADsum + MAD[i];
    }
    std::cout << "Mean Absolute Deviation: " << MADsum / list.size() << "\n";

    std::vector<double> SD;
    double a;
    for (int i = 0; i < list.size(); i++) {
        a = list[i] - listmean;
        SD.push_back(pow(a, 2));
    }
    double SDsum = 0;
    for (int i = 0; i < list.size(); i++) {
        SDsum = SDsum + SD[i];
    }
    std::cout << "Standard Deviation (+/-): " << sqrt(SDsum / list.size()) << "\n\n";
    std::cout << "--------------------------\n";
}
