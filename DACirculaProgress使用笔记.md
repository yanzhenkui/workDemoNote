## DACirculaProgress使用笔记

###1.使用步骤
####方式一


	1.将DACircularProgress文件夹拷贝到你自己的工程文件夹下
	2.确保你的工程包含 <QuartzCore.framework>框架
	3.引入头文件 #import "DACircularProgressView.h"


####方式二
```
	还可以使用XIB,添加一个UIView,并设置这个View的类型为DACircularProgress
```

###2.DACircularProgressView(不带中间文字)

* 示例

```
	// 创建 
	self.progressView = [[DACircularProgressView alloc]initWithFrame:CGRectMake(140.0f, 50.0f, 40.0f, 40.0f)];
    
    // 设置进度轨迹是否为圆角(也可以填NSInteger类型的数据)
    self.progressView.roundedCorners = YES;
    // 设置进度圆形轨迹的填充颜色(整个圆形)
    self.progressView.trackTintColor = [UIColor redColor];

```

* 所有属性

```
// 设置进度圆形轨迹的填充颜色(整个圆形)
@property(nonatomic, strong) UIColor *trackTintColor UI_APPEARANCE_SELECTOR;

// 设置进度的填充颜色
@property(nonatomic, strong) UIColor *progressTintColor UI_APPEARANCE_SELECTOR;

// 空心圆环内部的填充颜色
@property(nonatomic, strong) UIColor *innerTintColor UI_APPEARANCE_SELECTOR;

// 设置进度轨迹是否为圆角(也可以填NSInteger类型的数据,YES表示默认)
@property(nonatomic) NSInteger roundedCorners UI_APPEARANCE_SELECTOR; // Can not use BOOL with UI_APPEARANCE_SELECTOR :-(

// (厚度比)表示进度圆环的厚度与整个圆半径的比例(当为1.0时,正好是飞盘样式)
@property(nonatomic) CGFloat thicknessRatio UI_APPEARANCE_SELECTOR;

// 是否为顺时针转动
@property(nonatomic) NSInteger clockwiseProgress UI_APPEARANCE_SELECTOR; // Can not use BOOL with UI_APPEARANCE_SELECTOR :-(

// 转动进度
@property(nonatomic) CGFloat progress;

// 无限转动一圈持续时常,一般是在初始化时设置才有效
@property(nonatomic) CGFloat indeterminateDuration UI_APPEARANCE_SELECTOR;

// 是否为无线转动
@property(nonatomic) NSInteger indeterminate UI_APPEARANCE_SELECTOR; // Can not use BOOL with UI_APPEARANCE_SELECTOR :-(

- (void)setProgress:(CGFloat)progress animated:(BOOL)animated;
- (void)setProgress:(CGFloat)progress animated:(BOOL)animated initialDelay:(CFTimeInterval)initialDelay;

// 初始延迟initialDelay时间后,动画设置进度用duration时间
- (void)setProgress:(CGFloat)progress animated:(BOOL)animated initialDelay:(CFTimeInterval)initialDelay withDuration:(CFTimeInterval)duration;
```

###2.DALabeledCircularProgressView(带中间label文字)
* 继承自DACircularProgressView
* 仅仅多了一个label控件显示进度数值
		
		@interface DALabeledCircularProgressView : DACircularProgressView
		
		// UILabel placed right on the DACircularProgressView.
	 	@property (strong, nonatomic) UILabel *progressLabel;
	 	
	 	
###注意:
* 设置微信图片加载等待图标无限滚动时,不能在创建控件同时设置indeterminate属性,最好是在一个事件中(例如点击事件)设置
  