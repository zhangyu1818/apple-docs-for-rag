

- JavaScriptCore
- JSContext
-  evaluateScript(\_:withSourceURL:) 

Instance Method

# evaluateScript(\_:withSourceURL:)

Executes the specified JavaScript code, treating the specified URL as its source location.

iOS 8.0+iPadOS 8.0+Mac Catalyst 13.1+macOS 10.10+tvOS 9.0+visionOS 1.0+

``` source
func evaluateScript(
    _ script: String!,
    withSourceURL sourceURL: URL!
) -> JSValue!
```

## Parameters 

`script`  

The JavaScript source code to evaluate.

`sourceURL`  

A URL to be considered as the script’s origin.

## Return Value

The last value generated by the script. Note that a script can result in the JavaScript value `undefined`.

## Discussion

Evaluating a script runs any top-level code and adds function or object definitions to the context’s global object.

The `sourceURL` parameter is informative only; debuggers may use this URL when reporting exceptions.

## See Also

### Evaluating scripts

func evaluateScript(String!) -> JSValue!

Executes the specified JavaScript code.

