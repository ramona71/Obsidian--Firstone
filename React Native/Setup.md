- the bitchass documentation  (it's shit, don't, just chatgpt)
	- [Guides: Overview - Expo Documentation](https://docs.expo.dev/guides/overview/)
# Setup (Expo)
- `npx create-expo-app`
- ` npx expo install expo-router react-native-safe-area-context react-native-screens expo-status-bar expo-linking expo-constants   `
> CTR + P to find files
- delete everything in 'app' folder and make `main/ app/index.jsx` this gonna be home page
- app.json -> scheme: change app name
	- scheme (it's important)
> app.json -> you can change a lot of app related stuff here
- `npx expo start`
	- to start
	- `npx expo start -c` -> -c to clear previous cache  (dont use this)
	- gives a bunch of options like 'a' to go to android studio etc
- Emulator - expo go app , scan the qr 
- `rnfes` in `index.jsx` it's like `!doc` in html -> gives boiler plate base code
	- ![[Pasted image 20250403202042.png]]
- name it to `RootLayout` and start coding
# Common problems
- package.json
	- `npm init -y`
	- `npm install`
- new expo version `npx expo install react-native@0.76.9` and `npx expo install
`