# weather_widget

Simple weather related widget, which can be freely combined to form a variety of weather backgrounds

chinese [中文README](https://github.com/carendule/WeatherWidget/blob/master/README_zh.md)

## Getting Started
depend

Add this to your package's pubspec.yaml file:

```dart
dependencies:
  weather_widget: ^1.0.1
```

Weatherwidget is easy to use, just add weatherwidget to start using  

```dart
WeatherWidget(
             size:Size.infinite,
             weather:'Sunny',
             sunConfig:SunConfig()
         ),   
```
This will add a sunny day using the default settings  
![sunny](https://github.com/carendule/WeatherWidget/blob/master/image/1.gif)  
or other weather type  
(Note: Raindrops and snowflakes need to specify the default number, and they will move randomly within the range)  
```dart
WeatherWidget(
             size:Size.infinite,
             weather:'Cloudy',
             cloudConfig:CloudConfig()
         ),

WeatherWidget(
             size:Size.infinite,
             weather:'Rainy',
             rainConfig:RainConfig(
              rainNum:'the num of raindrops you want' 
             )
         ),


WeatherWidget(
             size:Size.infinite,
             weather:'Snowy',
             snowConfig:SnowConfig(
              snowNum:'the num of snowflakes you want' 
             )
         ),


WeatherWidget(
             size:Size.infinite,
             weather:'Thunder',
             thunderConfig:ThunderConfig()
         ),
```
![rainy](https://github.com/carendule/WeatherWidget/blob/master/image/2.gif)
![snowy](https://github.com/carendule/WeatherWidget/blob/master/image/3.gif)
![thunder](https://github.com/carendule/WeatherWidget/blob/master/image/4.gif)  

Of course, each config contains other settings, such as the range, size, length, falling speed and color of random raindrops. You can use them to create hailstones and other weather features  
If the default weather is not enough, you can use individual widgets and stack() widget to piece together the desired weather  
Like this sunset breeze, etc  
![sunset breeze](https://github.com/carendule/WeatherWidget/blob/master/image/6.gif)
![snow with rain](https://github.com/carendule/WeatherWidget/blob/master/image/5.gif)
![thunder with rain](https://github.com/carendule/WeatherWidget/blob/master/image/7.gif)  
These are include in this widget  
background
```dart
    BackgroundWidget（List<Color>,size）
```  
cloud  
```dart
    CloudWidget (Color)
```
A single random raindrop 
```dart
RainWidget (
                         @required rainRangeXStart, #X-axis starting point of raindrop random occurrence
                         @required rainRangeXEnd,  
                         @required rainRangeYStart,
                         @required rainRangeYEnd,
                         @required durationRangeStartMill,  #Minimum time to fall
                         @required durationRangeEndMill,    
                         rainLength,
                         rainWidth,
                         rainColor,
                         rainCurve  #Curve of falling animation
                         )
```
A single random snowflake
```dart
SnowWidget (
                         this.snowAreaXStart,  #X-axis starting point of snowflake random occurrence
                         this.snowAreaXEnd,    
                         this.snowWaveRangeMin,    #The minimum floating distance of snowflakes
                         this.snowWaveRangeMax,    
                         this.snowFallSecMin,  #Minimum time of snowflake falling
                         this.snowFallSecMax,  
                         this.snowWaveSecMin,  #Minimum time for snowflake to float
                         this.snowWaveSecMax,
                         this.snowSize,
                         this.snowColor,
                         this.snowAreaYStart,   #Y-axis point of snowflake occurrence
                         this.snowAreaYEnd,    
                         this.waveCurve,        #Floating animation curve
                         this.fadeCurve         #Vanish animation curve
)
```
A single flash 
```dart
ThunderWidget (
                         this.flashMillStart,   #Minimum flashing time
                         this.flashMillEnd,     
                         this.pauseMillStart,   #Minimum interval time
                         this.pauseMillEnd,     
                         this.blurStyle,        #blur model
                         this.blurSigma,        
                         this.points,
                         this.color,
                         this.width
)
```
a single wind
```dart
WindWidget (
                        this.pauseMillStart,    #Minimum interval time
                        this.pauseMillEnd,     
                        this.windPositionY,     #Y-axis point of wind occurrence
                        this.windSlideMill,     #Passing time
                        this.windColor,
                        this.windWidth,
                        this.windSlideXEnd,     
                        this.windSlideXStart,   
                        this.windGap,           #line spacing in a wind
                        this.blurStyle,
                        this.blurSigma
)
```

Using sunny weather by set the WeatherWidget background config in a sunConfig()