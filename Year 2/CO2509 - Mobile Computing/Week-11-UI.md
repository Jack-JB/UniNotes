# User Interface

## Widgets

- Stateless, Stateful and Inherited
- All immutable
  - Some have levels of state attached to them

### Stateless Widget

Once built the Widget can't be altered, every Widget starts off as a Stateless Widget and morphs into Stateful Widget

The lifecycle of a stateless widget starts with a constructor, which you can pass parameters to, and a `build()` method, which you override. The visual description of the widget is determined by the `build()` method.

The following events trigger this kind of widget to update:

1. 1.The widget is inserted into the widget tree for the first time
2. The state of a dependency or inherited widget — ancestor nodes — changes

### Stateful Widget

Preserve state, useful for when the UI needs to change dynamically

Stateful widgets store their mutable state in a separate State class. That's why every stateful widget must override and implement `createState()`.

### State Lifecycle

Every widget's `build()` method takes a `BuildContext` as an argument. The build context tells you where you are in the tree of widgets. You can access the element for any widget through the `BuildContext`. Later, you'll see why the build context is important especially for accessing state information from parent widgets.

### Dispose()

The rule of thumb for `dispose()` is to check any properties you define in your state and make sure you've disposed of them properly.

## Layout Widgets

### ListView

Lists are very important in mobile interfaces. Lists permit the user to reveal more content either by scrolling or tapping on items.

`Column()` or `Row()` Widgets are similar to `ListViews` apart from the are designed not to be scrolled.

A `ListView` takes four constructors:

1. The default constructor takes a list of widgets called children. That will construct every single child in the list, even the ones that aren't visible. You should use this if you have a small number of children
2. `ListView.builder()` takes in an `IndexedWidgetBuilder` and builds the list on demand. It will only construct the children that are visible onscreen. You should use this if you need to display a large or infinite number of items
3. `ListView.seperated()` takes two `IndexBuildWidgetBuilders`, `itemBuilder` and `seperatorBuilder`. This is useful if you want to place a separator widget between your items
4. `ListView.custom()` gives you more fine-grain control over your child items

### Nested ListView

You can use Nested `ListView's` to create a multiple list layout horizontal and vertical layouts.

### GridView

a `GridView` is a 2D scrollable widget. Supports horizontal and vertical scrolling.

Has five constructors:

1. The default takes an explicit list of widgets
2. `GridView.builder()`
3. `GridView.count()`
4. `GridView.custom()`
5. `GridView.extent()`