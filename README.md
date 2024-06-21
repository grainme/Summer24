# Summer 2024

## 21 - 06 - 2024
- *Ultimate goal is to implement a B-Tree* : I have revised some basic notion like def of Binary Tree, def of BST, Height of Tree, Balancing, why do we need balancing, its effect on T_Complexity on different operations(Insertion, searching, deletion..) -  [Further Reading](https://www.youtube.com/watch?v=MpGOoJtEYII)
- The most optimal tree, AFAIK is AVL Tree, because it's a BST and it is BALANCED which means its worst TC for searching is O(logN) 

## 20 - 06 - 2024
- *I'm trying to understand the following* : *This is why the main limitation of storage engines is the disk itself, and thus all designs try to minimize disk I/O and disk seeks as much as possible. Some designs even get rid of disks in favor of SSDs (although they are much more expensive)*
- *Difference between RAM and Disk Storage*
  - *Definitions* : RAM is a volatile memory that is used to store and quickly access data that is actively being used or processed. once laptop is powered off, data is BAHH! On the other hand, Storage is used for long-term data retention, like an HDD or SDD and unlike RAM this type of storage is non-volatile which means it can be used to keep data even after the laptop is powered off.
  - *Speed & capacity* : RAM is quicker that Disk Storage; Disk Storage can handle a huge amount of data whereas RAM can only handle Gbs of data!
  - *Further reading* : [Useful blog](https://www.backblaze.com/blog/whats-diff-ram-vs-storage/)   

## 17 - 06 - 2024
- *Source* : [Database Internals](https://www.databass.dev)
- [ ] *Database Fundamentals : Implementing Simple DBMS*:
  - *Basic Functions* : Db_get() to retrieve stuff from the database and Db_set() to push stuff to the database.
  - *Optimization Step* : Avoiding ACID problems, this a thing that most databases strive to guarantee.
    - *Atomicity* : if the machine crashes while running db_set() function, data would be written partially [Solution: Write to a temp then rename if all good!]
    - *Consistency* : this is a bit weird, and most internet people agree that it has been added to make the acronym work (ACID), otherwise it is also referred as referential integrity, which  is not a database private thing but a rule put by the creator of the database to maintain consistency across data - [Further Reading](https://www.freecodecamp.org/news/acid-databases-explained/#what-does-consistency-mean) 
    - *Isolation* : if one process calls db_get() while another calls db_set() on the same data, we might read only a part of data, leading to a corrupt result!
    - *Durability* : db_set() has just terminated succesfully, the machine crashes we might lost the data, as it's not flushed to the disk! [solution : flush it lol && sync]
    - *Performance (optional)* grep (bash) - while loop in C++ uses O(n) algorithm to find a certain key in the database file which is slow! [solution : hashmap, indexing...]

## 16 - 06 - 2024
- [x] *Profiling in C++ (gprof)*:
  - *Concept*: Profiling helps determine how your program uses processor resources.
  - *Goal*: Identify functions that take more time than expected and optimize them.
  - *Further Reading*: [More info on gprof](https://web.cecs.pdx.edu/~karavan/perf/book_gprof.html).

## 13 - 06 - 2024
- [x] *Simple Game Development using SFML*: 
  - *Concept*: Keep the game running until a specific action (e.g., game over) using a while loop.
  - *GUI Coding*: Utilized SFML library.
    - Main built-ins used: `sf::Sprite`, `sf::Texture`, `sf::RenderWindow`.
    - Functions: `window.clear()` on each iteration, `window.draw()`, `sprite.setPosition(x * SIZE, y * SIZE)`.
  - *Coding Practices*: 
    - used header files and namespaces.
    - employed classes instead of structs for practice.
    - Implemented static attributes.
    - active event listening: `window.pollEvent(e)`, `sf::Keyboard`.
    - randomization: `rand()` (when need to init a new square for the snake's food) + using modulo dimensions of the grid.
    - explained the difference between `const` and `#define`, and the use cases of `constexpr`.
    - Linking header files: Need to include them when running the executable.
