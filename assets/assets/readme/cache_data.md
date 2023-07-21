# cache_data

A Flutter library to fetch data then save the data with duration as a age of data using hive; return dart objects.
This library depend on [hive](https://pub.dev/packages/hive) for the database and [dart_json_mapper](https://pub.dev/packages/dart_json_mapper) for deserialize JSON to Dart object

## Getting started

Add the dependency to `pubspec.yaml`:
```yaml
dependencies:
  cache_data:
  dart_json_mapper:
  dart_json_mapper_flutter:
dev_dependencies:
  build_runner:
```

Put `@jsonSerializable` at your model.

**data.dart**
```dart
@jsonSerializable
class Data {
  int userId;
  int id;
  String title;

  Data({
    required this.userId,
    required this.id,
    required this.title,
  });
}
```

Next is add **main.mapper.g.dart** and initializes package.

**main.dart**
```dart
import 'main.mapper.g.dart' show initializeJsonMapper;

import 'package:dart_json_mapper_flutter/dart_json_mapper_flutter.dart' show flutterAdapter;

Future<void> main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await CacheData.init();
  initializeJsonMapper(adapters: [flutterAdapter]);
  runApp(const MyApp());
}
```

Next, create the **build.yaml** in project directory.
```yaml
targets:
  $default:
    builders:
      dart_json_mapper:
        generate_for:
        # here should be listed entry point files having 'void main()' function
          - lib/main.dart

      # This part is needed to tell original reflectable builder to stay away
      # it overrides default options for reflectable builder to an **empty** set of files
      reflectable:
        generate_for:
          - no/files
```

Now generate **main.mapper.g.dart** files
```shell
pub run build_runner build --delete-conflicting-outputs
```
or 
```shell
pub run build_runner watch --delete-conflicting-outputs
```
if you want to generate files everytime you make changes in the code.


## Usage
```dart
final cache = CacheData<List<Data>>();

FutureBuilder<List<Data>?>(
  future: cache.fetchData(
    'https://jsonplaceholder.typicode.com/albums',
    duration: duration),
  builder: (context, snapshot) {
    ...
  },
)
```

## Additional information

For more details about how to use dart_json_mapper, you can visit this [package](https://pub.dev/packages/dart_json_mapper)
