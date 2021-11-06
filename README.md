# react-native-placesearch

![npm](https://img.shields.io/npm/dt/react-native-placesearch?style=flat-square)   ![NPM](https://img.shields.io/npm/l/react-native-placesearch?style=flat-square)   ![npm](https://img.shields.io/npm/v/react-native-placesearch?style=flat-square)   ![npm collaborators](https://img.shields.io/npm/collaborators/react-native-placesearch?style=flat-square)

# Installation

```javascript
## NPM
$ npm install react-native-placesearch --save

## or with yarn
$ yarn add react-native-placesearch

```

## Required Package

`$ npm install react-native-vector-icons --save`

## Supporting the project

If you like my work, you can Buy Me a Coffee :wink:

<a href="https://www.buymeacoffee.com/mdrajibsk8" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" width="200" height="50" ></a>

## Video Link

`You want see more video regarding react-native visit my channel. Please make sure to subscribe to my channel, so you don't miss on my future video`

<a href="https://www.youtube.com/watch?v=KvnjOUFK0Cw" target="_blank"><img src="https://github.com/mdrajibsk8/React-Native-Push-Notification-Firebase7/blob/master/de1c91788be0d791135736995109272a.png?raw=true" alt="View Video" width="100" height="100" ></a>




### Demo

Here's a simple example of default ui:


<table>
  <tr>
    <td> <p align="center"><strong>ANDROID</strong></p></td>
    <td><p align="center"><strong>IOS</strong></p></td>
  </tr>
  <tr>
    <td><p align="center"><img src="https://github.com/mdrajibsk8/react-native-placesearch-details/blob/main/androidUi.jpeg?raw=true" alt="Developers' Sin" width="300" height="650"></p></td>
    <td><p align="center"><img src="https://github.com/mdrajibsk8/react-native-placesearch-details/blob/main/IOSui.png?raw=true" alt="Developers' Sin" width="300" height="650"></p></td>
  </tr>
</table>

## Usage
```javascript
import Placesearch from 'react-native-placesearch';

    <Placesearch 
    apikey="your api key" // required *
    SelectedAddress={(data)=>console.log(data)} // required *
    onClose={(data)=>console.log(data)}
    country ="country code" //optional
    coordinate={true} //optional
    removeImg = {true} //optional
    StatusBarColor="Your color code" //option *only for android
    StatusBarStyle="" //option  default "dark-content" *only for android
    ContainerBackgroundColor="Your color code" // optional
    InputContainer = {{'your style goes here'}} //optional
    MainContainer = {{'your style goes here'}} //optional
    ListStyle = {{'your style goes here'}} //optional
    ListTextStyle = {{'your style goes here'}} //optional
    ListIconStyle = {{'your style goes here'}} //optional
    ImgStyle = {{'your style goes here'}} //optional
    Img = {{'your style goes here'}} //optional
    textInput = {{'your style goes here'}} //optional
    placeHolder = {{'type any textInput placeholder as you like'}} //optional
    />

```

### Common props:

| Name             | Opt/Required  | Description                                                                                                                                                            |
| ---------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| apikey           | required   | Valid Google Place api key.                                                                                                                     |
| SelectedAddress           | required   | Accept function - to received the selected address.                                                                                                                     |
| country          | Optional   | Specfied country code if you want search result of specfied country.                                                                         |
| onlyCity      | Optional | Default false. If true you will get search result of only city name. |
| area      | Optional | Default false. If true then you can search against an area or city you just have to pass the coordinate of that area and radius. Example is shown below. |
| coordinate      | Optional | Default false. If true you will get lat lng of selected address |
| removeImg     | Optional | Default false. You can set it to true, if you want to remove background Image. |
| Changeheader  | Optional | Default false. You can set it to true, if you want to change the header the way you want and you have to pass another props called "CustomHeader". Example is show below. |
| ChangList  | Optional | Default false. You can set it to true, if you want to change the list style the way you want and you have to pass another props called "CustomList". Example is show below. |
|ContainerBackgroundColor | Optional | Accept string. |
| MainContainer         | optional  | Accept Object. The styles you want to set for the MainContainer.                      |
| InputContainer         | optional  | Accept Object. The styles you want to set for the InputContainer.                      |
| textInput         | optional  | Accept Object. The styles you want to set for the textInput.                      |
| ListStyle         | optional  | Accept Object. The styles you want to set for the address List.                      |
| ListIconStyle         | optional  | Accept Object. The styles you want to set for the List Icon.                      |
| ListTextStyle         | optional  | Accept Object. The styles you want to set for the List Text.                      |
| ImgStyle         | optional  | Accept Object. The styles you want to set for the Bottom Image.                      |
| Img         | optional  | Image url. if you want to change the bottom image.                      
                            

## Change Header
```javascript
import React, { Component } from 'react';
import { Text, View, TextInput } from 'react-native';
import { Icon } from 'native-base';
import {MY_API_KEY} from '@Constant/ApiKey'
import Placesearch from 'react-native-placesearch';

export default class GooglePlaceSearch extends Component {

  constructor(props) {
    super(props);
    this.state = {}
    this.child = React.createRef();
  } 


  KeyUp = () => {
    this.child.current.searchAddress();
  };

  chngText = (data) => {
    this.child.current.setAddress(data);
  };


  render() {
    return (
           <Placesearch 
            apikey={MY_API_KEY} // required *
            SelectedAddress={(data)=>console.log(data)} // required *
            country ="IN" //optional
            ref={this.child}
            Changeheader={true}
            CustomHeader={
            <View style={{flexDirection:'row',height:45,alignItems:'center'}}>
              <Icon name="search1" type="AntDesign" style={{marginLeft:20,fontSize:20}}/> 
              <TextInput 
                placeholder="Search for Places"
                underlineColorAndroid='transparent'
                autoFocus={true}
                onKeyPress={this.KeyUp}
                onChangeText={(value) => this.chngText(value)}
              />
            </View>
             }
            />
    );
  }
}

```


## Change List Style
```javascript
import React, { Component } from 'react';
import { Text, View, TextInput } from 'react-native';
import { Icon } from 'native-base';
import {MY_API_KEY} from '@Constant/ApiKey'
import Placesearch from 'react-native-placesearch';

export default class GooglePlaceSearch extends Component {

  constructor(props) {
    super(props);
    this.state = {}
  } 

  render() {
    return (
           <Placesearch 
            apikey={MY_API_KEY} // required *
            SelectedAddress={(data)=>console.log(data)} // required *
            country ="IN" //optional
            ChangList = {true}
            CustomList={(item) => 
                <View>
                <View style={{flexDirection:'row',alignItems:'center',paddingHorizontal:5,width:'100%',height:45}}>
                    <Icon name="location-pin" type="Entypo"/>
                    <Text>
                    {item.description}
                    </Text>
                </View>
                </View>
            }
            />
    );
  }
}

```

## Search against Area
```javascript
import React, { Component } from 'react';
import { Text, View, TextInput } from 'react-native';
import { Icon } from 'native-base';
import {MY_API_KEY} from '@Constant/ApiKey'
import Placesearch from 'react-native-placesearch';

export default class GooglePlaceSearch extends Component {

  constructor(props) {
    super(props);
    this.state = {}
  } 

  render() {
    return (
           <Placesearch 
            apikey={MY_API_KEY} // required *
            SelectedAddress={(data)=>console.log(data)} // required *
            country ="IN" //optional
            area={true}
            lat="22.5726"
            lng = "88.3639"
            radius="500" // in meters
            />
    );
  }
}

```
