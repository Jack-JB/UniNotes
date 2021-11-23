# Flutter Widgets

## Widgets

Flutter is based around componentisation, and in Flutter we can these components **Widgets**.

Remember flutter is based around Widgets (everything is a widget) and Widgets inside Widgets are 'Custom Widgets'.

<img src="C:\src\UniNotes\Year 2\CO2509 - Mobile Computing\images\image-20211123090627223.png" alt="image-20211123090627223" style="zoom:50%;" />

The approach to building mobile applications is through components. A Widget is basically a component. A view is made up of many components (Widgets).

The process is known as **componentisation**. This is not new but is something that is making a come back in terms of how other programming platforms approach development. React, Angular, Vue etc these days are all based on components. In essence, it's the breaking down of a problem into smaller chunks. You are breaking down a complex view into smaller Widgets (components) to handle a particular task.

In modern mobile development we break down our code into two parts: 

1. Behaviour
2. Presentation

To put it simply, the logic required to run applications and the look and feel of what is presented to the users.

### Widget Categories

**TODO: Finish this section**

1. **Value** - Checkbox, FlatButton.Icon, Text, Radio, Image etc. (These Widgets hold a 'value')
2. **Layout** -
3. **Navigation**
4. **Other**

​	It is important to note here that Widgets that are used to make up another Widget are defined as Custom Widgets. Every Widget is a class that has properties and methods (with zero or more parameters). Every Widget has its own build method which receives a `BuildContext` **TODO: Finish**

### Stateless and Stateful Widget

Widgets are based around this term of stateless and stateful fundamentals

- A Widget that retains its own state is known as a Stateful Widget
- Whereas a Stateless Widget does not

State refers to the data within the Widget is stored and maintained over its lifetime. The best way to think about this is if you have a label that shows static information like a user's name this doesn't need to be retained and therefore a Stateless Widget is fine. Whereas, if you want to allow users to change their email address in a TextField you want to display their current information then allow then to overwrite this - this would be known as a Stateful Widget. You need to know the state of the Widget prior, during and post display of information.

The rule of thumb is to always use Stateless Widgets and refactor them when you know this Widget requires state. You should strive to make your Widgets and apps as simple as possible - easier to write, simple to maintain and extend.

### Value Widgets

Remember a value Widget holds a value such as a text field.

### Images

**TODO: Add this section**

### Input Widgets

These are commonly used within forms. Similar to how an input text area works in HTML but they do not work in the sam,e way. In Flutter Input Widgets don't maintain their state (you have to do this manually). This makes it more difficult but is much safer and gives you much more control.

Input Widgets are best used within a Stateful widget. **TODO: Finish**

### Positioning Widgets

Positioning widgets are very important. We need to be able to position widgets next to each other, above/below, creating padding and spaces between them. When laying out widgets we need to know five things;

1. How to layout the entire screen (the scene). This is how we layout the entire view with the `AppBar`, `menu`, `buttons` etc
2. Position widgets in relation to each other. it is important to think about how these widgets behave next to each other
3. Space between widgets
4. How we deal with running out of space. You might have a list that overflows the screen. You will need to think about dealing with this.
5. Add fine details to our positioning

Row and Column are two of the most commonly used layout patterns. Each take a list of child widgets. A child widget can

### MaterialApp Widget

The `MaterialApp` Widget creates the outer framework for your app. This is what underpins your view. The user will never see **TODO: Finish**

### SafeArea Widgets

The `SafeArea` Widget, handles all the differences that we have amongst devices, curved screens, notches, rounded corners etc. If we wrap the SafeArea widget around our body, it will handle all these issues for us.

```dart
body: SafeArea(
)
```

### SnackBar Widget

`SnackBar` widgets are those areas on the view that alert the user to an action that has just happened. For instance, you have just deleted an email the `SnackBar` will notify you about this email has been deleted. The `SnackBar` can also include actions that the user can perform. In the case of the email deleted this could be 'undo'. `SnackBar` Widgets **TODO: Finish**

## Content First

Always consider what you content you want to display and chose the right UI component for it.

For example a list of name like an address book is best suited for a `ListView` Widget

