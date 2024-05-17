# custom_grid_count_view

`custom_grid_count_view` is a Flutter package that provides a dynamic height grid count view with a swipe to action feature. This package makes it easy to create flexible and interactive grid layouts in your Flutter applications.

## Features

- **Dynamic Height Grid**: Automatically adjusts the height of grid items based on their content.
- **Swipe to Action**: Implement swipe gestures to trigger actions on grid items.
- **Customizable**: Easily customize the appearance and behavior of the grid and swipe actions.

## Installation

Add `custom_grid_count_view` to your `pubspec.yaml`:

```yaml
dependencies:
  custom_grid_count_view: ^1.0.1
Then, run flutter pub get to install the package.UsageBasic Example Here’s a simple example of how to use custom_grid_count_view in your Flutter app:
```
```example 
import 'package:custom_grid_count_view/custom_grid_view.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const CustomGridCountViewExample(),
    );
  }
}

class CustomGridCountViewExample extends StatelessWidget {
  const CustomGridCountViewExample({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: CustomGridCountView(
        builder: (_,index){
          return Slidable(
            key: UniqueKey(),
            startActionPane: ActionPane(
              motion: const ScrollMotion(),
              dismissible: DismissiblePane(onDismissed: () {}),
              children:  [
                SlidableAction(
                  onPressed: (v){},
                  backgroundColor: const Color(0xFFFE4A49),
                  foregroundColor: Colors.white,
                  icon: Icons.delete,
                  label: 'Delete',
                ),
                SlidableAction(
                  onPressed: (v){},
                  backgroundColor: const Color(0xFF21B7CA),
                  foregroundColor: Colors.white,
                  icon: Icons.share,
                  label: 'Share',
                ),
              ],
            ),

            endActionPane:  ActionPane(
              motion: const ScrollMotion(),
              children: [
                SlidableAction(
                  // An action can be bigger than the others.
                  flex: 2,
                  onPressed: (v){},
                  backgroundColor: const Color(0xFF7BC043),
                  foregroundColor: Colors.white,
                  icon: Icons.archive,
                  label: 'Archive',
                ),
                SlidableAction(
                  onPressed: (v){},
                  backgroundColor: const Color(0xFF0392CF),
                  foregroundColor: Colors.white,
                  icon: Icons.save,
                  label: 'Save',
                ),
              ],
            ),
            child: Container(
              color: Colors.greenAccent,
              height: 100+(index*2),
            ),
          );
        },
        itemCount: 200,
        crossAxisCount: 3,
      ),
    );
  }
}
```

## License
This project is licensed under the MIT License - see the LICENSE file for details.
## Contributions 
Contributions are welcome! Please open an issue or submit a pull request for any bug fixes or enhancements.ContactIf you have any questions or feedback, feel free to reach out to us at [subhashchandras7318@gmail.com].

##### Thank you for using custom_grid_count_view! We hope it makes building dynamic and interactive grid layouts in your Flutter apps easier and more enjoyable.

