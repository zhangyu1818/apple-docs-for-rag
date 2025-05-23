

- AppKit
-  NSControlTextEditingDelegate 

Protocol

# NSControlTextEditingDelegate

A set of optional methods implemented by delegates of NSControl subclasses to respond to editing actions.

macOS

``` source
protocol NSControlTextEditingDelegate : NSObjectProtocol
```

## Topics

### Validating a Control’s Value

func control(NSControl, isValidObject: Any?) -> Bool

Invoked when the insertion point leaves a cell belonging to the specified control, but before the value of the cell’s object is displayed.

func control(NSControl, didFailToValidatePartialString: String, errorDescription: String?)

Invoked when the formatter for the cell belonging to `control` (or selected cell) rejects a partial string a user is typing into the cell.

### Responding to Text Formatting

func control(NSControl, didFailToFormatString: String, errorDescription: String?) -> Bool

Invoked when the formatter for the cell belonging to the specified control cannot convert a string to an underlying object.

### Responding to Text Editing

func control(NSControl, textShouldBeginEditing: NSText) -> Bool

Invoked when the user tries to enter a character in a cell of a control that allows editing of text (such as a text field or form field).

func control(NSControl, textShouldEndEditing: NSText) -> Bool

Invoked when the insertion point tries to leave a cell of the control that has been edited.

### Working with Text Completion

func control(NSControl, textView: NSTextView, completions: [String], forPartialWordRange: NSRange, indexOfSelectedItem: UnsafeMutablePointer&lt;Int>) -> [String]

Invoked to allow you to control the list of proposed text completions generated by text fields and other controls.

### Working with Key Bindings

func control(NSControl, textView: NSTextView, doCommandBy: Selector) -> Bool

Invoked when users press keys with predefined bindings in a cell of the specified control.

### Instance Methods

func controlTextDidBeginEditing(Notification)

Tells the delegate that the control started editing its text content.

func controlTextDidChange(Notification)

Tells the delegate that the control made changes to its text content.

func controlTextDidEndEditing(Notification)

Tells the delegate that the control finished editing its text content and committed the changes.

## Relationships

### Inherits From

- NSObjectProtocol

### Inherited By

- NSComboBoxDelegate
- NSMatrixDelegate
- NSOutlineViewDelegate
- NSSearchFieldDelegate
- NSTableViewDelegate
- NSTextFieldDelegate
- NSTokenFieldDelegate

## See Also

### Management

protocol NSTextFieldDelegate

A protocol that a text field delegate can use to control its field editor action menu.

