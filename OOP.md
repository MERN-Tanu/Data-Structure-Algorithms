### OOP CODE-1

```
 #include <iostream>
using namespace std;

class Animal{
        public:
        Animal() {
                cout << "i am inside animal constructor" << endl;
        }
         void speak() {
                cout << "Speaking " << endl;
        }
};

class Dog: public Animal {
        public:
        Dog() {
                cout << "i am inside Dog constructor" << endl;
        }
        //override
        void speak() {
                cout << "barking" << endl;
        }
};

int main() {
//   Dog a;
//   a.speak();

        // Animal* a = new Animal();
        // a->speak();

        // Dog* a = new Dog();
        // a->speak();

        //UpCasting
        // Animal* a = new Dog();
        // a->speak();

        // //DownCasting
        // Dog* b = (Dog* )new Animal();
        // b->speak();

        Dog* a = (Dog*)new Animal();
        // Dog a;



  return 0;
}
```

### CODE-2

```
#include <iostream>
using namespace std;

int main() {
        int row = 5;
        int col = 3;

        int** arr = new int*[5];

        for(int i=0; i<row; i++) {
                arr[i] = new int[col];
        }

        //printing
        // for(int i=0; i<row; i++) {
        //         for(int j=0; j<col; j++) {
        //                 cout << arr[i][j] <<" ";
        //         }
        //         cout << endl;
        // }

        //de-allocate
        for(int i=0; i<row; i++) {
                delete []arr[i];
        }

        delete []arr;



  return 0;
}
```


### CODE-3

```
#include <iostream>
#include<vector>
using namespace std;

int main() {
        vector<vector<int> > arr(5, vector<int>(6,0));

        for(int i=0; i<5; i++) {
                for(int j=0; j<6; j++) {
                        cout << arr[i][j] << " ";
                }
    cout << endl;    }
  
  return 0;
}
```
