

- Foundation
- NSUserNotification
-  isPresented Deprecated

Instance Property

# isPresented

Specifies whether the user notification has been presented.

macOS 10.8–11.0Deprecated

``` source
var isPresented: Bool { get }
```

Deprecated

All NSUserNotifications API should be replaced with UserNotifications.frameworks API

## Discussion

In some cases, for example when your application is frontmost, the notification center may decide not to actually present a delivered notification. In that case, the value of this property is false. It is set to true if the notification was presented according to user preferences.

## See Also

### Delivery Information

var isRemote: Bool

Specifies whether the remote was generated by a push notification.

Deprecated

var soundName: String?

Specifies the name of the sound to play when the notification is delivered.

Deprecated

