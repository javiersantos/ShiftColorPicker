<h1 align="center">ShiftColorPicker</h1>
<h4 align="center">Android Library</h4>

<p align="center">
  <a target="_blank" href="https://android-arsenal.com/api?level=9"><img src="https://img.shields.io/badge/API-9%2B-orange.svg"></a>
</p>

<p align="center">ShiftColorPicker is simple vertical and horizontal color picker. This library is a fork from the original <a href="https://github.com/DASAR/ShiftColorPicker">ShiftColorPicker library</a> by DASAR and includes a method to retrieve the selected position (like a RatingBar).
</p>

![ShiftColorPicker Library](/screenshot.png?raw=true)

##How to include

Add the repository to your project **build.gradle**:
```Javascript
repositories {
    maven {
        url "https://jitpack.io"
    }
}
```

And add the library to your module **build.gradle**:
```Javascript
dependencies {
    compile 'com.github.javiersantos:ShiftColorPicker:0.6'
}
```

##Usage

Add view to your activity's layout and specify orientation:
```xml
   <uz.shift.colorpicker.LineColorPicker
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:id="@+id/picker"
        android:layout_width="match_parent"
        android:layout_height="60dp"
        app:orientation="horizontal"/>
```

Optionally you can set colors directly in layout file:
```xml
        app:colors="@array/sample_colors"
        app:selectedColorIndex="3"
```

Setup view
```java
colorPicker = (LineColorPicker) findViewById(R.id.picker);

// set color palette
colorPicker.setColors(new int[] {Color.RED,Color.GREEN,Color.BLUE,Color.YELLOW});

// set selected color [optional]
colorPicker.setSelectedColor(Color.RED);

// set on change listener
colorPicker.setOnColorChangedListener(new OnColorChangedListener() {
			@Override
			public void onColorChanged(int c) {
				Log.d(TAG, "Selected color " + Integer.toHexString(c));
			}
		});

// get selected color
int color = colorPicker.getColor();

// get current selected position
int selectedPosition = colorPicker.getSelectedPosition();
```

###[Releases page](https://github.com/javiersantos/ShiftColorPicker/releases) 
or grab latest version from repository.

##Requirements

Android 2.3 (Gingerbread) and later.

##Todo
* Expand/collapse animations
* More color pickers in different styles
* rounded corners for line picker

##License

The MIT License (MIT)

Copyright (c) 2015 Bogdasarov Bogdan
