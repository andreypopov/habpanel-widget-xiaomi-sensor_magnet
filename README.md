# Habpanel / Xiaomi Door Window sensor 
Widget designed for 1x1 habpanel dashboard grid <br>
<b>Note:</b> Use 100% of browser zoom
<hr>
<img src="https://github.com/andreypopov/habpanel-widget-xiaomi-sensor_magnet/blob/master/readme/widget_view1.png?raw=true" height="200">
<img src="https://github.com/andreypopov/habpanel-widget-xiaomi-sensor_magnet/blob/master/readme/widget_view2.png?raw=true" height="200">
<br>
<br>
<b>things/*.things</b> file:<br>
<pre>
Thing mihome:sensor_magnet:YOUR ID "Xiaomi Door Sensor" [itemId="YOUR ID"]
</pre>
<br>
<b>items/*.items</b> file:<br>
<pre>// Xiaomi Window Switch
Contact WindowSwitch_Status "Window State" <window>  { channel="mihome:sensor_magnet:YOUR ID:isOpen" }
Number WindowSwitch_AlarmTimer "Window Alarm Timer" <clock> { channel="mihome:sensor_magnet:YOUR ID:isOpenAlarmTimer" }
DateTime WindowSwitch_LastOpened "Window Last Opened [%1$tY-%1$tm-%1$td  %1$tH:%1$tM]" <clock-on> { channel="mihome:sensor_magnet:YOUR ID:lastOpened" }
Number WindowSwitch_Battery "Window Battery" <battery> { channel="mihome:sensor_magnet:YOUR ID:batteryLevel" }
Switch WindowSwitch_BatteryLow "Window Battery Low" <energy> { channel="mihome:sensor_magnet:YOUR ID:lowBattery" }
</pre>
<br>
<b>sitemaps/*.sitemap</b> file:<br>
<pre>Switch item=WindowSwitch_Status label="Window status" mappings=[OPEN="Opened"] visibility=[WindowSwitch_Status==OPEN]
Switch item=WindowSwitch_Status label="Window status" mappings=[CLOSED="Closed"] visibility=[WindowSwitch_Status==CLOSED]
Text item=WindowSwitch_LastOpened label="Opened timed" visibility=[WindowSwitch_Status==OPEN]
Text item=WindowSwitch_LastOpened label="Closed time" visibility=[WindowSwitch_Status==CLOSED]</pre>
<br>
<b>persistence/mysql.persist</b> file:<br>
<pre>WindowSwitch_Status : strategy = everyChange, everyDay, restoreOnStartup
WindowSwitch_Battery : strategy = everyChange, everyDay, restoreOnStartup</pre>



<span style="float:left;">
<img src="https://github.com/andreypopov/habpanel-widget-xiaomi-sensor_magnet/blob/master/readme/widget_settings1.png?raw=true" height="400">
</span>
<span style="float:left;">
<img src="https://github.com/andreypopov/habpanel-widget-xiaomi-sensor_magnet/blob/master/readme/device.jpg?raw=true" height="400">
</span>

<hr>

Feel free to donate for new devices and some beer<br>

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=VQCYQ3WC7F75N)


