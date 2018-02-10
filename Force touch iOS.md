https://github.com/madriska/react-native-quick-actions

Set quick action from info.plist
This action available as default
This is default action - title
forceIcon - Icon name from Images.xcassets

```
	<key>UIApplicationShortcutItems</key>
	<array>
		<dict>
			<key>UIApplicationShortcutItemIconFile</key>
			<string>forceIcon</string>
			<key>UIApplicationShortcutItemTitle</key>
			<string>This is default action</string>
			<key>UIApplicationShortcutItemType</key>
			<string>$(PRODUCT_BUNDLE_IDENTIFIER).action</string>
		</dict>
	</array>
```

Set action from JS code

```
    QuickActions.setShortcutItems([
      {
        type: 'custom', // Required
        title: 'Dynamic Action', // Optional, if empty, `type` will be used instead
        subtitle: 'This action created from app',
        icon: 'forceIcon', // Pass any of UIApplicationShortcutIconType<name>
        userInfo: {
          url: 'app://addData' // provide custom data
        }
      }
    ]);
```

For handling action onPress do

```
import {DeviceEventEmitter} from 'react-native'

DeviceEventEmitter.addListener(
      'quickActionShortcut', function(data) {
        console.log(data);
	// DO something
      });
```
