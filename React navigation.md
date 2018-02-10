# React Navigation

## Install react-navigation https://reactnavigation.org/docs/intro/

## Minimal example include tabs and stack navigator in first tab

Create all components : first tab, second tab, first screen, second screen
(screens will be in first tab)

in app.js
```js
import { TabNavigator } from 'react-navigation';
import FirstTab from './FirstTab';
import SecondTab from './SecondTab';
```
before registry
```js
const App = TabNavigator({
  firstTab: { screen: FirstTab },
  secondTab: { screen: SecondTab },
});
```
FirstTab.js
```js
import { StackNavigator } from 'react-navigation';
import FirstScreen from './FirstScreen';
import SecondScreen from './SecondScreen';

FirstTab = StackNavigator({
  firstScreen: { screen: FirstScreen },
  secondScreen: { screen: SecondScreen },
});
export default FirstTab
```
FirstScreen.js
```js
// for transition to secondScreen with prop {user} use:
this.props.navigation.navigate('secondScreen', { user: 'Lucy' })

// For getting user do:
const { params } = this.props.navigation.state;
const user = params.user

// change navigationOptions depending of params:
static navigationOptions = ({ navigation }) => ({
    title: `Send ${navigation.state.params.item.title}`,
  });
```
OnRight action:
```js
  componentDidMount() {
    this.props.navigation.setParams({ handleRight: this.myFunc });
  }

  static navigationOptions = ({ navigation, screenProps }) => ({
    headerRight: (
      <TouchableOpacity onPress={()=> navigation.state.params.handleRight()}>
        <FontAwesome style={styles.rightIcon}>{Icons.ellipsisV}</FontAwesome>
      </TouchableOpacity>
    )
  });
```
