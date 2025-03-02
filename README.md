# React Native

## Prerequisites

JDK 17 to 20 is required

## Create ReactNative Cli App

```bash
# Set jdk
sdk default java 17.0.0-tem

# Check if all is well
npx react-native doctor

# Create new react-native app
npx @react-native-community/cli@latest init navigation
```

## Add Navigation support

```bash
npm install react-native-screens react-native-safe-area-context
npm install @react-navigation/native @react-navigation/native-stack
```

## for iOS

```bash
npx pod-install ios
```

## MainActivity setup

```kotlin
// Add imports
import android.os.Bundle;

// Please the following code to the body of MainActivity
  override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(null)
  }

```

## Sample Navigation

```javascript
// In App.js in a new project

import * as React from 'react';
import {View, Text} from 'react-native';
import {NavigationContainer} from '@react-navigation/native';
import {createNativeStackNavigator} from '@react-navigation/native-stack';

function HomeScreen() {
  return (
    <View style={{flex: 1, alignItems: 'center', justifyContent: 'center'}}>
      <Text>Home Screen</Text>
    </View>
  );
}

const Stack = createNativeStackNavigator();

function RootStack() {
  return (
    <Stack.Navigator>
      <Stack.Screen name="Home" component={HomeScreen} />
    </Stack.Navigator>
  );
}

export default function App() {
  return (
    <NavigationContainer>
      <RootStack />
    </NavigationContainer>
  );
}
```

## Run app

```bash
npm run start
npm run android
```
