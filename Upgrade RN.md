# Let's upgrade React Native version of existing project

### Step 1 Install tool
 - `npm install -g react-native-git-upgrade`
### Step 2 Run upgrade
 - Inside your working directory, run `react-native-git-upgrade` (with old RN and react version)
### Step 3 Log .patch file
 - `ls $TMPDIR/react-native-git-upgrade` - you'll find your corresponding .patch file, the name will correspond to the versions you're upgrading between.
### Step 4 Apply .patch changes
 - `git apply <path to patch> --reject` - e.g. `<path to patch>` --> `$TMPDIR/react-native-git-upgrade/upgrade_0.46.4_0.53.0.patch`
### Step 5 Upgrade all modules
 - `npm i -g npm-check-updates`
 - `ncu`
 - `ncu -u`
 - `git clean -dfx`
 - `npm i && cd ios && pod install $$ cd ..`
### Step 6
 - Almost finished =) Fix all left errors by googling and enjoy!
