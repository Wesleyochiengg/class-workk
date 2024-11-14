#include <iostream>
#include <string>

class Person {
protected:
    std::string name;

public:
    void setName(std::string n) {
        name = n;
    }

    std::string getName() {
        return name;
    }
};

class Student : public Person {
private:
    int studentID;

public:
    Student(std::string n, int id) {
        setName(n);
        studentID = id;
    }

    int getStudentID() {
        return studentID;
    }

    std::string getStudent() {
        return getName() + " (ID: " + std::to_string(studentID) + ")";
    }
};

class GraduateStudent : public Student {
private:
    std::string researchTopic;

public:
    GraduateStudent(std::string n, int id, std::string topic) : Student(n, id) {
        researchTopic = topic;
    }

    std::string getResearchTopic() {
        return researchTopic;
    }
};

int main() {
    Student student("John", 1001);
    GraduateStudent gradStudent("Alice", 2001, "Artificial Intelligence");

    std::cout << "Student: " << student.getStudent() << std::endl;
    std::cout << "Graduate Student: " << gradStudent.getStudent() 
              << ", Research Topic: " << gradStudent.getResearchTopic() << std::endl;

    return 0;
}
