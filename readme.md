## Show Cases

> Swiper image

![1.gif](https://cloud.githubusercontent.com/assets/7970947/21086300/388dedfc-c056-11e6-955e-0a2a0b541f7f.gif)

> Zoom while sliding

![2.gif](https://cloud.githubusercontent.com/assets/7970947/21086323/7355face-c056-11e6-8d68-384000d41d47.gif)

## Getting Started

### Installation

```bash
npm i react-native-image-zoom-viewer --save
```

### Basic Usage

* Install create-react-native-app first

```bash
$ npm install -g create-react-native-app
```

* Initialization of a react-native project

```bash
$ create-react-native-app AwesomeProject
```

* Then, edit `AwesomeProject/App.js`, like this:

```typescript
import { Modal } from 'react-native';
import ImageViewer from 'react-native-image-zoom-viewer';

const images = [{
    url: 'https://avatars2.githubusercontent.com/u/7970947?v=3&s=460'
}, {
    url: 'https://avatars2.githubusercontent.com/u/7970947?v=3&s=460'
}, {
    url: 'https://avatars2.githubusercontent.com/u/7970947?v=3&s=460'
}]

export default class App extends React.Component {
    render: function() {
        return (
            <Modal visible={true} transparent={true}>
                <ImageViewer imageUrls={images}/>
            </Modal>
        )
    }
}
```

### Props
|parameter|type|required|description|default|
|:---|:---|:---|:---|:---|
|imageUrls|array|yes|Image Source||
|enableImageZoom|boolean|no|Enable image zoom|`true`|
|onShowModal|function<br><br>`(content?: JSX.Element) => void`|no|The callback for show modal|`() => {}`|
|onCancel|funcion<br><br>`() => void`|no|The callback for cancel modal|`() => {}`|
|flipThreshold|number|no|Swipe threshold of the next page|`80`|
|maxOverflow|number|no|The X position maximum, that current page can slide to the next page|`300`|
|index|number|no|Init index of images|`0`|
|failImageSource|string, object<br><br>`{uri: string}`|no|placeholder for fail|`''`|
|loadingRender|function<br><br>`() => React.ReactElement<any>`|no|placeholder for loading|`() => null`|
|onSaveToCamera|function<br><br>`(index?: number => void`|no|The callback for save to camera|`() => {}`|
|onChange|function<br><br>`(index?: number => void`|no|When the image changed|`() => {}`|
|saveToLocalByLongPress|boolean|no|Enable save to camera when long press|`true`|
|onClick|function<br><br>`(onCancel?: function) => void`|no|Onclick|`(onCancel) => {onCancel()}`|
|onDoubleClick|function<br><br>`(onCancel?: function) => void`|no|OnDoubleClick|`(onCancel) => {onCancel()}`|
|onSave|function<br><br>`(url: string) => void`|no|The picture is saved to the local method, if you write this method will not call the system default method for Android does not support saveToCameraRoll remote picture, you can call this callback in Android call native interface||
|renderHeader|function<br><br>`() => React.ReactElement<any>`|no|Custom header|`() => null`|
|renderFooter|function<br><br>`() => React.ReactElement<any>`|no|Custom footer|`() => null`|
|renderIndicator|function<br><br>`(currentIndex?: number, allSize?) => React.ReactElement<any>`: number|no|Custom indicator|`(currentIndex, allSize) => currentIndex + "/" + allSize`|
|renderArrowLeft|function<br><br>`() => React.ReactElement<any>`|no|Custom left arrow|`() => null`|
|renderArrowRight|function<br><br>`() => React.ReactElement<any>`|no|Cutsom right arrow|`() => null`|

## Development pattern

### Step 1, run TS listener

After clone this repo, then:

```bash
npm install
npm start
```

### Step 2, run demo

```bash
cd demo
npm install
npm start
```

Then, scan the QR, use your [expo app](https://expo.io./).

### Dependence

Depend on `react-native-image-pan-zoom`: https://github.com/ascoders/react-native-image-zoom
