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
1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each
from this lab.
A StatelessWidget never changes after it is drawn, like a printed poster. A StatefulWidget can change while the app runs, like a scoreboard. In this lab, ProfileCard (Activity 1) is stateless because the name and email stay the same.

2. Why is a StatefulWidget written as two classes? What does each class do?
The first class (WaterTrackerPage) is the widget. It never changes, and its only job is to create the State object using createState(). The second class (_WaterTrackerPageState) is the State. It keeps the data that changes (_glasses), the methods that change it, and the build() method. Flutter can recreate the widget often, but the State object stays alive, so the data is not lost.

3. In Activity 2, what happened when you changed _glasses outside setState()? Why?
When i move the _glasses++ outside the setSatate() and tapped the + , the count still update   up to 8. Because the setState() was still called.

4. Looking at the Debug Console in Activity 2, when is build() called?
build() is called when the page first appears, and again every time setState() runs. In the Debug Console, a new build() called line appears after each tap on +, − or Reset.

5. Explain the main axis and the cross axis of a Row and of a Column.
the main axis is horizontal (left to right), and the cross axis is verticalwhile the column the main axis is vertical (top to bottom), and the cross axis is horizontal.

6. In Activity 3, what happened when you removed Expanded from a StatBox? What does Expanded do?
The box became only as wide as its content, so the three boxes were no longer equal in width.

7. Why do we use GridView.builder for the menu instead of a Column with many children?
The column doesn't scroll it would overflow the screen, GridView.builder does scroll, that make a grid layout and only build the cards.  

8. How do Stack and Positioned create the Best seller badge in Activity 4?
A stack draws its children on top of each other.The first child is the icon,name,price while the second child is the orang badge which positioned(top: 8, left: 8) places the badge in the top left corner


9. What is the difference between customizing with ThemeData and with a style on one widget? Give one example of each from Activity 5.
ThemeData styles the whole app so every widgets looks the same ,while a style on one widget affect or onluy shows to that specific widget.

10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the change reach MaterialApp?
the ThemeDemoAppState holds the isDark .When i flip the switch in SettingsPage,the sqitch then call the OnDarkChanged, which is the _setDark from the parent class. And _setDark calls the setState(). The MaterialApp gets the new themeMode and the whole turns to dark.