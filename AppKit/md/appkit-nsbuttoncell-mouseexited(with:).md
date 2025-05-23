

- AppKit
- NSButtonCell
-  mouseExited(with:) 

Instance Method

# mouseExited(with:)

Erases the button’s border.

macOS

``` source
@MainActor
func mouseExited(with event: NSEvent)
```

## Parameters 

`event`  

The event object generated by the mouse movement.

## Discussion

This method is called only when the pointer moves off the button and the value of showsBorderOnlyWhileMouseInside is true.

## See Also

### Handling Events and Action Messages

func mouseEntered(with: NSEvent)

Draws the button’s border.

func performClick(Any?)

Simulates the user clicking the button with the pointer.

