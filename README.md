# simple-react-native-snap-carousel
Simple example for react-native-snap-carousel

# Set up

### Is this a bug report, a feature request, or a question?

Feature request


### Example is overly complex

Thanks for a great package.
Can I suggest adding a simple and easy to understand example?

```
npx react-native init carousel-simple-example
cd carousel-simple-example
npm install react-native-snap-carousel
```

App.js

```
import React from 'react';
import {
  Text, 
  View,
  SafeAreaView } from 'react-native';
import Carousel from 'react-native-snap-carousel';

export default class App extends React.Component {
 
    constructor(props){
        super(props);
        this.state = {
          activeIndex:0,
          carouselItems: [
          {
              title:"Item 1",
              text: "Text 1",
          },
          {
              title:"Item 2",
              text: "Text 2",
          },
          {
              title:"Item 3",
              text: "Text 3",
          },
          {
              title:"Item 4",
              text: "Text 4",
          },
          {
              title:"Item 5",
              text: "Text 5",
          },
        ]
      }
    }

    _renderItem({item,index}){
        return (
          <View style={{
              backgroundColor:'floralwhite',
              borderRadius: 5,
              height: 250,
              padding: 50,
              marginLeft: 25,
              marginRight: 25, }}>
            <Text style={{fontSize: 30}}>{item.title}</Text>
            <Text>{item.text}</Text>
          </View>

        )
    }

    render() {
        return (
          <SafeAreaView style={{flex: 1, backgroundColor:'rebeccapurple', paddingTop: 50, }}>
            <View style={{ flex: 1, flexDirection:'row', justifyContent: 'center', }}>
                <Carousel
                  layout={"default"}
                  ref={ref => this.carousel = ref}
                  data={this.state.carouselItems}
                  sliderWidth={300}
                  itemWidth={300}
                  renderItem={this._renderItem}
                  onSnapToItem = { index => this.setState({activeIndex:index}) } />
            </View>
          </SafeAreaView>
        );
    }
}
```

Running on a device

`npx react-native run-android`
`npx react-native run-ios`
