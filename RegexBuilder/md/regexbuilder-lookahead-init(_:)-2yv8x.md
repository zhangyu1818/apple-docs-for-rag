

- RegexBuilder
- Lookahead
-  init(\_:) 

Initializer

# init(\_:)

Creates a lookahead from the regex generated by the given builder closure.

iOS 16.0+iPadOS 16.0+Mac Catalyst 16.0+macOS 13.0+tvOS 16.0+visionOSwatchOS 9.0+

``` source
init(@RegexComponentBuilder _ component: () -> R) where Output == R.RegexOutput, R : RegexComponent
```

