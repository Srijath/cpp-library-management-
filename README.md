# cpp-library-management-
Library Manager

A menu-driven C++ console app for adding, listing, searching, issuing, and returning books. The book list is loaded from `library_data.txt` when the app starts and saved after changes, so it is available the next time you run the program.

## Build and run

With g++:

```sh
g++ -std=c++17 library_manager.cpp -o library_manager
./library_manager
```

On Windows, run `library_manager.exe` after compiling. The app creates `library_data.txt` in its current working folder.

## Class design

- `Book` stores a book's ID, title, author, and whether it is issued. Its `issue()` and `giveBack()` methods update the status.
- `Library` owns the `std::vector<Book>`, assigns IDs, searches and lists books, changes issue status, and reads/writes the text file.
- `main()` displays the menu and collects input. The data file uses quoted title and author fields, so names with spaces are preserved.

IDs are assigned automatically and remain associated with the book after reload. Search matches part of a title or author without case sensitivity. Invalid menu choices and IDs are rejected without ending the program.
