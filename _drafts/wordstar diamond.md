The WordStarDiamond refers to the system of KeyboardLayout originated by WordStar (MicroPro Int'l.) for cursor and screen movement. It was originally designed by SeymourRubenstein and RobBarnaby. The WordStar diamond began with this construct:

"Ромб WordStar" называют набор горячих клавиш, которые использовались в редакторе WordStar для пермещения курсора и текста. Основой ромба WordStar была следующая конструкция
 
        ^E
     ^S    ^D
        ^X

Note that these letters represent the position of the keys on the left-hand side of a standard QWERTY keyboard.

Все эти буквы расположены под левой рукой в стандартной ISO/ANSI клавиатуре. Переопределяем клавиши под эту комбинацию в меню "Опции --> Сочетание клавиш...". Сразу становится понятно, что переопределяется два типовых сочетания клавиш. "Ctrl+S" - сохранить, "Ctrl+X" - вырезать. Их тоже придется переопределить. Я переопределил на "Ctrl+Shift+S" и "Ctrl+Shift+X". Это работает, но некомфортно переопределять клавиши, которые совершенно стандартые в большинстве программ. Теперь клавиши ромба WordStar двигают курсор. 

By adding a control key prefix to these keys, the typist could control the movement of the cursor (or pointer) without using the "arrow keys". Ctrl-E moved the cursor one line up, Ctrl-X moved it one line down, Ctrl-S moved the cursor one character to the left, and Ctrl-D moved it one character to the right. Holding the Control-key combination down for a second or two invoked key repeat, as expected.

Рядом с клавишами движения курсора находятся клавиши перемещения по словам. "Ctrl+A" двигает курсор на слово влево и "Ctrl+F" на слово вправо. Обе эти комбинации заменяют стандартные сочетания клавиш для выделения всего текста и поиска. Присваиваем для выделения всего текста комбинацию "Ctrl+Shift+A" и для поиска "Ctrl+Shift+F". 

The next aspect of the "WordStar Diamond" was to move by words. Add Ctrl-A to move left by a word, and Ctrl-F to move the cursor to the next word to the right. The same mnemonic pattern of movement remains. Left of the invisible spot between the keys S and D moved to the left, and right of that invisible spot moved the cursor to the right.

         E
         |
 ^A   S--+--D  ^F
         |
         X

Клавиши листания страницы вверх и вниз привязываются к "Ctrl+R" и "Ctrl+C". Опять переопределяем сочетание клавиш для копирования текста на "Ctrl+Shift+C". Клавиши "Ctrl+W" и "Ctrl+Z" прокручивают экран на строку вверх и строку вниз но не меняют положения курсора. В Notepad++ такая функция есть.

Page-Up and Page-Down were performed with Ctrl-R and Ctrl-C, respectively, since the R key is "up" (above the F key) and the C key is "down" (below the F key).

Fourth, there was screen movement. Ctrl-W would scroll the screen (but not the cursor) up one line, and Ctrl-Z would scroll the screen down one line, while keeping the cursor on the same line it was originally.

   ^W    E   ^R
         |
  A---S--+--D---F
         | 
   ^Z    X   ^C
   
   
Теперь все базовые операции навигации по тексту можно выполнять одной левой, не снимая руки с буквенных клавиш клавиатуры. Это заметно ускоряет правку текста, но при условии "правильного" расположения клавиши Ctrl вместо Caps Lock. Это работает либо с Happy hacking keyboard. Либо с помощью переопределения клавиши CapsLock при помощи программы AutoHotkey, либо с помощью программирования клавиатуры форм-фактора 60% или даже 40%.

Note that the basic typing operations are performed by the left hand, without leaving the main keyboard. This system was devised during the days when keyboards had the Control key directly to the left of the A key ("where God intended"), instead of its position on modern keyboards to the extreme lower left.

Следующие клавиши не относятся к "ромбу WordStar", но тоже нажимаются левой рукой. Это "Ctrl+G" который аналогичен клавише "Delete" и удаляет символ справа от курсора. В оригинальном WordStar клавиша "Ctrl+H" заменяла Backspace, но я не переопределял ее, так как клавиша Backspace есть на клавиатуре и нажать ее проще. "Ctrl+T" удаляет слово справа от курсора. Слово слева от курсора удаляется "по-старинке" при помощи "Ctrl+Backspace".

Although I do not consider it part of the WordStar Diamond, four common editing operations were available to the left hand: Delete the next character to the right (Ctrl-G), delete the next word to the right (Ctrl-T), toggle insert ON or OFF (Ctrl-V), and reformat the paragraph (Ctrl-B). By keeping the little finger of one's left hand anchored to the control key next to the "A", the trained typist could both type and make significant edits without looking down to the keyboard at all.

    W    E    R   ^T
         |
  A---S--+--D---F---^G
         | 
    Z    X    C   ^V  ^B
	
WordStar also offered chorded keys, or commands which used a two-key combination. The first key was a control key, and the second key was either a control key or a normal letter. Unlike the location-sensitive WordStar diamond, the two-key menus were mnemonic according to the actions they performed. Thus, Ctrl-Q invoked the Quick Menu, Ctrl-K invoked the Block Menu, Ctrl-O invoked the Onscreen menu, and Ctrl-P invoked the Print Menu. If the typist would type both keys in rapid succession, the menu would not come up at all, but the operation would be performed directly.

For example, to mark the beginning of a block one typed "^K B" (think of Block). But "^K b" and "^K ^B" would do the same thing. To mark the end of a block one typed "^K K" (think of blocK). And again, "^K k" or "^K ^K" would likewise mark the end of the block.

The intuitive nature of the WordStar diamond caused it to be emulated in a number of other word processors and editing environments, even where not overtly documented. For example, [Robert Sawyer] points out that dBase (Ashton Tate), SuperCalc, Sidekick (Borland), the Borland editor, XTree Pro, and even Microsoft's own EDIT.COM (after DOS 5.0) used the cursor movement system originally developed by WordStar. VDE and TDE, both still in active development, use the WordStarDiamond and other WordStar-based commands for editing text.

From what I'm hearing now, the ^K key was actually selected because it is a strong finger (on the QwertyKeyboard).

WordMaster worked somewhat differently. For additional info, see WMvsWScmdst