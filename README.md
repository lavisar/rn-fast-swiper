# RN Fast Swiper

[![Downloads](https://img.shields.io/npm/dt/rn-fast-swiper.svg?style=flat&color=success)](https://www.npmjs.com/package/rn-fast-swiper)
[![Version](https://img.shields.io/npm/v/rn-fast-swiper?style=flat&color=success)](https://www.npmjs.com/package/rn-fast-swiper)
<a href="https://pkg-size.dev/rn-fast-swiper"><img src="https://pkg-size.dev/badge/install/103906" title="Install size for rn-fast-swiper"></a>
<a href="https://pkg-size.dev/rn-fast-swiper"><img src="https://pkg-size.dev/badge/bundle/24854" title="Bundle size for rn-fast-swiper"></a>

<br/>

# Preview
![Screen-Recording-2024-08-09-at-16 24 52](https://github.com/user-attachments/assets/5b23819f-94d3-4c13-b365-869d5f30f8f1)

![Screen-Recording-2024-08-09-at-16 26 00](https://github.com/user-attachments/assets/64c0c8e1-62eb-41b5-97e3-db16fd49e04e)


# Installation

Type in the following to the command line to install the module.

<br/>

```bash
$ npm install --save rn-fast-swiper
```

or

```bash
$ yarn add rn-fast-swiper
```

<br/>

---

<br/>

## Usage

```javascript
import RNFastSwiper from 'react-native-flat-swiper';
import { View, Image, StyleSheet } from 'react-native';
import React, { useRef } from 'react';

const SomeComponent = () => {

  const rnFastSwiperRef = useRef(null);

  const onSwipeIndexChange = (index: number) => {
    // get the index of the card when on swiping
  };

  //Trigger to next card by ref:
  rnFastSwiperRef?.current?.scrollBy(1, false);  //scrollBy(cardIndex: number, animation: boolean)

  //Trigger to any card by ref with index:
  rnFastSwiperRef?.current?.scrollTo(yourCardIndex, false); //scrollTo(cardIndex: number, animation: boolean)

return (
   <RNFastSwiper
	index={0}
	loop={false}
	ref={rnFastSwiperRef}
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
