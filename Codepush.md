# Codepush
https://microsoft.github.io/code-push/

1. sudo npm install -g code-push-cli
2. code-push register
3. code-push app add <appName>
4. npm install --save react-native-code-push@latest
5. react-native link react-native-code-push
6. Wrap your main Component in Codepush

```js
import codePush from 'react-native-code-push';
const codePushOptions = {
  updateDialog: true,
  deploymentKey: <ProductionKey>,
  checkFrequency: codePush.CheckFrequency.ON_APP_RESUME ,
  installMode: codePush.InstallMode.ON_NEXT_RESUME};

export default codePush(codePushOptions)(App);
````

For check your keys run
`code-push deployment ls <appName> -k`

For push update version (Stage) run
`code-push release-react <appName> ios` or
`code-push release-react <appName> android`

For push update version (Production) after Stage run
`code-push promote <appName> Staging Production`

After reloading user will see alert for updating app
