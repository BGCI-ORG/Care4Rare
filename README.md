# Care4Rare
## Building
## Publishing
### Android
1.  cordova build android --release\
Exports app-release-unsigned.apk in platforms\android\app\build\outputs\apk\release
2.  Run `jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore care4rare-key.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk care4rare-key`
This signs the apk in place.
3.  Run `zipalign -v 4 platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk platforms/android/app/build/outputs/apk/release/app-release.apk`\
      -The apk is now ready here: platforms/android/app/build/outputs/apk/release/app-release.apk\
      -I had to do this first. I'm hoping it was a one-time thing. `echo "export PATH=\$PATH:~/Library/Android/sdk/build-tools/27.0.3/" >> ~/.bash_profile && . ~/.bash_profile`


