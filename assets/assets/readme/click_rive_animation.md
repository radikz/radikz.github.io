# Click Rive Animation
Flutter package for clicking animation with the help of rive animation

Any help is appreciated! Comment, suggestions, issues, or PR's!

---

## Goal
The goal of this package is creating a click animation with the help of rive package.

Currently, it takes one animation to run.

## Usage

Just drop it in your `pubspec.yaml`

```yaml
click_rive_animation: ^0.1.0-alpha
```

Make sure you have an animation in rive. No worries if you have none of that. In [here](https://help.rive.app/), you can find good documentation about rive which help you create a good animation.

> If you create animation from scratch with rive, make sure the animation mode is One-shot animation. Otherwise, choosing loop will make animation keep running.


```dart
Scaffold(
  backgroundColor: Colors.black,
  body: ClickRiveAnimation.asset(
    "assets/ripple.riv",
    animationName: "click_ripple",
    child: SizedBox(),
  ),
)
```

![screenshot](https://github.com/radikz/click_rive_animation/blob/master/screenshots/click_anim.gif)

Ideas are appreciated!
