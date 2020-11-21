#include <iostream>
#include <string>
#include <vector>
using namespace std;

class Animal {
public:
    Animal(); 
    Animal(const Animal& object); 
    Animal(const string animal, const string name, const int sex, const double price, const string aviary); 
    ~Animal();

    static int getCount() {
        return Count;
    }
    int getId() {
        return id;
    }
    void outData();

    void setAnimal(const string animal);
    void setName(const string name);
    void setSex(const int sex);
    void setPrice(const double price);
    void setAviary(const string aviary);
    void setData(const string animal, const string name, const int sex, const double price, const string aviary);
    
    string getAnimal();
    string getName();
    int getSex();
    double getPrice();
    string getAviary();

private:
    static int Count;
    int id;

    string animal;
    int sex;
    string name;
    double price;
    string aviary;
    string getnSex(const int sex);
};

int Animal::Count = 0;

Animal::Animal()
    : animal("none"), name("none"), sex(-1), price(-1), aviary("none") {
    Animal::Count++;
    id = Animal::Count;
}

Animal::Animal(const Animal& object) {
    this->animal = object.animal;
    this->name = object.name;
    this->sex = object.sex;
    this->price = object.price;
    this->aviary = object.aviary;
    Animal::Count++;
    id = Animal::Count;
}

Animal::Animal(const string animal, const string name, const int sex, const double price, const string aviary)
    : animal(animal), name(name), sex(sex), price(price), aviary(aviary) {
    Animal::Count++;
    id = Animal::Count;
}

Animal::~Animal() {
    Animal::Count--;
}

void Animal::outData() {
    cout << animal << " " << name << " " << getnSex(sex) << " " << price << aviary << endl;
}

void Animal::setAnimal(const string animal) {
    this->animal = animal;
}

void Animal::setName(const string name) {
    this->name = name;
}

void Animal::setSex(const int sex) {
    this->sex = sex;
}

void Animal::setPrice(const double price) {
    this->price = price;
}

void Animal::setAviary(const string aviary) {
    this->aviary = aviary;
}

void Animal::setData(const string animal, const string name, const int sex, const double price, const string aviary) {
    this->animal = animal;
    this->name = name;
    this->sex = sex;
    this->price = price;
    this->aviary = aviary; 
}

string Animal::getAnimal() {
    return animal;
}

string Animal::getName() {
    return name;
}

int Animal::getSex() {
    return sex;
}

double Animal::getPrice() {
    return price;
}

string Animal::getAviary() {
    return aviary;
}

string Animal::getnSex(const int sex) {
    switch (sex) {
    case 0: return "Female";
    case 1: return "Male";
    default: return "Unknown";
    }
}

void outMenu();
int inNum();

int main() {
    setlocale(LC_ALL, "rus");

    vector <Animal> vecAnimal;

    string cmd;
    string tanimal, tname, taviary;
    int tsex;
    double tprice;
   

    while (true) {
        outMenu();
        cout << ">";

        cin >> cmd;
        if (cmd == "q" || cmd == "quit") break;
        switch (atoi(cmd.c_str())) {
        case 1:
            if (!Animal::getCount()) {
                cout << "Information not found." << endl;
            }
            for (int i = 0; i < Animal::getCount(); i++) {
                cout << i + 1 << ") ";
                vecAnimal[i].outData();
            }
            break;
        case 2:
            if (!Animal::getCount()) {
                cout << "No animals found." << endl;
                break;
            }
            vecAnimal[inNum()].outData();
            break;
        case 3:
            cout << "Enter the type of animal: ";
            cin >> tanimal;
            cout << "Enter the name: ";
            cin >> tname;
            cout << "Enter ther floor (0/1): ";
            cin >> tsex;
            cout << "Enter the price: ";
            cin >> tprice;
            cout << "Enter the aviary of animal: ";
            cin >> taviary;
            vecAnimal.emplace_back(tanimal, tname, tsex, tprice, taviary);
            break;
        default:
            break;
        }
    }
    system("pause");
    return false;
}

void outMenu() {
    cout << "1) Displays information of all animals";
    cout << "\n2) Displays information of 1 animal special ";
    cout << "\n3) Add an animal";
    cout << "\n 'q' Exit.";
    cout << endl;
}

int inNum() {
    int number;
    while (true) {
        cout << "Enter number (1 - " << Animal::getCount() << "): ";
        cin >> number;
        if (number >= 1 && number <= Animal::getCount()) {
            return number - 1;
        }
        cout << "Error." << endl;
    }
}
