# ESCAPES, a python library with every ANSI escape code you will ever need!
## Attributes:
- - `Escapes`:
  - `bell`: makes the terminal make the error sound 
  - `backspace`: deletes the character behind the cursor, unless there are no characters behind the cursor. Newline does not count as a character.  
  - `saveScreen`: saves all content on the current screen 
  - `loadScreen`: loads the previous save
  - `newline`: makes a new line and moves cursor to the start of the new line
  - `formfeed`: form feed, or new page
  - `carraigeReturn`: printed after newline in raw or cbreak mode to make newline work properly in those modes
  - `esc`: starts an escape code
  - `delete`: delete key, not sure what it does but it does do _something_
  - `Tabs`: class that stores tabs
  - - `vertical`: a wierd tab that probably has no use
    - `horizontal`: a normal tab
    
