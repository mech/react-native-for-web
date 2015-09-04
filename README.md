# react-native-for-web
A set of classes and react components to make work your react-native app in a browser. (with some limitations obviously)
 - [Slack channel on reactiflux!](https://reactiflux.slack.com/messages/react-native-for-web/details/)

### WARNING!
This package is in pre-pre-pre-pre-pre-pre-pre-pre-pre-beta version! API will not change (as we are emulating the react-native ones ahah) but lots of components or properties could be missing.
We encourage you to help us by reporting those or PR implementation of them! :D

### What limitations?
Since it is all plain javascript, any native binary module won't be supported.
By the way we are planning to provide an extra folder that will contains polyfills and workaround for the exposed api of some of these modules.

### Check out the examples!
- [Sample App](http://koderslab.github.io/react-native-for-web/examples/SampleApp/)

### How can i install this?
- Move into your react-native project folder and install react-native-for-web
```
npm install react-native-for-web
```
- Setup a webpack.config.js file for your project
- Inside your webpack configuration, alias the react-native package to the react-native-for-web package, and setup the external for the image loader.
```javascript
{
  // other webpack config
  resolve: {
    alias: {
      "react-native": "react-native-for-web"
    }
  }
  // setup the macro to resolve require("image!...")
  externals: [
    require("react-native-for-web/src/macro/image")
  ],
}
```
- Run webpack
- Create an HTML document, with a div with an id="app" including the bundled webpack script and linking the css stylesheet node_modules/react-native-for-web/style.css
- Report any error to let us improve and help you! :D

### Building the library
Move into the package folder and run in your terminal:
```
npm run build
```

----------
## Supported Classes & Components

 - [X] StyleSheet
   - [X] create

 - [X] AppRegistry
   - [X] getAppKeys
   - [X] registerComponent
   - [X] registerConfig
   - [X] registerRunnable
   - [X] runApplication

 - [ ] View
   - [ ] accessible
   - [ ] accessibilityLabel
   - [ ] accessibilityComponentType
   - [ ] accessibilityLiveRegion
   - [ ] accessibilityTraits
   - [ ] onAcccessibilityTap
   - [ ] onMagicTap
   - [X] testID
   - [ ] onMoveShouldSetResponder
   - [ ] onResponderGrant
   - [ ] onResponderMove
   - [ ] onResponderReject
   - [ ] onResponderRelease
   - [ ] onResponderTerminate
   - [ ] onResponderTerminationRequest
   - [ ] onStartShouldSetResponder
   - [ ] onStartShouldSetResponderCapture
   - [ ] onLayout
   - [X] pointerEvents
   - [X] style
   - [X] removeClippedSubviews *not planned to support*
   - [X] renderToHardwareTextureAndroid *not planned to support*
   - [X] shouldRasterizeIOS *not planned to support*
   - [ ] collapsable

 - [ ] Text
   - [ ] numberOfLines
   - [ ] onLayout
   - [ ] onPress
   - [X] suppressHighlighting
   - [X] style
   - [X] testID
   - [ ] allowFontScaling