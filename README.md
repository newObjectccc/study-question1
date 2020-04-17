#### 一点关于react-native渲染问题

```javascript
/**
 * Sample React Native App
 * https://github.com/facebook/react-native
 *
 * @format
 * @flow strict-local
 */

import React from 'react';
import {
  SafeAreaView,
  StyleSheet,
  ScrollView,
  View,
  Text,
  StatusBar,
  Button,
  TextInput,
  TouchableOpacity,
  FlatList,
} from 'react-native';

import {
  Header,
  LearnMoreLinks,
  Colors,
  DebugInstructions,
  ReloadInstructions,
} from 'react-native/Libraries/NewAppScreen';

import AddItem from './components/add-item'

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
      textValue: 'hhhhlll',
      itemArr: [0],
    }
  }
  add() {
    let count = this.state.count;
    let itemArr = this.state.itemArr;
    count++;
    itemArr.push(count);
    this.setState({
      count,
      itemArr
    });
    console.log(itemArr)
  }
  renderListFunc(item) {
    return <AddItem title="xxx" idx={item.index} />
    // console.log(this.refs.flatList)
  }
  render() {
    return (
      <View style={styles.wrap}>
        // 不知道为啥，下面三个additem组件都无法渲染，不是很懂，所以做一个记录；
        // 猜测是因为在上面函数体中return了additem组件导致的；
        // 也有可能是因为下面采用了FlatList中的renderItem使用了additem导致的；
        // 但也有可能都不是 。。。。   哎。。。 我太菜了。。。后面慢慢研究
        <AddItem title="xxx" idx="99999" />
        <AddItem title="xxx" idx="99999" />
        <AddItem title="xxx" idx="99999" />
        <Button title="Axxx" onPress={() => this.add()}></Button>
        <Text>{this.state.count}</Text>
        <Text>{this.state.itemArr}</Text>
        <FlatList
          data={this.state.itemArr}
          renderItem={(item) => this.renderListFunc(item)}
          keyExtractor={(item, index) => index.toString()}
        />
      </View>
    );
  }
};

const styles = StyleSheet.create({
  wrap: {
    flex: 1,
    backgroundColor: 'pink'
  }
});

export default App;

```

