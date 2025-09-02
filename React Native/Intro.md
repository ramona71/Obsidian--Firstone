- jsx syntax
- native wind 
```js
import React from 'react';
import {View, Text} from 'react-native';
import {Text, Stylesheet} from "react-native";

const App=()=>{
	return(
	<View>
		<Text style={style.text}>
	</View>
	);
}
const styles= StyleSheet.create({

});
```
# Expo Vs react native cli
- what i understood
- expo- have download all dependencies (performance fucks up later)
- react native cli- download dependencies only what we need (better performance)
# Components
- View- layout str for other component
	- props
	- flexbox layout (by default)
- Touchable opacity- for button (it's a component)
- touchable highlight
- touchable without feedback
- ActivityIndicator
- button (use touchable's instead)
- flatlist- to render long lists 
	- use when long list
	- for short list - map (like in react)
 - ScrollView- multiple components and view (scrolling container)
 - SafeAreaView
	 - does't work sometimes
	 - use third party one
- Image
- ImageBackground- other components layer on top
	- neither support svg
	- but can download 3rd party package
- Model
- Alert
- Toggle (switch)
- StatusBar
- etc