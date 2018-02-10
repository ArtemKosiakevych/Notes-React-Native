# Async inside array map

```js  
async printFiles () {
    await Promise.all(arr.map(async (i) => {
      const response = await fetch(URL)
      console.log('1')    
    }));
    console.log('2')
  }
```
```
Console: 
1
2
```
Or 
```js
for (let file of files) {
    const response = await fetch(URL)
    console.log('1') 
  }
```

# Map files
```js
const fs = require('fs');

fs.readdir('./YOUR_DIRECTORY/', (err, files) => {
  files.forEach(file => {
    console.log(`${file`);
  });
});
```
