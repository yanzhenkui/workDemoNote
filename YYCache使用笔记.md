##YYCache使用笔记

### 1.缓存思路

* 没有用YYcache
	
	* 1.先请求，请求到show并且存一份到Sqlite

	* 2.下次请求前判断网络

	* 3.有网 --》继续1

	* 4.没有网络 -》加载缓存
	
* 使用YYcache
	* 1.先加载缓存

	* 2.判断有没有网络

	* 3.如果没有网络则return

	* 4.有网，则继续请求，然后刷新内容，刷新缓存
	


### 2.具体Demo参考
https://github.com/321zhangyang/SPHttpWithYYCache


	

