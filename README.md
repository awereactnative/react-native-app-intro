# react-native-app-intro
react-native-app-intro is a react native component implementing a parallax effect welcome page using base on [react-native-swiper](https://github.com/leecade/react-native-swiper) , similar to the one found in Google's app like Sheet, Drive, Docs...

# react-native-app-intro-slider Screen Capture


### Support android
<img src="http://i.giphy.com/3o6ozjLoOnYTXfzJgQ.gif">


### Installation

```bash
$ npm i react-native-app-intro --save
```



<img src="http://i.giphy.com/l3V0khy22aUviTTaM.gif">

```javascript
import React, {useState} from 'react';
import {
  SafeAreaView, StyleSheet, View, Text, Button, Image
} from 'react-native';

import AppIntroSlider from 'react-native-app-intro-slider';


const App = () => {
  const [showRealApp, setshowRealApp] =useState(false)


  const onSkip = () =>{
    setshowRealApp(true)
  }
  const onDone = () =>{
    setshowRealApp(true)
  }
  const renderItem = ({item}) => {
    return(
      <View
      style={{
        flex:1, 
        backgroundColor: item.backgroundColor,
        alignItems: 'center',
        justifyContent: 'space-around',
        paddingBottom: 100
        }}
        >
          <Text style={styles.introTittleStyle}>
          {item.title}
          </Text>

          <Image 
          style={styles.introImageStyle}
          source={item.image}
          />

          <Text style={styles.introtextstyle}>
            {item.text}
          </Text>
        </View>
    )
      
}
  return (
    <>
     {
       showRealApp ?(
        <SafeAreaView style={styles.container}>
        <View style={styles.container}>
          <Text style={styles.titleStyle}>
            React Native App Intro Slider using AppIntroSlider
            </Text>
          <Text style={styles.paragraphStyle}>
            Welcome to the App!!!
            </Text>
            <Button
              title="show intro slider again"
              onPress= {() => setshowRealApp(false)}
            />
        </View>
      </SafeAreaView>
       ):(
         <AppIntroSlider
          data={slides}
          renderItem={renderItem}
          onDone={onDone}
          onSkip={onSkip}
          showSkipButton={true}
          bottomButton
         />
       )
     }
    </>
  );
};

export default App;

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    padding: 10,
    justifyContent: 'center',
  },
  titleStyle: {
    padding: 10,
    textAlign: 'center',
    fontSize: 18,
    fontWeight: 'bold',
  },
  introTittleStyle: {
    fontSize: 25,
    color : 'white',
    textAlign: 'center',
    marginBottom: 16,
    fontWeight: 'bold'
  },
  introImageStyle: {
    width: 200,
    height: 200
  },
  introtextstyle: {
    fontSize: 18,
    color: 'white',
    textAlign:'center',
    paddingVertical: 30
  }
}
);

const slides = [
  {
    key: 's1',
    text: 'Best Phone offers',
    title: 'Buy New Phone',
    image: {
      uri:
        'https://raw.githubusercontent.com/tranhonghan/images/main/intro_mobile_recharge.png',
    },
    backgroundColor: '#20d2bb',
  },
  {
    key: 's2',
    title: 'Flight Booking',
    text: 'Upto 25% off on Domestic Flights',
    image: {
      uri:
        'https://raw.githubusercontent.com/tranhonghan/images/main/intro_flight_ticket_booking.png',
    },
    backgroundColor: '#febe29',
  },
  {
    key: 's3',
    title: 'Great Offers',
    text: 'Enjoy Great offers on our all services',
    image: {
      uri:
        'https://raw.githubusercontent.com/tranhonghan/images/main/intro_discount.png',
    },
    backgroundColor: '#22bcb5',
  },
  {
    key: 's4',
    title: 'Best Deals',
    text: ' Best Deals on all our services',
    image: {
      uri:
        'https://raw.githubusercontent.com/tranhonghan/images/main/intro_best_deals.png',
    },
    backgroundColor: '#3395ff',
  },
  {
    key: 's5',
    title: 'Bus Booking',
    text: 'Enjoy Travelling on Bus with flat 100% off',
    image: {
      uri:
        'https://raw.githubusercontent.com/tranhonghan/images/main/intro_bus_ticket_booking.png',
    },
    backgroundColor: '#f6437b',
  },
  {
    key: 's6',
    title: 'Train Booking',
    text: ' 10% off on first Train booking',
    image: {
      uri:
        'https://raw.githubusercontent.com/tranhonghan/images/main/intro_train_ticket_booking.png',
    },
    backgroundColor: '#febe29',
  },
];
```

