# Summer 2024

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
