# I_Disposable Interface

## Definition

|             |                            |
| ----------- | -------------------------- |
| Namespace   | mobject-disposable         |
| Library     | mobject-disposable         |
| Inheritance | \_\_System.IQueryInterface |
| Implements  |                            |

## Remarks

The Disposable Abstract Class is a utility class that allows objects to handle being destroyed in a consistent manor.

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
VAR_INPUT
END_VAR
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
