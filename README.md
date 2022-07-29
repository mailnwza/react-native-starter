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

### Install the Code into Project

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
  add `options={{ headerShown: false }}` in Screen tag.

```js
<Tab.Screen
  name="Home"
  component={HomeScreen}
  options={{ headerShown: false }}
/>
```

For production environments... soon
