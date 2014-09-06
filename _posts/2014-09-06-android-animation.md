---
layout: post
title: Android Animation
date: 2014-09-06 15:27:00
category: Android
excerpt: Android 框架提供了非常便捷的基础设施用于实现动画效果，掌握这些API接口以及其演进历史非常重要，本文粗浅的对 Animation 框架进行了梳理，对相关API进行了介绍。
---

## API演化历史

在 *API Level 11 (Android 3.0)* 以前 *Animation* 类位于 *android.view.animation* 包中。

在 *API Level 11 (Android 3.0)* 中引入了一系列新的类，使得实现动画效果更为简单，这些新的类位于 *android.animation* 包中。

在 *API Level 12 (Android 3.1)* 中引入一些新的工具类，使得在 *View* 上实现动画效果更加简单了。

## Animation类

在 *android.view.animation* 包中包含如下几个类：

![Animation UML](/assets/images/android-animation.png)

*Animation* 是个抽象类，*Android* 提供 4 个基本动画类：

* *AlphaAnimation* : 透明度动画
* *RotateAnimation* : 旋转动画
* *ScaleAnimation* : 缩放动画
* *TranslateAnimation* : 平移动画

这些基本动画类重写了 *Animation* 类的 *applyTransformation()* 方法，这个方法第一个参数是经过 *Interpolator* 插值器计算出当前时间点的插值，第二个参数 *Transformation* 则用于实现当前时间点的变化，比如调用 *Transformation.setAlpha()* 可以改变动画对象的透明度。

*AnimationSet* 则是一些基本动画的组合，这些基本的动画可以**并行**执行也可以**串行**执行。

*AnimationUtils* 则提供了一些便捷的工具方法，比如从 *XML* 文件读取动画、Layout动画和插值器等。

```
AnimationUtils.loadAnimation(Context context, int id): Animation
AnimationUtils.loadLayoutAnimation(): LayoutAnimationController
AnimationUtils.loadInterpolator(Context context, int id): Interpolator
AnimationUtils.makeInAnimation(Context c, boolean fromLeft): Animation
AnimationUtils.makeOutAnimation(Context c, boolean toRight): Animation
AnimationUtils.makeInChildBottomAnimation(Context c): Animation
```

*View* 有一个 *View.startAnimation(Animation)* 方法，一般使用方法如下：

```java
//main.xml中的ImageView
ImageView spaceshipImage = (ImageView) findViewById(R.id.spaceshipImage);
//加载动画
Animation anima = AnimationUtils.loadAnimation(this, R.anim.hyperspace_jump);
//使用ImageView显示动画
spaceshipImage.startAnimation(anima);
```
这也意味着动画只能用在 *View* 上，另外，这些动画只是纯粹的动画而已，并不会修改 *View* 的属性，也就是说动画结束后，View还是会出现在原来的位置，这可以通过调用 *setFillAfter(true)* 来解决。

## *Animator* 类

在 *Android 3.0* 中引入了一系列新的类，位于 *android.animation* 包中，包括：

![Animator UML](/assets/images/android-animator.png)

结构貌似和 *Animation* 很类似，不过这里新增了 *AnimatorUpdateListener* 接口，这是 *Animator* 的核心，开发者可以在这个回调接口里面实现任何动画。这些类已经完全和 *View* 解耦了，理论上可以用于任何对象，比如 *Drawable* 等。

一般的调用方法：

```java
ValueAnimator anim = ValueAnimator.ofFloat(0f, 1f);
anim.setDuration(500);
anim.addUpdateListener(new ValueAnimator.AnimatorUpdateListener() {
    public void onAnimationUpdate(ValueAnimator animation) {
        Float value = (Float) animation.getAnimatedValue();        
        // do something with value...
        mImageView.setAlpha(value * 255);
    }
});
anim.start();
```

或者直接在XML中写：

```xml
<animator xmlns:android="http://schemas.android.com/apk/res/android"
        android:valueFrom="0"
        android:valueTo="100"        
        android:valueType="intType"/>
```

*ValueAnimator* 改变的是数值，而 *ObjectAnimator* 改变的是对象的属性，使用方法如下：

```java
ObjectAnimator.ofFloat(myObject, "alpha", 0f).start();
```

## *ViewPropertyAnimator* 类

在3.1中，又新引入了一些新的工具类，比如 *ViewPropertyAnimator*，并且在 *View* 类中添加了一些方法，使得对View的动画更加简单：

```java
myView.animate().x(500).y(500);
```

*View.animate()* 返回的是一个 *ViewPropertyAnimator* 对象，这个对象虽然没继承*Animator* 类，但是其接口基本相似。

## 小结

*Android* 框架提供了非常便捷的基础设施用于实现动画效果，掌握这些API接口以及其演进历史非常重要，本文粗浅的对 *Animation* 框架进行了梳理，很多细节仍有待发掘。

