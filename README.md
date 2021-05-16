# ESCAPES, a python library with every ANSI escape code you will ever need!
## Attributes:
- `Escapes`:
  - `bell`: makes the terminal make the error sound 
  - `backspace`: deletes the character behind the cursor, unless there are no characters behind the cursor. Newline does not count as a character.  
  - `saveScreen`: saves all content on the current screen  
    **DISCLAIMER:** it will only save the line which contains the command used to start the script, and any output that the program makes **that is in view**!
  - `loadScreen`: loads the previous save
  - `newline`: makes a new line and moves cursor to the start of the new line
  - `formfeed`: form feed, or new page
  - `carraigeReturn`: printed after newline in raw or cbreak mode to make newline work properly in those modes
  - `esc`: starts an escape code
  - `delete`: delete key, not sure what it does but it does do _something_
  - `Tabs`: class that stores tabs
    - `vertical`: a wierd tab that probably has no use
    - `horizontal`: a normal tab
  - `Cursor`: cursor related escape codes
    - `makeInvisible`: hide the cursor
    - `makeVisible`: show the cursor
    - `home`: move the cursor to home (`(1,2)`)
    - `moveTo`: the template of the escape to move the cursor, where row is "row" and column is "column".  
      The escape is not yet built.
    - `moveEscape`: generates a escape that moves the cursor to row,column.  
      syntax: `moveEscape(row,column)`, where `row` and `column` are int values or string representations of int values.  
      **DISCLAIMER:** the coordinates start at 1, not 0, and row 1 is usually reserved, and you are unable to move there!
    - `save`: saves the current cursor position
    - `load`: loads the last saved cursor position
    - `up`: the template to move the cursor up `#` lines  
      The escape is not yet built.
    - `upEscape`: generates a escape that moves the cursor up `n` lines
      syntax: `upEscape(n)`, where `n` is a int value or a string representation of a int value
    - `down`: the template to move the cursor down `#` lines  
      The escape is not yet built.
    - `downEscape`: generates a escape that moves the cursor down `n` lines
      syntax: `downEscape(n)`, where `n` is a int value or a string representation of a int value
    - `left`: the template to move the cursor left `#` lines  
      The escape is not yet built.
    - `leftEscape`: generates a escape that moves the cursor left `n` lines
      syntax: `leftEscape(n)`, where `n` is a int value or a string representation of a int value
    - `right`: the template to move the cursor right `#` lines  
      The escape is not yet built.
    - `rightEscape`: generates a escape that moves the cursor right `n` lines
      syntax: `rightEscape(n)`, where `n` is a int value or a string representation of a int value
  - `Erase`: escapes related to erasing the screen
    - `screen`: clears the screen
    - `scrollbackScreen`: clears the screen by printing &lt;terminal height&gt;
