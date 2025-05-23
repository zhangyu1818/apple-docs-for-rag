

- AppKit
- NSControlTextEditingDelegate
-  control(\_:textView:completions:forPartialWordRange:indexOfSelectedItem:) 

Instance Method

# control(\_:textView:completions:forPartialWordRange:indexOfSelectedItem:)

Invoked to allow you to control the list of proposed text completions generated by text fields and other controls.

macOS

``` source
@MainActor
optional func control(
    _ control: NSControl,
    textView: NSTextView,
    completions words: [String],
    forPartialWordRange charRange: NSRange,
    indexOfSelectedItem index: UnsafeMutablePointer
) -> [String]
```

## Parameters 

`control`  

The control whose cell initiated the message. If the control contains multiple cells, the one that initiated the message is usually the selected cell.

`textView`  

The field editor of the control. You can use this parameter to get the typed text.

`words`  

An array of `NSString` objects containing the potential completions. The completion strings are listed in their order of preference in the array.

`charRange`  

The range of characters the user has already typed.

`index`  

On input, an integer variable with the default value of `0`. On output, you can set this value to an index in the returned array indicating which item should be selected initially. Set the value to `-1` to indicate there should not be an initial selection.

## Return Value

An array of `NSString` objects containing the list of completions to use in place of the array in the `words` parameter. The returned array should list the completions in their preferred order

## Discussion

Each string you return should be a complete word that the user might be trying to type. The strings must be complete words rather than just the remainder of the word, in case completion requires some slight modification of what the user has already typed—for example, the addition of an accent, or a change in capitalization. You can also use this method to support abbreviations that complete into words that do not start with the characters of the abbreviation. The `index` argument allows you to return by reference an index specifying which of the completions should be selected initially.

The actual means of presentation of the potential completions is determined by the complete(_:) method of `NSTextView`.

## See Also

### Related Documentation

func complete(Any?)

Invokes completion in a text view.

