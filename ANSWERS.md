<<<<<<< HEAD
# https://github.com/angelicavillarubia-ai/flutter_basic_lab.git

# build() called: 4 glasses
# build() called: 5 glasses
# build() called: 6 glasses

# Activity 2: moving _glasses++ outside setState
 I moved _glasses++ outside setState() and tapped +. The app still updated the number and the progress bar, and a build() called line appeared after each tap. This is because setState(() {}) was still called, so Flutter ran build() again, and _glasses already had its new value. I then put the code back inside setState().

# Activity 3: removing Expanded from one StatBox
When I removed Expanded from one StatBox, that box became only as wide as its content (the icon, value and label). The other two boxes stayed wider, so the three boxes were no longer equal. I then put Expanded back and all three shared the row equally again.


# Activity 5: changing one setting in buildTheme()
I changed the button corner radius in buildTheme() from 8 to 20. The Elevated button became much more rounded, with almost pill-shaped ends. The Outlined and Filled buttons did not change, because only elevatedButtonTheme was edited.




# 10 questions.
=======
>>>>>>> 6974fcd831c60df59d8c4bbd5ab13cb575203ada
1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each
from this lab.
A StatelessWidget never changes after it’s built (e.g. StatBox), while a StatefulWidget holds data that changes and redraws (e.g. the Activity 2 water tracker).

2. Why is a StatefulWidget written as two classes? What does each class do?
The widget class is immutable and creates the State, while the State class holds the changing data and the build() method.

3. In Activity 2, what happened when you changed _glasses outside setState()? Why?
The value changed but the screen didn’t update, because only setState() tells Flutter to rebuild.

4. Looking at the Debug Console in Activity 2, when is build() called?
build() is called at first display and every time setState() runs (or the parent/theme changes).

5. Explain the main axis and the cross axis of a Row and of a Column.
Row’s main axis is horizontal and cross axis vertical; Column’s main axis is vertical and cross axis horizontal.

6. In Activity 3, what happened when you removed Expanded from a StatBox? What does Expanded do?
The boxes shrank to their content size (or overflowed); Expanded makes a child fill the available space along the main axis.

7. Why do we use GridView.builder for the menu instead of a Column with many children?
GridView.builder builds only the visible items and scrolls, while a Column builds everything at once and can overflow.

8. How do Stack and Positioned create the Best seller badge in Activity 4?
Stack layers the badge over the card, and Positioned pins it to a specific corner.

9. What is the difference between customizing with ThemeData and with a style on one widget? Give
one example of each from Activity 5.
ThemeData styles the whole app (e.g. the color scheme), while a style on one widget affects only that widget (e.g. a TextStyle on one Text).

10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the
change reach MaterialApp?
A State object above MaterialApp holds the dark-mode bool, and setState() rebuilds MaterialApp with the new themeMode..