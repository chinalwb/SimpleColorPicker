# SimpleColorPicker
A simple color picker on Android

## Screenshots:
### checkType = dot
 ![image](https://github.com/chinalwb/SimpleColorPicker/blob/master/demo/demo_dot.png?raw=true)
 
### checkType = checkMark
 ![image](https://github.com/chinalwb/SimpleColorPicker/blob/master/demo/demo_checkmark.png?raw=true)
 
## How to use?
1. Clone or download to your local (will integrate with Maven and Gradle later)
2. Add to your dependencies, modify your build.gradle, add this:
```
dependencies {
    implementation project(':colorpicker')
}
```
3. Import in your layout:
Add this `xmlns:colorPickerView="http://schemas.android.com/apk/res-auto"` to your layout xml namespace.

```
    <com.rainliu.colorpicker.ColorPickerView
        android:id="@+id/rteColorPalette"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:background="@android:color/background_light"
        android:padding="10dp"
        android:layout_centerHorizontal="true"
        android:visibility="gone"
        colorPickerView:colorViewHeight="30dp"
        colorPickerView:colorViewWidth="30dp"
        colorPickerView:colorViewMarginLeft="2dp"
        colorPickerView:colorViewMarginRight="2dp"
        colorPickerView:colorViewCheckedType="dot"
        colorPickerView:colors="@array/colorPickerColors"
        />
```
4. Customized attributes description:
-----------------
4.1  Set width & height: `colorPickerView:colorViewHeight="30dp"` and `colorPickerView:colorViewWidth="30dp"`

4.2  Set margin left & right: `colorPickerView:colorViewMarginLeft="2dp"` and `colorPickerView:colorViewMarginRight="2dp"`, this will change the space between two color blocks

4.3  Color block checked view: `colorPickerView:colorViewCheckedType="dot"`, there are two supported types now: `dot` and `checkMark`, each screenshot has been shown at top of this page. You can also call `colorPickerView.setCheckedView(view)` to set your own view for checked status

4.4  The colors to be shown for user to pick: `colorPickerView:colors="@array/colorPickerColors"`, for example in colors.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <array name="colorPickerColors">
        <item>#000000</item>
        <item>#607D8B</item>
        <item>#9E9E9E</item>
        <item>#795548</item>
        <item>#FF5722</item>
        <item>#FF9800</item>
        <item>#FFC107</item>
        <item>#FFEB3B</item>
        <item>#CDDC39</item>
        <item>#8BC34A</item>
        <item>#4CAF50</item>
        <item>#009688</item>
        <item>#00BCD4</item>
        <item>#03A9F4</item>
        <item>#2196F3</item>
        <item>#3F51B5</item>
        <item>#673AB7</item>
        <item>#9C27B0</item>
        <item>#E91E63</item>
        <item>#f44336</item>
    </array>
</resources>
```

4.5  Set color pick listener: call `colorPickerView.setColorPickerListener(colorPickerListener)`, and your callback function looks like: 
```
ColorPickerListener mColorPickerListener = new ColorPickerListener() {
		@Override
		public void onPickColor(int color) {
			// color is the one being selected
		}
	};
```

4.6  Set the color to be checked: call `colorPickerView.setColor(selectedColor)`

FYI: A sample usage in my project: [Android-Rich-text-Editor](https://github.com/chinalwb/Android-Rich-text-Editor)

Todo:
--------------
Add Gradle support

Add animation

Add more layout styles
