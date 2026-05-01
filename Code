#include <iostream>
#include <fstream>
#include <string>

using namespace std;

void registerUser() {
    string username, password;

    cout << "\n--- Registration ---\n";
    cout << "Enter username: ";
    cin >> username;
    cout << "Enter password: ";
    cin >> password;

    ofstream file("users.txt", ios::app);

    if (!file) {
        cout << "Error opening file!\n";
        return;
    }

    file << username << " " << password << endl;
    file.close();

    cout << "Registration successful!\n";
}

bool loginUser() {
    string username, password;
    string fileUser, filePass;

    cout << "\n--- Login ---\n";
    cout << "Enter username: ";
    cin >> username;
    cout << "Enter password: ";
    cin >> password;

    ifstream file("users.txt");

    if (!file) {
        cout << "Error opening file!\n";
        return false;
    }

    while (file >> fileUser >> filePass) {
        cout << "Checking: " << fileUser << " " << filePass << endl; // DEBUG LINE

        if (fileUser == username && filePass == password) {
            file.close();
            return true;
        }
    }

    file.close();
    return false;
}

int main() {
    int choice;

    do {
        cout << "\n===== MENU =====\n";
        cout << "1. Register\n";
        cout << "2. Login\n";
        cout << "3. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                registerUser();
                break;
            case 2:
                if (loginUser()) {
                    cout << "Login successful! Welcome!\n";
                } else {
                    cout << "Invalid username or password.\n";
                }
                break;
            case 3:
                cout << "Exiting...\n";
                break;
            default:
                cout << "Invalid choice!\n";
        }
    } while (choice != 3);

    return 0;
}
