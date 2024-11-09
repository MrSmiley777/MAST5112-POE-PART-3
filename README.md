# MAST5112-POE-PART-3
ST10459254 MAST5112 PART 3 LOG FILE and Snack.expo ZIP
Changelog
Improvements based on feedback:
I got 98/100 and there was no feedback written but I did make some changes for fluidity. Made separate screens as Homepage.js, Menu.js and Filter.js.

For App.js:

I did not like the way I did the screens for part 2 as they were not fluid in navigation, so I imported necessary navigation components- **NavigationContainer** from **@react-navigation/native** and **createStackNavigator** from **@react-navigation/stack**.
Added **menuItems** to manage the menu data. This is the array for storing all the menu items to be manipulated.
Navigation through screens is done using **react-navigation**.
Added **Stack.Navigator** as it allows smooth navigation through screens, it does this by where each screen appears on top of the previous one, like a *stack* hence its name.

Homepage.js:

Added **ImageBackground** from **react-native** to be used to put a background for the menu to make it look like a natural menu. Food.jpg from part 2 is what I used as the background.
The menu display has dynamic content based on the **menuItems** passed from **App.js**.
We need to do the averages of each course in the menu, for this I made a function, **calculateAveragePrice** which calculates and displays the average price of menu items per course dynamically.
Used **FlatList** to render the menu items based on the **menuItems** prop.
Added buttions for navigating to the filtering screen and the screen to manage the menu.

Menu.js:

Imported **TouchableOpacity** to be used for cycling courses when adding menu items.
Introduced **dishName**, **description**, **course**, and **price** using useState to handle input fields. It is also validated to ensure that all fields are filled before adding a menu item.
On this screen the chef can enter the details of the menu item they wish to add and remove any item added. The **handleAddItem** function is used to add the items to the **menuItems** array using the **setMenuItems** function when the add button is clicked. The removal of items is done with the **handleRemoveItem** function, which removes an item based on its unique **id** when the remove button is clicked. Displayed the list of menu items in a **FlatList**.

Filter.js:

Added a state **selectedCourse** to manage the selected filter option, the **menuItems** array is dynamically filtered based on the selected course. **FlatList** is used to render the filtered items. Buttons were added to filter based on courses, (All, Starters, Mains, Desserts).

Code Refactor:

Each screen is for a single purpose, Menu screen for displaying the menu items with averages, Manage Menu screen which the chef can change the menu, and the Filter screen for the guest to filter the menu based on course selected.
**FlatList** was implemented to dynamically render lists of menu items in both homepage and filter screen.
Used **KeyExtractor** with **FlatList** to improve performance when rendering lists by providing a unique key for each item. 
