# flutter_opencv

A Flutter plug-in providing a binding to OpenCV-4.x.

[![Pub](https://img.shields.io/pub/v/opencv.svg)](https://pub.dartlang.org/packages/opencv)
[![Docs flutter-opencv.readthedocs.io](https://img.shields.io/website-up-down-green-red/http/flutter-opencv.readthedocs.io.svg)](https://flutter-opencv.readthedocs.io/)
[![GitHub license](https://img.shields.io/github/license/AdityaMulgundkar/flutter_opencv.svg)](https://github.com/AdityaMulgundkar/flutter_opencv/blob/master/LICENSE)

[![Flutter OpenCV](https://media.giphy.com/media/M9UOQmSYQrWgOkYqO8/giphy.gif)](https://pub.dartlang.org/packages/opencv)

## Usage

### Installation

In the `pubspec.yaml` of your flutter project, add the following dependency:

```yaml
dependencies:
  ...
  opencv: "^1.0.0"
```

In your library add the following import:

```dart
import 'package:opencv/opencv.dart';
```

### Examples

#### Basic Usage
All functions are currently contained in the ImgProc class.
e.g. `ImgProc.blur(...)`

Variables for integer choices (read pre-defined values/enums for border types, threshold types, etc.) are stored in ImgProc & Core classes, exactly similar to how OpenCV itself does.
i.e. One of the border types is `Core.BORDER_REFLECT`,
can be used in `ImgProc.blur(someBytes, someIntArray, someIntArray, Core.BORDER_REFLECT);`

So, if you refer to the OpenCV docs or a tutorial, the function you're implementing in OpenCV is very much identical to that in flutter_opencv.

The only difference is how the data is managed - OpenCV uses the Mat class to store every image as a matrix.

flutter_opencv instead only works on data as an array of bytes.

## FAQs related to the idea/concept behind this plug-in

### Why not do a full binding?
I am actually planning to write a full binding and publish it separately later on. I understand that this implementation is lackluster & a lot of functions still need to be added. If you really need something, make a feature request.

### Why not use the core OpenCV classes like Mat?
Because I wanted to provide a simple interface - one that does not require the user to learn OpenCV or it's API. Instead, much of the way the library works is designed around Flutter/Dart, making it easier for Flutter users to pick it up.

### Does lesser functions (in comparison to a full binding) mean lower build size?
Unfortunately, no. The build size would be the same for this, or a fully bound version (which I'll work on after this project reaches certain level of maturity)

### Benchmarks?
None yet. I'm still profiling the plug-in for most use cases, and haven't faced any issues with rendering so far. Will add benchmarks soon. PR/PM me if interested.

###

## Getting started

### With Flutter OpenCV
See the `example` directory for a complete sample app using Flutter OpenCV.

### With Flutter
For help getting started with Flutter, view the online [documentation](https://flutter.io/).

## Notes
 * iOS not supported currently - I do not own a Mac, so deploying for iOS will be a little slow.

## Todos
   - [x] Setup CI for docs
   - [ ] Document using Sphinx, store in `/docs`
   - [ ] List [future features](https://docs.opencv.org/2.4/index.html) in the doc
   - [ ] Create an issue template
   - [ ] Document basic usage
   - [ ] Document/blog about advanced usage
   - [ ] Create an feature request template
   - [ ] Write tests

## Changelog

Please see the [Changelog](https://github.com/AdityaMulgundkar/flutter_opencv/blob/master/CHANGELOG.md) page to know what's recently changed.

## Contributions

Feel free to contribute to this project.

If you find a bug or want a feature, but don't know how to fix/implement it, please fill an [issue](https://github.com/AdityaMulgundkar/flutter_opencv/issues).  
If you fixed a bug or implemented a feature, please send a [pull request](https://github.com/AdityaMulgundkar/flutter_opencv/pulls).
