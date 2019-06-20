# react-native-navigation-twopane

Custom two-pane navigator for [React Navigation](https://reactnavigation.org/). Implements master/detail pattern. Built on top of Stack navigator.

## Usage
The only difference from Stack navigator is that in routes config additional field `emptyRightPaneName` should be set.

```
import {
    createAppContainer,
    createBottomTabNavigator,
} from 'react-navigation'; 
import {createTwoPaneNavigator} from "react-native-navigation-twopane";


const routes = {
    Item: {
        screen: ItemScreen,
    },
    List: {
        screen: ListScreen,
    },
    Details: {
        screen: DetailsScreen,
    },
    NoChats: {
        screen: NoChatsScreen,
    },
};


const routesConfig = {
    initialRouteName: 'List',
    emptyRightPaneName: 'NoChats'
};

const MasterDetailNavigator = createTwoPaneNavigator(routes, routesConfig);

const AppContainer = createAppContainer(MasterDetailNavigator);

export default class App extends React.Component {
    render() {
        return <AppContainer/>
    }
}

```
