## Certificates for beta


## Manual
Launch Xcode -> disable signing automatic -> choose adhoc
If no error with distribution cert you can fastlane beta

If error you need to create cert (you need admin permission for your dev team)

Login to apple developer -> account -> Certificates -> click plus -> create distribution cert (App Store and Ad Hoc
) if it says "Maximum number of certificates generated" then revoke one of distribution cert.

You should Generate your certificate.

Launch keychain and keychain -> cert assistant -> Request cert from …
Enter your email and chose save to disk

Then return to apple developer account and choose file you just created -> continue

Download iOS Distribution and click it (it saves to keychain)

Then go to iOS Provisioning Profiles -> click on just created AdHoc distribution cert -> edit -> choose under Certificates your created cert -> generate -> download -> click on mobileprovisionprofile (it saves to keychain) -> Done

Congratulation now in Xcode you can Preference -> accounts -> choose your acc -> Download manual profiles and choose in signing field adhoc

## Using fastlane match

If you store your profiles on remote repo, configure Matchfile and type `fastlane match adhoc`