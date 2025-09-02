- base
```js
import { StyleSheet, Text, View } from 'react-native'
import React from 'react'
  
const RootLayout = () => {
  return (
    <View style={styles.container}>
      <Text>RootLayout</Text>
    </View>
  )
}
  
export default RootLayout             // don't forget to export vro
  
const styles = StyleSheet.create({
    container:{
        display:'flex',
        flex: 1,
        alignItems:'center',
        justifyContent:'center'
    }
})
```
- Slot 
```js
import { StyleSheet, Text, View } from 'react-native'
import {Slot} from 'expo-router';                       //here
  
const RootLayout = () => {
  return (
    <>
    <Text>Header</Text>
    <Slot/>                                            //here
    <Text>Footer</Text>
    </>
  );
}
  
export default RootLayout
```
- Stack returning
```js
import { StyleSheet, Text, View } from 'react-native'
import React from 'react'
  
const Profile = () => {
  return (
    <View>
      <Text>Profile</Text>
      <Text>This is profile</Text>
    </View>
  )
}

export default Profile  
```
- to navigate to another page
```js
import {Link} from 'expo-router'                        // this
  
const RootLayout = () => {
  return (
    <View>
      <Link href="/Profile" style={{ color: 'blue' }}>  //this
	      <Text>Go to Profile</Text>
      </Link>
    </View>
  )
}
```
- in href the file should be `"/FileName"` don't copy path, just /filename