# I_Disposable Interface

## Definition

|             |                            |
| ----------- | -------------------------- |
| Namespace   | mobject-disposable         |
| Library     | mobject-disposable         |
| Inheritance | \_\_System.IQueryInterface |
| Implements  |                            |

## Remarks

The I_Disposable interface should be implemented by any class which supports the Dispose() method.

## Example

```declaration
FUNCTION_BLOCK MyObject IMPLEMENTS I_Disposable
VAR
END_VAR
```

```body
//... no code should go here.
```

```declaration
METHOD Dispose
```

```body

// Here you should dispose of any objects your object owns or manages.
// ...

```

## Methods

### Dispose()

Used to trigger the object for deletion.

#### Parameters

N/A

#### Return

N/A

#### Usage

```example
myObject.Dispose()
```
