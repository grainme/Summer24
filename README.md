# Summer 2024

## 28 - 06 - 2024
- **Still learning C++ (infinite language)** //
- **unique_ptr : ** cool feature in C++, it's basically a pointer that deallocate itself when going out of scope also you can't have two owners of the same ptr, it's unique after all, there is what's called shared_ptr for that use case, but we won't go deep into that unless necessary!
- **Template Classes** : template definitons should be in the header file because they need to be available for every single translate unit (.cpp file // .cpp compiled into objects then the linker combines these objects into a single executable) that uses them, also the compiler generates code for the template when it is used with specific types. 
- **Macros vs Functions** : macros are bad (lol), error-prone, hard to debug, not very much readable, they rely on textual substitution and do not perform type checking ; macros are preprocessed whereas functions are compiled, i believe we cannot perform side effects using macros at least not naturally.
- writing multi line macros are pain in the hand (lol).
- UB : check this out, very dangerous camarade! - [Further reading](https://stackoverflow.com/questions/9104568/macro-vs-function-in-c)
- ![image](https://github.com/grainme/Summer24/assets/104838272/d331f8aa-2bdd-43c8-928d-2f2579f7f32b)
- **Extern keyword** : This comes in useful when you have global variables. You declare the existence of global variables in a header, so that each source file that includes the header knows about it, but you only need to “define” it once in one of your source files. Awesome answer by @dreamlax - [Further Reading](https://stackoverflow.com/questions/10422034/when-to-use-extern-in-c)

## 26 - 06 - 2024
- **No runtime**: I often see phrases like "Rust has no runtime" and wondered wth runtime means!
- The runtime is the part of a programming language responsible for executing the code you write. It includes memory management, error handling, and other necessary services the code relies on while running. Higher-level programming languages have a significant runtime, meaning they need to load a lot of components before running the code, such as garbage collection and dynamic type checking. In contrast, Rust, C, and C++ have minimal runtimes.
- **Lambda in C++** : i will write down some notes about lambda and related subjects
- Asynchronous vs Synchronous events: async event are the event that occur at diffrent times whereas sync event are the opposite.
- A *callback function* is a function that is passed as an argument to another function and then it will get executed inside that block, usually callback funcs are used in event-driven programming, when you want to perform some action when a certain event occurs!
- BTW we still in C/C++ (maybe this knowledge is passe-partout and could be inherited by RUST) but i'm definitely not writing about JS, so get outa here!
- SO why am i noting down callbacks, because Lambdas are so useful when it comes to defining callback in fact, here is a proper note : **C++ Lambda expressions are a convenient way to define an anonymous function object or functor in C++. It can improve readability when writing callback functions.**


## 23- 06 - 2024
- *Stuff I've learned :*
   - Insertion process in the MST:
     - Insert keys in the node till the key count == m-1 (should be inserted in ascending order)
     - if node is full ```key count == m-1``` then insert key in the left subtree where key_new < key_parent
     - if node is full ```key count == m-1``` then insert key in the right subtree where key_new > key_parent
     - Repeat Process
   - Deletion process in the MST:
     - Case 1 : Deletion of a key with no subtrees : simply delete the key.
     - Case 2a : Deletion of a key with a left subtree : Replace the key with the largest value from LST and then delete that replaced key.
     - Case 2a : Deletion of a key with a right subtree : Replace the key with the smalest valure from RST and then delete that replaced key.
     - Case 3 : Deletion of a key with both left and right subtree: Either replace the key with largest value from LST or smallest value from RST and then delete that replaced key.
- **B-Tree Introduction** :
   - it's self-balancing m-way search tree that allows all operations in O(logN)
   - it is perfectly balanced which means all leaf node are at the same depth.
   - EVERY node is at least Half-full, which means it contains up to **M/2** keys (surely less, it should be **<= M-1**)

## 21 - 06 - 2024
- *Ultimate goal is to implement a B-Tree* : I have revised some basic notion like def of Binary Tree, def of BST, Height of Tree, Balancing, why do we need balancing, its effect on T_Complexity on different operations(Insertion, searching, deletion..) -  [Further Reading](https://www.youtube.com/watch?v=MpGOoJtEYII)
- **Stuff I've learned :**
   - The most optimal tree, AFAIK is AVL Tree, because it's a BST and it is BALANCED which means its worst TC for searching is O(logN)
   - M-way Tree / M-way Search Tree (MST) : is basically a tree that where every node can have up to **M-1** key fields and **M** pointers (Address Memory) to its children.
   - **Biggest Advantage of MST over BST** is less traversal overhead, because in a MST we do have shorter heights compared to a BST because we can store multiple keys in one single node and so we can quickly look up a specific value, also from a bird's-eye view an MST is bunch of homogeneous BSTs (my own observation HHHH);
   - Different facts : max elements that a MT can handle is : **M^(H+1)-1** ; where **H** is the height of the tree and **M** is the degree already known.
   - Criteria that a MT should follow to be MST : ![image](https://github.com/grainme/Summer24/assets/104838272/71eb733a-24bd-4c7c-83ac-df09858d961b)



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
