## Create React native app on bitrise.io

 # Use hints from bitrise.io and configure git URL etc.
 Don't forget about Settings-> Stack selector and Project Type Selector
 # Env Variables
 If you are using match add to vars `MATCH_PASSWORD` (passphase from repo with profiles)
 Add `FASTLANE_PASSWORD` (pass from fastlane account)

 For Android don't forget configure KEY_STORE_SECRETS (key store alias, pass, etc.)
 # Configure Triggers 
 In Settings get url for hook and add this url to hooks on GitLab/GitHub
 # Workflow/bitrise.yml
 You can configure this on bitrise.io but we store bitrise.yml on our repo and we run flow from repo.
 Example bitrise.yml under CI_CD folder (bitrise.yml)

 bitrise.yml will run bitrise.yml from ios/ and android/ folder, so you should store those files in the repo
 Exmaples for Android bitrise.yml and IOS one are under CI_CD folder
 bitrise.yml from IOS/Android file will run lane: beta from Fastfile.
 You can find Fastfile from IOS/Android under CI_CD folder 

 # Thats all, push to repo will trigger beta lane from Fastfile: sign, build app and upload to Beta.

 #P.S. Use bitrise CLI for testing =)



 
