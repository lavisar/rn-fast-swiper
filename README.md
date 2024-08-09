# React Native Flat Swiper

<!-- ![Libraries.io dependency status for latest release](https://img.shields.io/librariesio/release/npm/react-native-flat-swiper)
[![Build Size](https://img.shields.io/bundlejs/size/react-native-flat-swiper)](https://pkg-size.dev/react-native-flat-swiper) -->

[![Downloads](https://img.shields.io/npm/dt/react-native-flat-swiper.svg?style=flat&color=success)](https://www.npmjs.com/package/react-native-flat-swiper)
[![Version](https://img.shields.io/npm/v/react-native-flat-swiper?style=flat&color=success)](https://www.npmjs.com/package/react-native-flat-swiper)
<a href="https://pkg-size.dev/react-native-flat-swiper"><img src="https://pkg-size.dev/badge/install/103906" title="Install size for react-native-flat-swiper"></a>
<a href="https://pkg-size.dev/react-native-flat-swiper"><img src="https://pkg-size.dev/badge/bundle/24854" title="Bundle size for react-native-flat-swiper"></a>

<br/>

# Preview

![Screen-Recording-2024-08-08-at-17 42 28](https://github.com/user-attachments/assets/308caee8-757e-4161-8072-420ba0cb96b9) ![Screen-Recording-2024-08-08-at-17 39 51](https://github.com/user-attachments/assets/e08a7199-893a-48b0-a577-1a79cf67e7b4)


# Installation

Type in the following to the command line to install the module.

<br/>

```bash
$ npm install --save react-native-flat-swiper
```

or

```bash
$ yarn add react-native-flat-swiper
```

<br/>

---

<br/>

## Usage

Add an `import` to the top of the file. At minimal, place `array` data into the `data` prop and render the pages using the `renderItem` prop.

```javascript
import FlatSwiper from 'react-native-flat-swiper';
import { View, Image, StyleSheet } from 'react-native';
import React, { useRef } from 'react';

const SomeComponent = () => {
	const flatSwiperRef = useRef(null);

  const onSwipeIndexChange = (index: number) => {
    // get the index of the card when on swiping
  };

  //Trigger to next card by ref:
  flatSwiperRef?.current?.scrollBy(1, false);  //scrollBy(cardIndex: number, animation: boolean)

  //Trigger to any card by ref with index:
  flatSwiperRef?.current?.scrollTo(yourCardIndex, false); //scrollTo(cardIndex: number, animation: boolean)

return (
   <FlatSwiper
	index={0}
	loop={false}
	ref={flatSwiperRef}
	horizontal={false}
	loadMinimal={true}
	data={yourData[] || []}
	enableAndroidViewPager={false}
	onIndexChangeReached={(index) => onSwipeIndexChange(index)}
	renderItem={({ item, index }) => {
	   //IMPORTANT: props name "item" is required
	   return (
		<View key={index} style={styles.item}>
			<Text>View {index}</Text>
		</View>
	   );
	}}
   />
);
};

const styles = StyleSheet.create({
  item: { flex: 1}  // to display 1 item per time
})
```