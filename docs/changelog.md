# Changelog

## 0.2.1

### Disposable

- Removed ABSTRACT from Disposable OnDispose. This removes the requirement from the end user to implement the OnDispose if the child class has no requirement for it. You would still look to extend from Disposable to handle the usual lifecycle of disposing and deleting of the object.
