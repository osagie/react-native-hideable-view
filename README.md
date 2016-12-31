### React Native Hideable View
---

A component for React Native that can show/hide its child components.

## Installation

`npm install --save react-native-hideable-view`

## Usage

```
import HideableView from 'react-native-hideable-view';

<HideableView visible={boolean}>
  <YourView />
</HideableView>
```

## Props

Prop              | Type     | Default  | Description
----------------- | -------- | -------- | --------------------
visible           | bool     | false    | Show/Hide the View
duration          | int      | 500      | Animation time (ms)
removeWhenHidden  | bool     | false    | Unmount component when hidden
noAnimation       | bool     | false    | If true, no animation

## Example

```
import React, { Component } from 'react';
import { View, Text, TouchableOpacity  } from 'react-native';

import HideableView from 'react-native-hideable-view';

class Example extends Component {
    constructor(props) {
        super(props);
        this.state = {
            visible: false
        };
        this.toggle = this.toggle.bind(this);
    }

    toggle() {
        this.setState({
            visible: !this.state.visible
        });
    }

    render() {
        return (
            <View style={styles.container}>
                <Text style={styles.title}>
                    I am always here.
                </Text>
                <HideableView hidden={this.state.hidden}>
                    <Text>
                      I appear and disappear at your behest.
                    </Text>
                </HideableView>
                <TouchableOpacity onPress={this.toggle}>
                    <Text>{this.state.visible ? 'Hide' : 'Show'}</Text>
                </TouchableOpacity>
            </View>
        );
    }
}
```
