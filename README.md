## VideoCutView 视频裁剪view 带帧预览
![image](https://github.com/libq/VideoCutView/blob/master/view.png)

## 1.配置
step 1:  project  build.gradle
```
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}


```
step 2: module build.gradle

```
	dependencies {
	        compile 'com.github.libq:VideoCutView:1.0.0'
	}

```


## 2.使用

# java 

```

cut.getSuitImageCount(new VideoCutView.GetImageCountCallback() {
            @Override
            public void invoke(int count) {
                String root =Environment.getExternalStorageDirectory().getAbsolutePath();
                //本地图片

                String imgPath = root+ File.separator +"Pictures/03 演示图片.jpg";
                ArrayList<String> paths = new ArrayList<>();
                for(int i = 0 ; i<=count ;i++){
                    paths.add(imgPath);
                    //"http://p3.wmpic.me/article/2017/11/08/1510105952_KopFLXPj.jpg"
                }
                cut.setImageUrls(paths);
            }
        });

       cut.setVideoDuration(10000);
       cut.setCutMinDuration(3000);
       cut.setOnCutBorderScrollListener(new VideoThumbnailView.OnCutBorderScrollListener() {
            @Override
            public void onScrollBorder(float start, float end) {
                Log.e("Main","###### start ="+start+"   end = "+end);
            }
        });
```


# xml
```

```

