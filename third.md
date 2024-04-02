Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.

#include<iostream>
using namespace std;

struct Book {
    string title;
    string author;
    string isbn;
};

int main() {
    
    map<string, Book> library;

    library["978-0590353403"] = {"Harry Potter and the Sorcerer's Stone", "J.K. Rowling", "978-0590353403"};
    library["978-0439064873"] = {"Harry Potter and the Chamber of Secrets", "J.K. Rowling", "978-0439064873"};
    library["978-0439136358"] = {"Harry Potter and the Prisoner of Azkaban", "J.K. Rowling", "978-0439136358"};
    library["978-0439139601"] = {"Harry Potter and the Goblet of Fire", "J.K. Rowling", "978-0439139601"};
    library["978-0439358071"] = {"Harry Potter and the Order of the Phoenix", "J.K. Rowling", "978-0439358071"};

    cout << "Enter the ISBN of the book: ";
    string input_isbn;
    cin >> input_isbn;

    if (library.find(input_isbn) != library.end()) {

        Book book = library[input_isbn];
        cout << "Book Found!\n";
        cout << "Title: " << book.title << endl;
        cout << "Author: " << book.author << endl;
        cout << "ISBN: " << book.isbn << endl;
    } else {
    
        cout << "Sorry, the book with ISBN " << input_isbn << " is not available in the library." << endl;
    }

    return 0;
}
