# Flutter Widgets 2

- `CheckBox` - Have a Boolean value which is switched by a n `onChanged` method, fired every time there is a change on the `checkbox`
- `Radio Buttons` - These differ from `checkboxes` as you usually see a radio button used when you are wanting users to select only one option
  - They are grouped to ensure when one radio button is selected the others are deselected. In Flutter, the `groupValue ID` is what groups radio buttons together
- `Dropdown` - These are used when you want to provide a user with a selection of choices
- `Form` - These Widgets are great but if you are using them in a form you will need to bring it all together in a `Form Widget`. A `Form Widget` groups all child Widgets together so that yo can control them entirely rather than individually.
-  Gestures - Swiping, tapping, pinching are all interactions within an application. We call these gestures in Flutter.

## Laying out Widgets

When building any app things can get complicated, you should always start with a basic wireframe and a good understanding of the programming language and environment.

1. Layout the entire view (scene) - this includes the `AppBar`, menu navigation and structure of your apps
2. Positions Widgets next to each other - you might want a title and a description to appear above and below each other
3. Spacing Widgets - create padding/margins to allow your Widgets to breathe
4. Handle the situation when you un out of space and overflow is required

## AppBar 

The `AppBar` Widget is the area at the top of the view. `Appbar's` are not mandatory in building any mobile application. However, we've grown to familiarise ourselves with this bar at the top of the screen where prominent features are based for navigation, help and proceeding. An `AppBar` can include Text, Icons, Buttons etc. 

## Container

Web technologies have found their way into Flutter such as `container`. We define this as the box mode, and its used to create pleasing user interfaces - allowing for space, clarity and style. However, not all these properties can be found in every Widget we need to rethink how our views are broken down. For example, you can't add border, padding and margin to an Image Widget. However, you can embed an Image Widget inside a Container. Where the Container Widget does include such properties. The Image Widget becomes the child of the Container.

## Alignment

When you place a Widget inside another (large Container) you will have more space in the Container needed for the child.

The default position for the child Widget would be top, left. This can be altered using the alignment property. Top left would be -1,-1; bottom right becomes 1,1 and centre is 0,0. 

That said, in Flutter we can use String to represent theses coordinates such as `topLeft`, `bottomRight`, `center`.

## Navigation

The more complex our mobile apps become, the need for better navigation is important. Facebook have evolved their interface over the years from using tabs, fragments, top bar navigation, app bar navigation and so on.

This is an excellent demonstration of how complex the Facebook app has become and the next to understand their audiences - how they use the app, what features do people want direct access to and where is the optimum location for such Interactions when viewed on various screen sizes, ratio and thickness.

There are many ways to navigate users in your app:

1. Stacks - each Widget is full screen and as a user taps a button go to the next view each view is maintained in the stack. Therefore, a user can traverse back and forth to each view in the history
2. Drawer - these are also known as hamburger menus
3. Tabs - these are what we saw In the Facebook app. These can be located at the top of bottom of our views. The tab bar contains a set of Items which when tapped navigate the user to a new widget
4. Dialogs - are model (pop-ups) and are usually used when alerting/Informing the user about an action. We've already experienced one of these in the form of the `SnackBar`

