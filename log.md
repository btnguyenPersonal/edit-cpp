# day 0
have no idea how to even read file in (i'm so rusty)
got bones working to start displaying file

# TODO for working self-editing:
- save file
- typing mode
- cursor at right position during render
- window auto focusing the cursor
- tabs prolly?

# so I don't hate myself
- Makefile that isn't dumb
- copy paste

# day 1
- got typing and moving around kinda working, still can't edit files bigger than term length
- got color sorta working, but not all 256 yet
- moved around file structure and Makefile compiling .cpp and .h -> .o -> binary
- tried for an hour getting clang-tidy linter set up; why is it so damn hard?
  - bruh have to wrap the compile command with `bear` and then generate `compile_commands.json`

# questions about c++
- pragma once?
- are linters a thing?
- how do you run tests?
- what is good style to put in .h vs .cpp?
- what are good CFLAGS?
- where should you put .o and binary?
- is it good style to put `using namespace std`?
- should i learn to use char* or string?
- default arrays or vector?
- should you always free everything before returning from main?
- is there a way to find out if any of my imports are not being used?
- what is good practice for `auto`? what about unsigned int vs int?

# day 2-3
- got motions set up, much cleaner than edit1.0
- have copy paste working with system paste, just need to make a paste shortcut and set up logic to paste into current file
- this time wanna put all HIGHLIGHTING into one file (maybe another enum specifying what type of HIGHLIGHTING we are in(v ctrLv or V)
- cursor is fully working, and logic is better because there is a sanity check every render, and no weird edge cases
- found out that terminal window size detection actually works unlike js
- got a shower thought that for big files want to do DoubleLinkedList<DoubleLinkedList> data, because for inserting and deleting would be faster
  - will have to test performance, but inserting be O(1) should make things a lot faster I would think, because that's almost all the actions going on
- I wonder how bad perf is right now for >1GB files?

```
line 0 | 'H' <-> 'E' <-> 'L' <-> 'L' <-> 'O'
line 1 | 'W' <-> 'O' <-> 'R' <-> 'L' <-> 'D' <-> '!'
line 2 | ''

0 <-> 1 <-> 2
```

# day 4ish
- colors!!
- made render function amazing, can deal with files that are 256000 lines long comfortably
- omg pointers make everything so fast, didn't know that putting something in function params made a copy neat
- putting a huge file in made a huge difference for finding bugs
- maybe later will test with even larger files
- want to start self editing, but at least need
    - visual mode
    - diff based undo
    - commenting
    - searching

    - autosave feels really nice
    - tab completion
    - file tabs
    (wanna try making these fullscreen ones off to the side maybe?? atleast fileexplorer should be)
    - grep
    - filefinder
    - fileexplorer

# day 5ish
- added visualLine
- wow much cleaner than the js crap I had
- std::vector has cool iterators
- had to add the same if (deleted entire file) { add empty line }
- also black seems a bit different color but idk
- plan for tomorrow:
    - paste
    - visual (normal)
    - visual (block)
    - commenting
- plan for sunday:
    - undo (diff based) don't chicken out again I tried in edit1.0 like 2 times and failed

# weekend over
- paste working, uses newline at end like correct
- visualLine working, need visual and visualBlock
- wow why was undo so hard before?
- i mean i didn't get the most efficient one, but whatever I'll fix it later when i need perf
- undo also why didn't i just find the location change happened instead of storing it with the diff???

# switch over
- let's see how this goes, hopefully no bugs pop up fingers crossed


# grep & findfile working
todo need harpoon(need to figure out how to store old states, maybe make an archive? maps filename to old state)
search replace

??? todo make H character switch between .cpp and .h
