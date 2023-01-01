# Custom Selectable Text

This package helps you to select text and perform utilize functionalities like copy. You can also perform custom selectable like share text.

## Screenshot
![ss](https://raw.githubusercontent.com/radikz/custom_selectable_text/master/screenshots/ss.png)

## Usage
![ss1](https://raw.githubusercontent.com/radikz/custom_selectable_text/master/screenshots/ss1.png)

```dart
CustomSelectableText(
  "Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit...",
  textAlign: TextAlign.center,
  items: [
    CustomSelectableTextItem(controlType: SelectionControlType.copy),
    CustomSelectableTextItem(
        controlType: SelectionControlType.selectAll),
    CustomSelectableTextItem(
        label: "Share",
        controlType: SelectionControlType.other,
        onPressed: (text) {
          ScaffoldMessenger.of(context).showSnackBar(SnackBar(
            content: Text("$text is successfully shared"),
          ));
        }),
  ],
)
```

### You can also change to icons


![ss2](https://raw.githubusercontent.com/radikz/custom_selectable_text/master/screenshots/ss2.png)

```dart
CustomSelectableText(
  "Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit...",
  textAlign: TextAlign.center,
  items: [
    CustomSelectableTextItem.icon(controlType: SelectionControlType.copy, icon: const Icon(Icons.copy)),
    CustomSelectableTextItem.icon(
        controlType: SelectionControlType.selectAll, icon: const Icon(Icons.select_all)),
    CustomSelectableTextItem.icon(
        icon: const Icon(Icons.share),
        onPressed: (text) {
          ScaffoldMessenger.of(context).showSnackBar(SnackBar(
            content: Text("$text is successfully shared"),
          ));
        }),
  ],
)
```