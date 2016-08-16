##MJRefresh使用笔记

### 1.支持哪种类型的controls刷新
	* UIScrollView
	* UITableView
	* UICollectionView
	* UIWebView
	
	
### 2.如何使用
* 拖入``` MJRefresh```文件夹到工程中
* 引入主头文件 ``` #import "MJRefresh.h"```

###MJRefreshComponent:刷新控件的基类
#### 1.MJRefreshHeader:基础的下拉刷新控件
* MJRefreshStateHeader带有状态文字的下拉刷新控件
	* MJRefreshNormalHeader默认的下拉刷新控件
	* MJRefreshGifHeader带动图的下拉刷新控件



#### 2.MJRefreshFooter:基础的上拉刷新控件
* MJRefreshBackFooter 会回弹到底部的上拉刷新控件
	* MJRefreshBackStateFooter 带有状态文字的上拉刷新控件
		* MJRefreshBackNormalFooter默认的上拉刷新控件
		* MJRefreshBackGifFooter带有动图的上拉刷新控件
* MJRefreshAutoFooter 会自动刷新的上拉刷新的控件
	* MJRefreshAutoStateFooter 带有状态文字的上拉刷新控件
		* MJRefreshAutoNormalFooter默认是的上拉刷新控件
		* MJRefreshAutoGifFooter带有动图的上拉书刷新控件
		
 