# HJDanmaku

![](https://img.shields.io/badge/build-passing-brightgreen.svg)
![](https://img.shields.io/badge/Cocoapods-v1.1.1-blue.svg)
![](https://img.shields.io/badge/language-objc-5787e5.svg)
![](https://img.shields.io/badge/license-MIT-brightgreen.svg)  

A high performance danmaku engine for iOS. For more details please click [here](http://www.olinone.com/?p=186)

![GitHub set up-w140](http://7pum7o.com1.z0.glb.clouddn.com/HJDanmakuDemo.jpg)

## Feature

Dimension | 1.0| 2.0
--------- | ------------- | -------------
Performance | ⭐️⭐️⭐️ | ⭐️⭐️⭐️⭐️
Fluency | ⭐️⭐️⭐️ | ⭐️⭐️⭐️⭐️⭐️
Accuracy | ⭐️⭐️⭐️⭐️ | ⭐️⭐️⭐️
Concurrency | ⭐️⭐️ | ⭐️⭐️⭐️⭐️⭐️

## Installation with CocoaPods

[CocoaPods](http://cocoapods.org/) is a dependency manager for Objective-C, which automates and simplifies the process of using 3rd-party libraries in your projects. See the [Get Started](http://cocoapods.org/#get_started) section for more details.

## Podfile

```
pod 'HJDanmaku', :git => 'https://github.com/panghaijiao/HJDanmakuDemo.git'
```

## Usage

#### Live Mode

```
// init config with mode HJDanmakuModeLive
HJDanmakuConfiguration *config = [[HJDanmakuConfiguration alloc] initWithDanmakuMode:HJDanmakuModeLive];
HJDanmakuView *danmakuView = [[HJDanmakuView alloc] initWithFrame:self.view.bounds configuration:config];
```

#### Video Mode

```
// init config with mode HJDanmakuModeVideo
HJDanmakuConfiguration *config = [[HJDanmakuConfiguration alloc] initWithDanmakuMode:HJDanmakuModeVideo];
HJDanmakuView *danmakuView = [[HJDanmakuView alloc] initWithFrame:self.view.bounds configuration:config];
```


#### Send Danmaku

```
DemoDanmakuModel *danmaku = [[DemoDanmakuModel alloc] initWithType:HJDanmakuTypeLR];
danmaku.text = @"😊😊olinone.com😊😊";
[self.danmakuView sendDanmaku:danmaku forceRender:YES];
```

#### Custom style

```
// register cell class before dequeue
[self.danmakuView registerClass:[DemoDanmakuCell class] forCellReuseIdentifier:@"cell"];

// configure cell with custom style
DemoDanmakuCell *cell = [danmakuView dequeueReusableCellWithIdentifier:@"cell"];
DemoDanmakuModel *model = (DemoDanmakuModel *)danmaku;
cell.textLabel.font = model.textFont;
cell.textLabel.textColor = model.textColor;
cell.textLabel.text = model.text;
```

##  History Release

HJDanmaku 1.0 was first released in 2015, You can get it in the folder [HJDanmaku1](https://github.com/panghaijiao/HJDanmakuDemo/tree/master/HJDanmaku1). Surely, for better performance, we recommend the latest version 2.0.

## License

HJDanmakuDemo is released under the MIT license. See LICENSE for details.
Copyright (c) 2015 olinone.

