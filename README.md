# ExpandableCardView

[![](https://jitpack.io/v/tahaak67/ExpandableCardView.svg)](https://jitpack.io/#tahaak67/ExpandableCardView)



![Example Gif](demo.gif)

This is a more coustomizable version of [AleSpero/ExpandableCardView](https://github.com/AleSpero/ExpandableCardView)

An Android library that lets you create in a simple, fast and hassle-free way a CardView in which you can insert your custom layout and just expand and collapse without even writing a single Java/Kotlin line of code.

This component follows the [Material Design Guidelines](https://material.io/guidelines/).

## Demo

Get it on the [Google Play Store](https://play.google.com/store/apps/details?id=com.alessandrosperotti.expandablecardviewexample).

# Setup

First of all, add jitpack maven to your root build.gradle file
```
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
Then include the dependency in your app build.gradle:

```
dependencies {
	        implementation 'com.github.tahaak67:ExpandableCardView:0.6.5-beta4'
	}
```

## Declaring the view

After you have the Library correctly setup, just declare the ExpandableCardView in your xml:

```xml
   <com.tahaak67.expandablecardview.ExpandableCardView
      android:id="@+id/myCardView"
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      app:arrow="@drawable/collapsed_arrow"
      app:arrowAnimated="true"
      app:cardBackgroundColor="@color/colorSecondary"
      app:expandedArrow="@drawable/expanded_arrow"
      app:inner_view="@layout/my_inner_view"
      app:startExpanded="true"
      app:titleTextAppearance="@style/cardTitleStyle"
      app:titleTextColor="@color/mainTextColor" />
```
The only required attributes are `inner_view` and `title`. The other attributes are optional.

You can specify a custom title and icon on the header on the card by setting the attribute ```app:title``` and  ```app:icon``` respectively.

After you created the base xml, just create your custom layout and place it inside your ```layout``` folder.

Additional attributes:

-```app::arrow``` change the arrow to an image or your choice

-```app::arrowAnimated``` enable or disable the animation of the arrow when expanding/collapsing

-```app::cardBackgroundColor``` change the background color of the card

-```app::expandedArrow``` change the arrow image when the card is expanded

-```app::titleTextAppearance``` change the style of the title text (Requires API 23/aka Marshmellow or newer)

-```app::titleTextColor``` change the title text color



Now just pass your newly created layout resource to the ```app:inner_view``` attribute. By setting the attribute ```app:expandOnClick="true"``` the card will have a default behaviour (expand/collapse on click); By setting the `animationDuration` attribute you can set a custom animation time, and by setting the `startExpanded` attribute the card will be automatically expanded when inflated.

Done! Now your ExpandableCardView is ready to roll.

## Usage

If you want some basic Expandable Card without any custom behaviour, setting the view in the XML is enough. Otherwise just declare your ExpandableCardView in your Activity/Fragment and you're ready to use its methods.

### Java
```java
ExpandableCardView card = findViewById(R.id.profile);

 //Do stuff here
```
### Kotlin

```kotlin
val card : ExpandableCardView = findViewById(R.id.profile)

 //Do stuff here
```

You can use ```expand()``` and ```collapse()``` to respectively expand and collapse the card, and use ```isExpanded()``` to check if the card is expanded or not.
You can change the title and icon of the card dynamically by using ```setTitle()``` and ```setIcon()``` methods.

You can also set an OnExpandedListener to the card:

### Java
```java
card.setOnExpandedListener(new OnExpandedListener() {
    @Override
    public void onExpandChanged(View v, boolean isExpanded) {
        Toast.makeText(applicationContext, isExpanded ? "Expanded!" : "Collapsed!", Toast.LENGTH_SHORT).show();
    }
});
```
### Kotlin

```kotlin
card.setOnExpandedListener { view, isExpanded ->
    Toast.makeText(applicationContext, if(isExpanded) "Expanded!" else "Collapsed!", Toast.LENGTH_SHORT).show()
 }
```
## Contribute

This library is still in its early stages, so feel free to contribute. I will review any Pull Request in 24-48 hours.

## License

```
  Copyright (c) 2018 Alessandro Sperotti
 
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at
 
  http://www.apache.org/licenses/LICENSE-2.0
 
  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
 
```

## Author
Made By [Alessandro Sperotti](www.alessandrosperotti.com). 

alessandrosperotti at gmail dot com

Costumized version made by me :) [Taha Ben Ashur](https://699taha.blogspot.com/)



If you liked this library, why don't you offer Alessandro a coffee ? :D

ETH: 0x70b6b9eaCDf6f76ECb92bE3fb81d72B3971BA1Bc
