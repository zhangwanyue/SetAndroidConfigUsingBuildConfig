# Using `BuildConfig` to set up Android Config

## several ways to set up a config file for a application:

ref link: https://stackoverflow.com/a/35527922/7701089

* Method 1: Use a *.properties file with Properties
* Method 2: Use AndroidManifest.xml meta-data element
* Method 3: Use buildConfigField in your Flavor

## What is `BuildConfig`?

BuildConfig.java is generated automatically by Android build tools, and is placed into the gen folder.

## Why to choose `BuildConfig`?

项目中有一个需求，从配置文件中读取配置，加载到App中，并在编译阶段就将配置文件的数据读入，所以选用了`BuildConfig`的方式设定配置文件。（其他两种方式都是需要将配置文件载入到手机中，并在运行时读取的）

## How to use `BuildConfig`?
### Android Module

* Use BuildConfigField brings from `android` plugin

https://developer.android.com/studio/build/gradle-tips#share-custom-fields-and-resource-values-with-your-app-code

* Example

Example is in `app` module.

### Java Module

* Use this plugin which brings BuildConfig to pure Java module

https://github.com/mfuerstenau/gradle-buildconfig-plugin

* Example

Example is in `javaModule` module.

* solve problems

遇到一个问题：这个plugin生成的`BuildConfig`文件并没有被加入到 sourceDir或者 class dependencies 中，所以IDE中会报错，解决办法：
https://github.com/mfuerstenau/gradle-buildconfig-plugin/issues/16#issuecomment-339293376