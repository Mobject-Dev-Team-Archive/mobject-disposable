# Dispose Abstract Class

## Definition

|             |                                 |
| ----------- | ------------------------------- |
| Namespace   | mobject-disposable              |
| Library     | mobject-disposable              |
| Inheritance | None                            |
| Implements  | [I_Disposable](i-disposable.md) |

## Remarks

The Disposable Abstract Class is a utility class that allows objects to handle being destroyed in a consistent manor.

## Example

```declaration
FUNCTION_BLOCK MyObject EXTENDS Disposable
VAR
END_VAR
```

```body
//... no code should go here.
```

```declaration
METHOD OnDispose : BOOL
VAR_INPUT
	CalledExplicitly : BOOL; // true if disposal was triggered from Dispose()
END_VAR
```

```body

// Here you should dispose of any objects your object owns or manages.
// ...

```

## Methods

### Dispose()

Will trigger the object for deletion.

#### Parameters

N/A

#### Return

N/A

#### Usage

```example
myObject.Dispose()
```

### Protected OnDispose() : BOOL;

This method should be implemented by the concrete class if that class needs to dispose of other components.

OnDispose will be called explicitly by the Dispose() method, or from someone calling \_\_DELETE on the object, or by TwinCAT when it destroys the object.

#### Parameters

| Parameters       | Datatype | Description                                                            |
| ---------------- | -------- | ---------------------------------------------------------------------- |
| CalledExplicitly | BOOL     | This boolean will return True if disposal was triggered from Dispose() |

#### Return

| Datatype | Description                                                                                                                                    |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| BOOL     | Returning true will cancel the disposal. If you cancel it, then you must call Dispose or \_\_DELETE when you are ready for the final disposal. |

#### Usage

```declaration
METHOD OnDispose : BOOL
VAR_INPUT
	CalledExplicitly : BOOL; // true if disposal was triggered from Dispose()
END_VAR
```

```body
// your code goes here...
// you should dispose any dynamic objects your object is managing
// in most cases you can simply return from this method.
RETURN;

// however...
// if the releasing of objects is not possible in a single cycle then you must return TRUE
 OnDispose := true;
// This will suppress the final deletion and a second call of Dispose() will be required.
// The second call of Dispose() will not re-trigger this method.
```
