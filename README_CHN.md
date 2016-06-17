## PullLaunchRocket

[![Twitter](https://img.shields.io/badge/Twitter-@LuMengHZ-blue.svg?style=flat-square)](https://twitter.com/LuMengHZ)
[![License](https://img.shields.io/github/license/lubeast/PullLaunchRocket.svg?style=flat-square)](https://github.com/lubeast/PullLaunchRocket/blob/master/LICENSE)

感谢[Yalantis](https://github.com/Yalantis)为下拉刷新创建了一个炒鸡棒的逻辑案例, 也是`PullLaunchRocket`的基础.

欢迎各位点个`Star`给我.

![sample](https://raw.github.com/lubeast/PullLaunchRocket/master/screenshots/sample.gif)

### 使用
*为了更好使用也可参照示例工程`sample`*

1.在module层级`build.gradle`中加入
`compile 'com.lumenghz.'pullrefresh`
2.在布局文件中使用`PullToRefreshView`
```xml
<lumenghz.com.pullrefresh.PullToRefreshView
        android:id="@+id/pull_to_refresh"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:lrefresh="rocket"
        >

        <ListView
            android:id="@+id/list_view"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:divider="@null"
            android:dividerHeight="0dp"
            android:fadingEdge="none"
            />

</lumenghz.com.pullrefresh.PullToRefreshView>
```
3.在`onCreate`方法中初始化此View并添加刷新监听
```java
mPullToRefreshView.setOnRefreshListener(new PullToRefreshView.OnRefreshListener() {
    @Override
    public void onRefresh() {
        mPullToRefreshView.postDelayed(new Runnable() {
            @Override
            public void run() {
                mPullToRefreshView.setRefreshing(false);
            }
        }, REFRESH_DELAY);
    }
 });
```
4.你可以调用`mPullToRefreshView.setRefreshing(boolean isRefreshing);`修改刷新状态.