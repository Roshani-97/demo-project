# demo-project
My first Git Repository
#include <iostream>
#include <cstdlib>  // for rand() and srand()
#include <ctime>    // for time()

using namespace std;

string getComputerChoice() {
    int randomNum = rand() % 3; // Generates a random number between 0 and 2
    if (randomNum == 0)
        return "Rock";
    else if (randomNum == 1)
        return "Paper";
    else
        return "Scissors";
}

string getUserChoice() {
    int choice;
    cout << "Enter your choice: \n1. Rock \n2. Paper \n3. Scissors\n";
    cin >> choice;

    switch (choice) {
        case 1:
            return "Rock";
        case 2:
            return "Paper";
        case 3:
            return "Scissors";
        default:
            cout << "Invalid choice, defaulting to Rock." << endl;
            return "Rock";
    }
}

void determineWinner(string userChoice, string computerChoice) {
    cout << "You chose: " << userChoice << endl;
    cout << "Computer chose: " << computerChoice << endl;

    if (userChoice == computerChoice) {
        cout << "It's a tie!" << endl;
    } else if ((userChoice == "Rock" && computerChoice == "Scissors") ||
               (userChoice == "Paper" && computerChoice == "Rock") ||
               (userChoice == "Scissors" && computerChoice == "Paper")) {
        cout << "You win!" << endl;
    } else {
        cout << "You lose!" << endl;
    }
}

int main() {
    srand(time(0)); // Seed the random number generator

    string userChoice = getUserChoice();
    string computerChoice = getComputerChoice();

    determineWinner(userChoice, computerChoice);

    return 0;
}

