# switch_tab

A flutter package that allows toggling as a tab bar.

## Getting started

Add the dependency to `pubspec.yaml`:
```yaml
switch_tab:
```

Import package
```dart
import 'package:switch_tab/switch_tab.dart';
```

## Example
```dart
SwitchTab(
  text: const ["Flutter", "React Native"],
  shape: SwitchTabShape.rectangle,
  thumbColor: Colors.orange,
  onValueChanged: (index) {},
)
```
![switch tab](https://github.com/radikz/switch_tab/blob/32c41c803d0cb133d90ed7e9c4b1610c7fd59fbd/example.gif)

## Contributing
Any kind of support in the form of reporting bugs, answering questions or PRs is always appreciated.