# Changelog

## 1.0.0

- Changed status from alpha to beta.
- Updated documentation to support dark mode.
- Library built using 4024.53.

## 0.3.1

### Disposable

- Renamed the test suite.
- Removed Mock classes that used OnDispose method.
- Fixed typos and text.
- Fixed test project to use specific version (0.3.1) of library.

## 0.3.0

### Disposable

- Removed OnDispose. Due to new information being provided in regards to how FB_exit operates it is no longer possible to implement the OnDispose method in this way. FB_exit does not follow the same rules as an inherited method, and as such would have only called OnDispose at the point when the disposable abstract class was destroyed, NOT at the point that a child class is destroyed. This is a subtle issue which is worth removing this functionality for. If left in it could have resulted in some very hard to find bugs in the user code.

## 0.2.1

### Disposable

- Removed ABSTRACT from Disposable OnDispose. This removes the requirement from the end user to implement the OnDispose if the child class has no requirement for it. You would still look to extend from Disposable to handle the usual lifecycle of disposing and deleting of the object.
