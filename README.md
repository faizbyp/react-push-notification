
[![npm version](https://badgen.net/npm/v/react-push-notification)](https://www.npmjs.com/package/react-push-notification)

# Also checkout: React Chat Window + Free Dashboard 🚀

**Just released my new product! A react Chat window with a free to use tier dashboard. Check it out at [https://speak-base.com](https://speak-base.com) or at NPM [@speakbase/react-chat-window](https://www.npmjs.com/package/@speakbase/react-chat-window)**

  - React
  - Chat window
  - Free dashboard
  - No-code customization

### Chat window
[<img width="1000" alt="Speak Base" src="https://user-images.githubusercontent.com/36661261/233860682-c0cb6dd0-86ea-4c60-a5df-b8158938c545.png">](https://speak-base.com)
### Free dashboard
[<img width="1000" alt="Screenshot 2023-04-18 at 18 31 59" src="https://user-images.githubusercontent.com/36661261/233898459-84d589b7-b08f-4ddc-9600-3da9f8fb3f23.png">](https://speak-base.com)

**Thank you! ❤️**

--- 

# react-push-notification

Easy, type-safe, & lightweight push notification library for React.js.
Written in TypeScript & compiled to JavaScript for robust code.

In-app notification system, as well as web native Notification support.

![](https://i.imgur.com/SorfHNa.gif)
![](https://i.imgur.com/IKppymi.gif)


### Install

```bash
yarn add react-push-notification
```
or 
```bash
npm i react-push-notification
```

### Sneakpeak

In-app notification example. Regular React components.

![](https://i.imgur.com/SorfHNa.gif)

Web native notification example. Web native components. Send push notifications outside of the browser while the browser is running in the background or just idle. 

Mac OSX example:

![](https://i.imgur.com/IKppymi.gif)
![](https://imgur.com/HwA1Bf5.png)



### Set-up

Add the notifications component to the top of your React.js project. 
This is probably `index.js` or `app.js`. When using `native: true`, this step is not required.


```jsx
import { Notifications } from 'react-push-notification';

const App = () => {
    return (
      <div className="app">
        // Top of DOM tree
        <Notifications />
        <div className="row">
          <div className="content">
           Hello world.
          </div>
        </div>
      </div>
    );
  }
};

export default App;
```

### Usage

import the `addNotification` function and call it.

```jsx
import addNotification from 'react-push-notification';

const Page = () => {

    const buttonClick = () => {
        addNotification({
            title: 'Warning',
            subtitle: 'This is a subtitle',
            message: 'This is a very long message',
            theme: 'darkblue',
            native: true // when using native, your OS will handle theming.
        });
    };

    return (
      <div className="page">
          <button onClick={buttonClick} className="button">
           Hello world.
          </button>
      </div>
    );
  }
};

export default Page;
```

## <Notifications /> Props


| Property                               | Description                                   |
| ---------------------------------- | ------------------------------------------------------------------ |
| position `string`            | One of `top-left`, `top-middle`, `top-right`, `bottom-left`, `bottom-middle`, `bottom-right`.<br/>Default: `top-left`    |



## `addNotification({Options})` argument properties

The `addNotification()` function has the following function type:

```tsx

const options = {
    title: 'title',
    subtitle: 'subtitle', //optional
    message: 'message', //optional
    onClick: (e: Event | Notification) => void, //optional, onClick callback.
    theme: 'red', //optional, default: undefined
    duration: 3000, //optional, default: 5000,
    backgroundTop: 'green', //optional, background color of top container.
    backgroundBottom: 'darkgreen', //optional, background color of bottom container.
    colorTop: 'green', //optional, font color of top container.
    colorBottom: 'darkgreen', //optional, font color of bottom container.
    closeButton: 'Go away', //optional, text or html/jsx element for close text. Default: Close,
    native?: boolean, //optional, makes the push notification a native OS notification
    icon?: string, // optional, Native only. Sets an icon for the notification.
    vibrate?: number | number[], // optional, Native only. Sets a vibration for the notification.
    silent?: boolean // optional, Native only. Makes the notification silent.

};

const addNotification: (options: Options) => void;

```

<img align="right" src="https://imgur.com/YpzhAzC.png" alt="react-push-notification" />


The `addNotification()` function takes an object as argument with the follow properties:


| Property                           | Description                                                        |
| ---------------------------------- | ------------------------------------------------------------------ |
| title `string`                     | Required. Title of the push notification                           |
| subtitle `string`                  | Optional. Subtitle of the push notification                        |
| message `string`                   | Optional. Message of the push notification                         |
| onClick `(e: Event OR Notification) => void`    | Optional. onClick callback of push notification.<br/>When `native: true` `e` will be of type `Notification`.<br/>Else `e` will be of type `Event`.           |
| theme `string`                     | Optional. One of `darkblue`, `red`, `light`, `undefined`.<br/>Default: `undefined`   |
| duration `number`                  | Optional. Duration of the push notification in ms.<br/>Default: 3000   |
| backgroundTop `string`             | Optional. background color of top container.                       |
| backgroundBottom `string`          | Optional. background color of bottom container.                    |
| colorTop `string`                  | Optional. font color of top container.                             |
| colorBottom `string`               | Optional. font color of bottom container.                          |
| closeButton `string`               | Optional. text or html/jsx element for close text.<br/>Default: `Close`                         |
| native `boolean`                   | Optional. Turns the notification into a native web notification. <br/>Default: `false`  |
| icon `string`                      | Optional. Native only. Shows an icon in the notification.          |
| vibrate `number` | `number[]`      | Optional. Native only. Makes the notification vibrate.          |
| silent `boolean`      | Optional. Native only. Makes the notification silent.          |



The custom background or font colors will always override a chosen theme.

### Changelog

v1.3.0

Added native OS push notification support, as well as an `onClick` callback function.
