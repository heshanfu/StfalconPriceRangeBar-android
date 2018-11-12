# Stfalcon-PriceRangeBar
<img src="images/swipe_new.gif" width="240" height="420" />
## Who we are
Need iOS and Android apps, MVP development or prototyping? Contact us via info@stfalcon.com. We develop software since 2009, and we're known experts in this field. Check out our portfolio and see more libraries from stfalcon-studio.
## Download
Download via Gradle: 
```compile 'com.github.stfalcon:pricerangebar:0.1.0'```
## Usage
For adding default seekbar with chart just put this code into your layout:
```
<com.stfalcon.pricerangebar.SeekBarWithChart
   android:layout_width="match_parent"
   android:layout_height="wrap_content"/>
```
Or you can use default rangebar with chart just put this code into your layout:
```
<com.stfalcon.pricerangebar.RangeBarWithChart
   android:layout_width="match_parent"
   android:layout_height="wrap_content"/>
```
After that you should to add list entries with data to displaying

```
val seekBarEntries = ArrayList<SeekBarEntry>()

seekBarEntries.add(SeekBarEntry(30.0f, 5.0f))
seekBarEntries.add(SeekBarEntry(32.0f, 7.0f))
seekBarEntries.add(SeekBarEntry(34.0f, 10.0f))
seekBarEntries.add(SeekBarEntry(36.0f, 11.0f))
seekBarEntries.add(SeekBarEntry(38.0f, 14.0f))
seekBarEntries.add(SeekBarEntry(40.0f, 15.0f))

seekBar.setEntries(seekBarEntries)
```
You can use many attributes for more flexibility and convenience of use. Here's the full list:
- seekActiveLineColor 
- seekActiveThumbColor
- seekActiveTickRadius
- seekChartSelectedBackgroundColor
- seekChartSelectedLineColor
- seekChartUnSelectedLineColor
- seekChartUnselectedBackgroundColor
- seekLineColor

For example:
```
<com.stfalcon.pricerangebar.SeekBarWithChart
    android:id="@+id/seekBar"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:seekActiveLineColor="@android:color/holo_orange_dark"
    app:seekActiveThumbColor="@android:color/holo_blue_light"
    app:seekActiveTickRadius="@dimen/custom_active_tick_radius"
    app:seekChartSelectedBackgroundColor="@android:color/holo_red_dark"
    app:seekChartSelectedLineColor="@android:color/holo_green_dark"
    app:seekChartUnSelectedLineColor="@android:color/holo_green_light"
    app:seekChartUnselectedBackgroundColor="@android:color/holo_red_light"
    app:seekLineColor="@android:color/holo_blue_light"/>
```
If you want to observe any changes you should to add callbacks like:
- ```onPinPositionChanged```
- ```onSelectedEntriesSizeChanged```
- ```onSelectedItemsSizeChanged```
Let's take look a small sample:
```
seekBar.onPinPositionChanged = { index, pinValue ->
    println("$pinValue $index")
}
seekBar.onSelectedEntriesSizeChanged = { selectedEntriesSize ->
    println("$selectedEntriesSize")
}
seekBar.onSelectedItemsSizeChanged = { selectedItemsSize ->
    println("$selectedEntriesSize elements was selected")
}
```
## License
```
Copyright 2018 stfalcon.com

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
