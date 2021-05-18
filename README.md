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
    - `moveEscape`: generates a escape that moves the cursor to row,column.  
      syntax: `moveEscape(row,column)`, where `row` and `column` are int values or string representations of int values.  
      **DISCLAIMER:** the coordinates start at 1, not 0, and the row that contains the command prompt used to run the script is usually reserved, and you are unable to move there untill the command prompt is pushed up with newlines!
    - `save`: saves the current cursor position
    - `load`: loads the last saved cursor position
    - `upEscape`: generates a escape that moves the cursor up `n` lines
      syntax: `upEscape(n)`, where `n` is a int value or a string representation of a int value
    - `downEscape`: generates a escape that moves the cursor down `n` lines
      syntax: `downEscape(n)`, where `n` is a int value or a string representation of a int value
    - `leftEscape`: generates a escape that moves the cursor left `n` lines
      syntax: `leftEscape(n)`, where `n` is a int value or a string representation of a int value
    - `rightEscape`: generates a escape that moves the cursor right `n` lines
      syntax: `rightEscape(n)`, where `n` is a int value or a string representation of a int value
  - `Erase`: escapes related to erasing the screen
    - `screen`: clears the screen
    - `scrollbackScreen`: clears the screen by printing &lt;terminal height&gt; newlines. Does not work properly when cursor is not at home
    - `scrollback`: clears scrollback
    - `eraseLine`, `line`: they both clear the current line. If you figure out the difference between them, please help me update this file.
    - `fromCursor`: escapes to clear from cursor
      - `toEndOfScreen`: erases everything from cursor to end of screen
      - `toStartOfScreen`: erases everything from cursor to start of screen
      - `toStartOfLine`: erases from the cursor to the start of the line
      - `toEndOfLine`: erases from the cursor to the end of the line
  - `Style`: escapes to change the style of text
    - `reset`: resets all style
    - `bold`: makes all the text printed after printing this bold
    - `dim`: makes all the text printed after printing this dim
    - `italic`: makes all the text printed after printing this italic
    - `underline`: makes all the text printed after printing this underlined
    - `blink`: makes all the text printed after printing this blink
    - `invert`: makes all the text printed after printing this have it's color inverted from the current color
    - `invisible`: makes all the text printed after printing this be invisible
    - `strikethrough`: makes all the text printed after printing this be struck through
  - `Color8`: 8 basic ansi colors that are supported widely
    - `Foreground`: foreground color escape codes
      - `black`: makes the foreground of all text printed after printing this black
      - `red`: makes the foreground of all text printed after printing this red
      - `green`: makes the foreground of all text printed after printing this green
      - `yellow`: makes the foreground of all text printed after printing this yellow
      - `blue`: makes the foreground of all text printed after printing this blue
      - `magenta`: makes the foreground of all text printed after printing this magenta
      - `cyan`: makes the foreground of all text printed after printing this cyan
      - `white`: makes the foreground of all text printed after printing this white
    - `Background`: background color escape codes
      - `black`: makes the background of all text printed after printing this black
      - `red`: makes the background of all text printed after printing this red
      - `green`: makes the background of all text printed after printing this green
      - `yellow`: makes the background of all text printed after printing this yellow
      - `blue`: makes the background of all text printed after printing this blue
      - `magenta`: makes the background of all text printed after printing this magenta
      - `cyan`: makes the background of all text printed after printing this cyan
      - `white`: makes the background of all text printed after printing this white
  - `Color256`: 256 basic ansi colors that are supported widely
    - `Foreground`: foreground escapes
      - `color`: function to make color escape code
        Syntax: `color(n)`, where `n` is the ID of your color (IDs end at 256)
    -`Background`:
      - `color`: function to make color escape code
        Syntax: `color(n)`, where `n` is the ID of your color (IDs end at 256)
  - `TrueColor` escapes for the full RGB range. some terminals dont support
    - `Foreground`: foreground escapes
      - `color`: function to make color escape code
        Syntax: `color(r,g,b)`, where `r`,`g`,and`b` are the rgb values of your color
    -`Background`:
      - `color`: function to make color escape code
        Syntax: `color(r,g,b)`, where `r`,`g`,and`b` are the rgb values of your color

---

**Disclaimers**: 
  - Some escape codes do not work in certain terminals, such as strikethrough, which does not work in terminal.app  
  - If you called one of these thinking they were functions, and got `TypeError: 'str' object is not callable`, you tried to *call* an escape code, which is meant to be *printed*.  

---

Also, a **HUGE** thank you to fnky, who made [this](https://gist.github.com/fnky/458719343aabd01cfb17a3a4f7296797) gist, which is where i took almost all of these escape codes from
