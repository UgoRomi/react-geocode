# react-geocode

A React module to transform a description of a location (i.e. street address, town name, etc.) into geographic coordinates (i.e. latitude and longitude) and vice versa.

This module uses [Google Maps Geocoding API](https://developers.google.com/maps/documentation/geocoding/intro) and requires an API key for purposes of quota management. Please check [this link](https://developers.google.com/maps/documentation/geocoding/get-api-key) out to obtain your API key.

### Install

```shell
npm i react-geocode-multi-language
```

### Example

```js
import Geocode from 'react-geocode';

// set Google Maps Geocoding API for purposes of quota management. Its optional but recommended.
Geocode.setApiKey('xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx');

// set response language. Defaults to english.
Geocode.setLanguage('en');

// Enable or disable logs. Its optional.
Geocode.enableDebug();

// Get address from latidude & longitude.
Geocode.fromLatLng('48.8583701', '2.2922926').then(
  response => {
    const address = response.results[0].formatted_address;
    console.log(address);
  },
  error => {
    console.error(error);
  }
);

// Get latidude & longitude from address.
Geocode.fromAddress('Eiffel Tower').then(
  response => {
    const { lat, lng } = response.results[0].geometry.location;
    console.log(lat, lng);
  },
  error => {
    console.error(error);
  }
);
```

#### Methods

| Method      | Arguments                  |   Params   |    Type    | Description                                                                                                                                                      |
| :---------- | :------------------------- | :--------: | :--------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| setApiKey   | `api_key`                  |     -      | `function` | set [Google Maps Geocoding API](https://developers.google.com/maps/documentation/geocoding/intro) for purposes of quota management. Its optional but recommended |
| setLanguage | `language code`            |     -      | `function` | Specify language of the parsed address. [List of the available language codes](https://developers.google.com/maps/faq#languagesupport). Defaults to english      |
| enableDebug | `true` or `false`          |     -      | `function` | Enable or disable logs. Its optional.                                                                                                                            |
| fromLatLng  | `latitude` and `longitude` | `response` | `function` | Get address from latidude & longitude.                                                                                                                           |
| fromAddress | `address`                  | `response` | `function` | Get latidude & longitude from address.                                                                                                                           |

### Follow me on Twitter: [@shukerullah](https://twitter.com/shukerullah)

<a href="https://www.buymeacoffee.com/shukerullah" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
