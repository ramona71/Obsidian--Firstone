- this https://www.nativewind.dev/getting-started/installation
- `npx create-expo-stack@latest --nativewind` in the beginning or
	- `npm i nativewind` after making the app
	- `npm install nativewind tailwindcss@^3.4.17 react-native-reanimated@3.16.2 react-native-safe-area-context` 
	- cuz we need tailwind too 
	- `npx tailwind init` to make config file
	- replace empty content in tailwind.config file with this ->`content: ["./app/**/*.{js,jsx,ts,tsx}"],` 
	- if babel.config.js is not present then
		- `npm install --save-dev babel-preset-expo`
		- and make a babel file https://chatgpt.com/c/67eeaa83-d410-8003-b773-b51850bce9a9
```js       // babel
module.exports = function(api) {
    api.cache(true);
    return {
      presets: ['babel-preset-expo'],
      plugins: ['tailwindcss-react-native/babel'],      
    }
};
```
> DONE !!!!!!!

