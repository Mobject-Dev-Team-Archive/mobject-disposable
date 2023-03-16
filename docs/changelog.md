# Changelog

## 0.3.0

### Disposable

- Removed OnDispose. Due to new information being provided in regards to how fb_exit operates it is no longer possible to implement the OnDispose method in this way. fb_exit is not follow the same rules as an inherited method, and as such would have only called OnDispose at the point when the disposable abstract class was destroyed. NOT at the point that a child class is destroyed. This is a subtle issue which is worth removing this functionality for. If left in could have resulted in some very hard to find bugs in the user code.

## 0.2.1

### Disposable

- Removed ABSTRACT from Disposable OnDispose. This removes the requirement from the end user to implement the OnDispose if the child class has no requirement for it. You would still look to extend from Disposable to handle the usual lifecycle of disposing and deleting of the object.
