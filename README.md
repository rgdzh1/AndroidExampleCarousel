# AndroidExampleCarousel
There is a simple example of how to make a carousel effect on Android.  
It looks like this:  
![Alt text](demo1.gif?raw=true)

修改了`list_item.xml`布局
```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/root"
    android:layout_width="wrap_content"
    android:layout_height="200dp"
    android:layout_marginStart="10dp"
    android:layout_marginEnd="10dp">

    <ImageView
        android:id="@+id/listItemIcon"
        android:layout_width="18dp"
        android:layout_height="18dp"
        android:layout_gravity="center"
        android:src="@drawable/icon_background_blue"
        tools:ignore="ContentDescription" />
</FrameLayout>
```
增加了代码
```kotlin
item_list.addItemDecoration(object : ItemDecoration() {
            override fun getItemOffsets(outRect: Rect, view: View, parent: RecyclerView, state: RecyclerView.State) {
                super.getItemOffsets(outRect, view, parent, state)
                if (parent.getChildPosition(view) != (itemAdapter.itemCount - 1)) {
                    outRect.left = -40
                }
            }
        })
```
这样就能一屏幕展示多个View进行轮播,并且每个View之间还有叠加效果.