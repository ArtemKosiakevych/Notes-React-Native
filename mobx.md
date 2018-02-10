# Short how to use guide 

1. Install mobx, mobx-react, autobind-decorator
2. Create store

```js
import { observable, action, } from 'mobx'
import { persist } from 'mobx-persist'
import autobind from 'autobind-decorator'

@autobind
class store {
  @persist @observable title = 'Second Tab';

  @action setTitle(val){
    this.title = val
  }
}
export default new store();
```

 3. Store data
 ```js
 import store from './state/store'
...
// if you want to store data to AsyncStorage do
// `install mobx-persist`
import { create } from 'mobx-persist'
const hydrate = create({ storage: AsyncStorage })
hydrate('title', store)
...
// do action
store.setTitle(’title’)
 ```
4. Use stored data
```js
import store from './state/store'
import {observer} from 'mobx-react/native';
// annotate class
@observer
class….
// and use title
const title = store.title
```
