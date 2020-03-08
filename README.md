# weather_widget

天气相关的简易控件,可自由组合搭配形成各种天气背景

## Getting Started

WeatherWidget使用方法简便，只需添加WeatherWidget控件即可开始使用

```dart
WeatherWidget(
             size:Size.infinite,
             weather:'Sunny',
             sunConfig:SunConfig()
         ),   
```
这将使用默认设置添加一个晴天
![Image]https://github.com/carendule/WeatherWidget/blob/master/image/1.gif
或
注：雨滴和雪花需指定默认数量,它们将在范围内随机运动
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
              rainNum:'你希望的雨滴数量' 
             )
         ),


WeatherWidget(
             size:Size.infinite,
             weather:'Snowy',
             snowConfig:SnowConfig(
              snowNum:'你希望的雪花数量' 
             )
         ),


WeatherWidget(
             size:Size.infinite,
             weather:'Thunder',
             thunderConfig:ThunderConfig()
         ),
```
![Image]https://github.com/carendule/WeatherWidget/blob/master/image/2.gif
![Image]https://github.com/carendule/WeatherWidget/blob/master/image/3.gif
![Image]https://github.com/carendule/WeatherWidget/blob/master/image/4.gif

当然每个Config包含其他设置,如随机雨点的出现范围，大小，长度，下落速度和颜色等，你可以使用他们创造冰雹等其他特征天气
如果默认天气不足，你可以使用各个单独的widget结合Stack()来拼凑希望的天气
如日落的微风等
![Image]https://github.com/carendule/WeatherWidget/blob/master/image/6.gif
![Image]https://github.com/carendule/WeatherWidget/blob/master/image/5.gif
![Image]https://github.com/carendule/WeatherWidget/blob/master/image/7.gif
包括
背景
```dart
    BackgroundWidget（List<Color>,size）
```  
云朵  
```dart
    CloudWidget (Color)
```
单独一个随机雨滴 
```dart
RainWidget (
                         @required rainRangeXStart, #雨滴随机出现的X轴起点
                         @required rainRangeXEnd,   #雨滴随机出现的X轴终点
                         @required rainRangeYStart,
                         @required rainRangeYEnd,
                         @required durationRangeStartMill,  #下落的最小时间
                         @required durationRangeEndMill,    #下落的最大时间
                         rainLength,
                         rainWidth,
                         rainColor,
                         rainCurve  #下落动画的曲线
                         )
```
单独一个随机雪花 
```dart
SnowWidget (
                         this.snowAreaXStart,  #雪花随机出现的X轴起点
                         this.snowAreaXEnd,    #雪花随机出现的X轴终点
                         this.snowWaveRangeMin,    #雪花的最小飘动距离
                         this.snowWaveRangeMax,    #雪花的最大飘动距离
                         this.snowFallSecMin,  #雪花下落最小时间
                         this.snowFallSecMax,  
                         this.snowWaveSecMin,  #雪花飘动最小时间
                         this.snowWaveSecMax,
                         this.snowSize,
                         this.snowColor,
                         this.snowAreaYStart,   #雪花出现的Y轴点
                         this.snowAreaYEnd,     #雪花消失的Y轴点
                         this.waveCurve,        #飘动动画曲线
                         this.fadeCurve         #消失动画曲线
)
```
单独一个闪电 
```dart
ThunderWidget (
                         this.flashMillStart,   #闪烁的最小时间
                         this.flashMillEnd,     #闪烁的最大时间
                         this.pauseMillStart,   #间隔的最小时间
                         this.pauseMillEnd,     #间隔的最大时间
                         this.blurStyle,        #高斯模糊模式
                         this.blurSigma,        #高斯模糊半径
                         this.points,
                         this.color,
                         this.width
)
```
单独的一个风 
```dart
WindWidget (
                        this.pauseMillStart,    #间隔最小时间
                        this.pauseMillEnd,      #间隔的最大时间
                        this.windPositionY,     #出现的Y轴位置
                        this.windSlideMill,     #飘过的时间
                        this.windColor,
                        this.windWidth,
                        this.windSlideXEnd,     #结束的X轴位置
                        this.windSlideXStart,   #开始的X轴位置
                        this.windGap,           #风的间距
                        this.blurStyle,
                        this.blurSigma
)
```

太阳在WeatherWidget sunConfig中设置背景Color
