#include <iostream>
#include <algorithm>
#include <string.h>
using namespace std;

int const cap = 10;//	Capacity List
class list {
	
	int size;//		list Size
	int arr[cap];
	
public:
	list() {size = 0;}//	Constructor
	//		8) Methods List 	//
	bool set(int index, int val);//	1)Change Elemnts
	int get(int index);//	2)Return Value By Index
	bool remove(int index);//	3)Remove Elemnts By Index
	int Size();//	4)Return Size
	bool insert(int index, int val);// 5)Enter The Value By Index
	void pushpack(int val);//	6)Add Element
	void print();//	7)Print All Elements in size
	void Start_Program();//		8)Option
};
int list::get(int index) {
	int ind = index-1;
	if (ind >= cap || ind < 0 || ind >= size)
	{
		cout << "Not Found " ;
		return -1;
	}
	 return arr[ind];
}

bool list::insert(int index, int val) {
	int ind = index - 1;
	if (ind >= cap || ind<0 || ind>=size)return false;
	for (int pos = size - 1; pos >= ind; pos--)
		arr[pos+1] = arr[pos ];
	arr[ind] = val;
	size++;
	return true;
}
bool list::set(int index, int val) {
	int ind = index - 1;
	if (ind >= cap || ind < 0 || ind >= size)return false;
	arr[ind] = val;
	return true;
}
bool list::remove(int index) {
	int ind = index - 1;
	if (ind >= cap || ind < 0 || ind >= size)return false;
	for (int pos = ind; pos < size; pos++)
		arr[pos] = arr[pos + 1];
	size--;
	return true;
}
void list::pushpack(int val) {
	arr[size] = val;
	if (size == cap)return;
	size++;
}
int list::Size() {
	return size;
}
void list::print() {
	for (int x = 0; x < size; x++) {
		cout << arr[x];
	}
}
void list::Start_Program() {
	cout << "My List\nWhat Do you Need ?\n1)Add Element\n2)Remove Element\n3)Change Element\n4)Instert Elemnts";
	cout << endl << "5)Size List\n6)Show The Elements\n7)Get The Elemnt\n8)Exit Program\n";
	cout << "\nEnter The Number : ";
	class list l1;
	int ind, val;
	char ele ;
	bool check = false;

		while (check !=true) {
			cin >> ele;
			
			if (ele == '8' ) {

				check = true;
			}
			else if (ele == '1') {
				cout << "Enter The Elements : ";
				cin >> val;
				l1.pushpack(val);
			}
			else if (ele == '2') {
				cout << "Enter The endex : ";
				cin >> ind;
				l1.remove(ind);
			}
			else if (ele == '3') {
				cout << "Enter The index : ";
				cin >> ind;
				cout << "Enter The Elemnts : ";
				cin >> val;
				l1.set(ind, val);
			}
			else if (ele == '4') {
				cout << "Enter The index : ";
				cin >> ind;
				cout << "Enter The Elemnts : ";
				cin >> val;
				l1.insert(ind, val);
			}
			else if (ele == '5')cout << l1.Size();
			else if (ele == '6') l1.print();
			else if (ele == '7') {
				cout << "Enter The index : ";
				cin >> ind;
				cout << l1.get(ind);
			}
			if (ele != '8' )
			cout << "\nEnter The Number : ";

		}
	}
int main()
{	
	
	list l2;
	l2.Start_Program();
}