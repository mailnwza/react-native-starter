# Start React-Native Project

- [React-Native](https://reactnative.dev/)
- [ReactJS](https://reactjs.org/) - Javascript Library
- [Styled-Components](https://styled-components.com/) - great UI boilerplate for web apps
- [Visual Studio Code](https://code.visualstudio.com/) - awesome web-based text editor
- [Yarn](https://yarnpkg.com/) - Yarn is a package manager for your code

## Installation

Requires [Node.js](https://nodejs.org/) v16.16+ to run.
Requires [Yarn](https://yarnpkg.com/) v.1.23+

### Install the dependencies and devDependencies.

- Install for react-navigation/bootom-tabs

```sh
yarn add @react-navigation/native @react-navigation/native-stack react-native-screens react-native-safe-area-context @react-navigation/bottom-tabs @react-native-community/masked-view react-native-gesture-handler react-native-reanimated
```

- Install for UI CSS ([Styled-Components](https://styled-components.com/))

```sh
yarn add styled-components
```

- Install for SVG Icon ([react-native-svg](https://www.npmjs.com/package/react-native-svg))

```js
yarn add react-native-svg
```

and Link native code :

```js
cd ios && pod install
```

## Example the Code in Project

#### 1. react-navigation/bottom-tabs

create `src` folder in project and create `navigation` folder in src and create new file name is `Tabs`

#### Tabs.js

```js
import React from 'react';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';

import HomeScreen from '../screens/Home';

const Tab = createBottomTabNavigator();

const Tabs = () => {
  return (
    <Tab.Navigator>
      <Tab.Screen
        name="Home"
        component={HomeScreen}
        options={{ headerShown: false }}
      />
    </Tab.Navigator>
  );
};

export default Tabs;
```

import Tabs.js in App.js

#### App.js

```js
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import Tabs from './src/navigation/Tabs';

const App = () => {
  <NavigationContainer>
    <Tabs />
  </NavigationContainer>;
};
```

#### Options

- remove header screen in `@react-navigation/bottom-tabs`
  > `options={{ headerShown: false }}` in Screen tag.

```js
<Tab.Screen
  name="Home"
  component={HomeScreen}
  options={{ headerShown: false }}
/>
```

- add icon/image in `@react-navigation/bottom-tabs`
  > `options={{ tabBarIcon: () => <View>...</View> }}` in Screen tag.

```js
<Tab.Screen
  name="Home"
  component={HomeScreen}
  options={{ tabBarIcon: () => <View><Image source={...} /></View> }}
/>
```

#### 2. using SVG Icon BY JSX (react-native-svg)

[convert SVG code](https://react-svgr.com/playground/?native=true) to react-native-svg.

```js
import Svg, { Path } from 'react-native-svg';

const SVG = () => {
  return (
    <Svg width={25} height={24} fill="none" xmlns="http://www.w3.org/2000/svg">
      <Path
        d="m22.243 12.331-9-10c-.379-.422-1.107-.422-1.486 0l-9 10a.998.998 0 0 0-.17 1.076c.16.361.518.593.913.593h2v7a1 1 0 0 0 1 1h3a1 1 0 0 0 1-1v-4h4v4a1 1 0 0 0 1 1h3a1 1 0 0 0 1-1v-7h2a.997.997 0 0 0 .743-1.669Z"
        fill="#222"
      />
    </Svg>
  );
};

export default SVG;
```

For production environments... soon
