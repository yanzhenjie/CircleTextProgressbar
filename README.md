# CircleTextProgressbar

严振杰的主页: http://www.yanzhenjie.com
严振杰的博客: http://blog.csdn.net/yanzhenjie1003

----
# 效果预览
<image src="./image/demo.gif" width="350px"/>

#简介与使用
本质是一个TextView，所以TextView的基本属性它都有。

因为实在是太简单了，这里展示下怎么设置属性：
```java
// 和系统普通进度条一样，0-100。
progressBar.setProgressType(CircleTextProgressbar.ProgressType.COUNT);

// 改变进度条。
progressBar.setProgressLineWidth(30);// 进度条宽度。
progressBar.setProgressLineWidth(3);// 写入宽度。

// 设置倒计时时间毫秒，默认3000毫秒。
progressBar.setTimeMillis(3500);

// 改变进度条颜色。
progressBar.setProgressColor(Color.RED);

// 改变外部边框颜色。
progressBar.setOutLineColor(Color.RED);

// 改变圆心颜色。
progressBar.setInCircleColor(Color.RED);

// 模拟网易新闻跳过。
progressBar.setOutLineColor(Color.TRANSPARENT);// 外部轮廓透明。
progressBar.setInCircleColor(Color.parseColor("#AAC6C6C6"));// 中间圆为灰色。
progressBar.setProgressColor(Color.DKGRAY);// 进度条为灰色。
progressBar.setProgressLineWidth(3); // 进度条宽度为3。
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

[0]: [http://www.yanzhenjie.com]
[0]: [http://blog.csdn.net/yanzhenjie1003]