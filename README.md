# rn-pedometer

React Native pedometer support for iOS version 8.0 and higher and Android. The module is CMPedometer wrapper. More info about CMPedometer can be found in https://developer.apple.com/library/ios/documentation/CoreMotion/Reference/CMPedometer_class/

## Install

```sh

npm install --save npm i rn-pedometer

# Or

yarn add rn-pedometer

```

then make sure it is well **linked**, for this you can run
```sh
yarn react-native link rn-pedometer  
  
# Or

npx react-native link
```
more information [here](https://reactnative.dev/docs/linking-libraries-ios)

## Basic usage

```js
// Import the react-native-pedometer module
import Pedometer from 'rn-pedometer';

// determine pedometer availability
Pedometer.isStepCountingAvailable((error, isAvailable) => {
  // do something
});

Pedometer.isDistanceAvailable((error, isAvailable) => {
  // do something
});

Pedometer.isFloorCountingAvailable((error, isAvailable) => {
  // do something
});

Pedometer.isCadenceAvailable((error, isAvailable) => {
  // do something
});

// start tracking from current time
const now = new Date();
Pedometer.startPedometerUpdatesFromDate(now.getTime(), pedometerData => {
  // do something with pedometer data
});

// query pedometer data from selected date to other selected date
const startDate = new Date();
startDate.setHours(0, 0, 0, 0);
const endDate = new Date();
Pedometer.queryPedometerDataBetweenDates(startDate.getTime(), endDate.getTime(), pedometerData => {
  // do something with pedometer data
});

// stop pedometer updates
Pedometer.stopPedometerUpdates();
```
