#include <iostream>

using namespace std;

// Node structure for circular linked list
struct Node {
    int data;
    Node* next;
    Node(int val) : data(val), next(nullptr) {}
};

class CircularLinkedList {
private:
    Node* head;

public:
    CircularLinkedList() : head(nullptr) {}

    // Function to insert a node at the beginning of the list
    void insertAtBeginning(int val) {
        Node* newNode = new Node(val);
        if (!head) {
            newNode->next = newNode;
            head = newNode;
        } else {
            Node* tail = head;
            while (tail->next != head) {
                tail = tail->next;
            }
            newNode->next = head;
            tail->next = newNode;
            head = newNode;
        }
    }

    // Function to insert a node at the end of the list
    void insertAtEnd(int val) {
        Node* newNode = new Node(val);
        if (!head) {
            newNode->next = newNode;
            head = newNode;
        } else {
            Node* tail = head;
            while (tail->next != head) {
                tail = tail->next;
            }
            newNode->next = head;
            tail->next = newNode;
        }
    }

    // Function to delete a node by a given value
    void deleteByValue(int val) {
        if (!head) {
            cout << "List is empty. Nothing to delete." << endl;
            return;
        }

        Node* current = head;
        Node* prev = nullptr;

        do {
            if (current->data == val) {
                if (current == head) {
                    Node* tail = head;
                    while (tail->next != head) {
                        tail = tail->next;
                    }
                    head = head->next;
                    tail->next = head;
                } else {
                    prev->next = current->next;
                }
                delete current;
                cout << "Deleted " << val << " from the list." << endl;
                return;
            }
            prev = current;
            current = current->next;
        } while (current != head);

        cout << "Value not found in the list." << endl;
    }

    // Function to traverse and display the list (forward)
    void traverseAndDisplay() {
        if (!head) {
            cout << "List is empty." << endl;
            return;
        }

        Node* current = head;
        do {
            cout << current->data << " ";
            current = current->next;
        } while (current != head);
        cout << endl;
    }

    // Function to search for a specific value in the list
    bool search(int val) {
        if (!head) {
            return false;
        }

        Node* current = head;
        do {
            if (current->data == val) {
                return true;
            }
            current = current->next;
        } while (current != head);

        return false;
    }
};

int main() {
    CircularLinkedList list;
    int choice, value;

    do {
        cout << "Menu:" << endl;
        cout << "1. Insert at the beginning" << endl;
        cout << "2. Insert at the end" << endl;
        cout << "3. Delete by value" << endl;
        cout << "4. Traverse and display" << endl;
        cout << "5. Search for a value" << endl;
        cout << "6. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter value to insert at the beginning: ";
                cin >> value;
                list.insertAtBeginning(value);
                break;
            case 2:
                cout << "Enter value to insert at the end: ";
                cin >> value;
                list.insertAtEnd(value);
                break;
            case 3:
                cout << "Enter value to delete: ";
                cin >> value;
                list.deleteByValue(value);
                break;
            case 4:
                cout << "List (forward): ";
                list.traverseAndDisplay();
                break;
            case 5:
                cout << "Enter value to search for: ";
                cin >> value;
                if (list.search(value)) {
                    cout << value << " found in the list." << endl;
                } else {
                    cout << value << " not found in the list." << endl;
                }
                break;
            case 6:
                cout << "Exiting program." << endl;
                break;
            default:
                cout << "Invalid choice. Try again." << endl;
        }
    } while (choice != 6);
    return 0;
}
