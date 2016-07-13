# CircleTextProgressbar

严振杰的主页: http://www.yanzhenjie.com  
严振杰的博客: http://blog.csdn.net/yanzhenjie1003

----
# 效果预览
<image src="./image/demo.gif" width="350px"/>

#简介与使用
本质是一个TextView，所以TextView的基本属性它都有。

`CircleTextProgressbar`支持自动倒计时，自动减少进度，自动增加进度等。

如果需要自动走进度的话，设置完你自定义的属性后调用`start()`方法就可以自动倒计时了，如果想走完后再走一遍自动进度调用一下`reStart()`就OK了。

如果不想自动走进度，你可以通过`setProgress()`来像系统的progress一样修改进度值。

```java
// 和系统普通进度条一样，0-100。
progressBar.setProgressType(CircleTextProgressbar.ProgressType.COUNT);

// 改变进度条。
progressBar.setProgressLineWidth(30);// 进度条宽度。

// 设置倒计时时间毫秒，默认3000毫秒。
progressBar.setTimeMillis(3500);

// 改变进度条颜色。
progressBar.setProgressColor(Color.RED);

// 改变外部边框颜色。
progressBar.setOutLineColor(Color.RED);

// 改变圆心颜色。
progressBar.setInCircleColor(Color.RED);

// 如果需要自动倒计时，就会自动走进度。
progressBar.start();

// 如果想自己设置进度，比如100。
progressBar.setProgress(100);
```

进度监听
```java
// 监听进度。
progressBar1.setCountdownProgressListener(1, progressListener);
progressBar2.setCountdownProgressListener(2, progressListener);

OnCountdownProgressListener progressListener = new OnCountdownProgressListener() {
    @Override
    public void onProgress(int what, int progress) {
        if (what == 1) {
            progressBar1.setText(progress + "%");
        } else if (what == 2) {
            progressBar2.setText(progress + "%");
        }
        // 比如在首页，这里可以判断进度，进度到了100或者0的时候，你可以做跳过操作。
    }
};
```

## 目前已知的兼容问题修复
目前`CircleTextProgressbar`在`ReletiveLayot`中高度会变大，导致进度条会有一点点扁。修复方法如下：
如果你要在`ReletiveLayot`中使用`CircleTextProgressbar`，就不要重写`onMeasure()`方法，然后在xml中指定`CircleTextProgressbar`的宽高就好，比如都指定为`50dp`，然后就没有问题啦。

# License
```
Copyright 2016 Yan Zhenjie

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

[0]: [http://www.yanzhenjie.com]
[0]: [http://blog.csdn.net/yanzhenjie1003]
