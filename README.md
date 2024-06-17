
### StatelessWidget
A `StatelessWidget` is a type of widget that doesn't change. Think of it like a photo. Once you print it, it stays the same.

#### Key Points:
- **Unchanging**: Once it’s created, it doesn’t change.
- **Simple**: Best for showing things that don’t need to update.

#### Example:
Imagine you have a widget that shows a text. Since the text won’t change, you can use a `StatelessWidget`.

```dart
import 'package:flutter/material.dart';

class MyStatelessWidget extends StatelessWidget {
  final String text;

  MyStatelessWidget({required this.text});

  @override
  Widget build(BuildContext context) {
    return Text(text);
  }
}

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('Stateless Widget Example')),
      body: Center(
        child: MyStatelessWidget(text: 'Hello, World!'),
      ),
    ),
  ));
}
```

In this example, `MyStatelessWidget` takes some text and displays it. The text won't change, so the widget doesn't need to update.

### StatefulWidget
A `StatefulWidget` is a type of widget that can change. Think of it like a chalkboard. You can write on it, erase it, and write something new. It can change over time.

#### Key Points:
- **Changing**: Can update based on user actions, data changes, or other events.
- **Interactive**: Best for showing things that change or need interaction.

#### Example:
Imagine you have a widget that shows a counter and a button. Every time you press the button, the counter goes up.

```dart
import 'package:flutter/material.dart';

class MyStatefulWidget extends StatefulWidget {
  @override
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
}

class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text('You have pressed the button this many times:'),
        Text(
          '$_counter',
          style: Theme.of(context).textTheme.headline4,
        ),
        ElevatedButton(
          onPressed: _incrementCounter,
          child: Text('Increment'),
        ),
      ],
    );
  }
}

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      appBar: AppBar(title: Text('Stateful Widget Example')),
      body: Center(
        child: MyStatefulWidget(),
      ),
    ),
  ));
}
```

In this example, `MyStatefulWidget` has a counter that starts at 0. Each time you press the button, the counter goes up by 1. The `setState` function tells Flutter to update the UI with the new counter value.

### In-short
- **StatelessWidget**: Use it when the content does not need to change, like labels or fixed images.
- **StatefulWidget**: Use it when the content needs to change dynamically, like forms, counters, or interactive elements.

By understanding these two types of widgets, you can decide when to use each one, depending on whether your UI needs to change or stay the same.
