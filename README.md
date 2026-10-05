# My-task-3-
Student Management System using C++
#include <iostream>
using namespace std;

struct Student {
    string name, enrollment, branch;
    int semester;
    float marks;
};

Student s[100];
int n = 0;

void addStudent() {
  cout << "\nEnter Name: ";
  cin >> s[n].name;

  cout << "Enter Enrollment Number: ";
  cin >> s[n].enrollment;

  cout << "Enter Branch: ";
  cin >> s[n].branch;

  cout << "Enter Semester: ";
  cin >> s[n].semester;

  cout << "Enter Marks: ";
  cin >> s[n].marks;

  n++;
  cout << "Student added successfully!\n";
}

void displayStudents() {
    if (n == 0) {
        cout << "No students found.\n";
        return;
    }

    for (int i = 0; i < n; i++) {
        cout << "\nName: " << s[i].name;
        cout << "\nEnrollment: " << s[i].enrollment;
        cout << "\nBranch: " << s[i].branch;
        cout << "\nSemester: " << s[i].semester;
        cout << "\nMarks: " << s[i].marks << "\n";
    }
}

void searchStudent() {
    string enroll;
    cout << "Enter Enrollment Number: ";
    cin >> enroll;

    for (int i = 0; i < n; i++) {
        if (s[i].enrollment == enroll) {
            cout << "\nName: " << s[i].name;
            cout << "\nBranch: " << s[i].branch;
            cout << "\nSemester: " << s[i].semester;
            cout << "\nMarks: " << s[i].marks << "\n";
            return;
        }
    }

    cout << "Student not found.\n";
}

void updateStudent() {
    string enroll;
    cout << "Enter Enrollment Number: ";
    cin >> enroll;

    for (int i = 0; i < n; i++) {
        if (s[i].enrollment == enroll) {
            cout << "Enter New Marks: ";
            cin >> s[i].marks;

            cout << "Student updated successfully!\n";
            return;
        }
    }

    cout << "Student not found.\n";
}

void deleteStudent() {
    string enroll;
    cout << "Enter Enrollment Number: ";
    cin >> enroll;

    for (int i = 0; i < n; i++) {
        if (s[i].enrollment == enroll) {
            for (int j = i; j < n - 1; j++)
                s[j] = s[j + 1];

            n--;
            cout << "Student deleted successfully!\n";
            return;
        }
    }

    cout << "Student not found.\n";
}

int main() {
    int choice;

    do {
        cout << "\n\n--- Student Management System ---";
        cout << "\n1. Add Student";
        cout << "\n2. Display Students";
        cout << "\n3. Search Student";
        cout << "\n4. Update Student";
        cout << "\n5. Delete Student";
        cout << "\n6. Exit";
        cout << "\nEnter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: addStudent(); break;
            case 2: displayStudents(); break;
            case 3: searchStudent(); break;
            case 4: updateStudent(); break;
            case 5: deleteStudent(); break;
            case 6: cout << "Exiting..."; break;
            default: cout << "Invalid choice!";
        }
    } while (choice != 6);

    return 0;
}
