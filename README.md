[![](https://jitpack.io/v/otoclashmediatama/RvBanner.svg)](https://jitpack.io/#otoclashmediatama/RvBanner)

Introduction
RecyclerBanner is a custom control that uses RecycleView to implement a carousel chart.


Please note that this library is currently supported on android API 19 and above.

---

### Setup

##### build.gradle (project)
```groovy
allprojects {
    repositories {
        ...
        maven {
            url 'https://jitpack.io'
        }
    }
}
```

#### build.gradle (app)
```groovy
dependencies {
    ...
    implementation 'com.github.otoclashmediatama:RvBanner:1.1.9'
}
```

### Basic Usage
```xml
...


        <com.library.swrevo.rvbanner.BannerLayout
            android:id="@+id/recycler"
            android:layout_width="match_parent"
            android:layout_height="200dp"
            app:autoPlaying="true"
            app:centerScale="1.3"
            app:itemSpace="20"
            app:moveSpeed="1.8"/>


...
```

#### XML
```xml
...


        <com.library.swrevo.rvbanner.BannerLayout
            android:id="@+id/recycler_ver"
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:layout_marginTop="10dp"
            app:orientation="vertical"
            app:showIndicator="false"/>


...
```


#### Java
Demo Activity:
```java

public class MainActivity extends AppCompatActivity implements BannerLayout.OnBannerItemClickListener {


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        BannerLayout  recyclerBanner =  findViewById(R.id.recycler);
        BannerLayout bannerVertical =  findViewById(R.id.recycler_ver);

        List<String> list = new ArrayList<>();
        list.add("http://img0.imgtn.bdimg.com/it/u=1352823040,1166166164&fm=27&gp=0.jpg");
        list.add("http://img3.imgtn.bdimg.com/it/u=2293177440,3125900197&fm=27&gp=0.jpg");
        list.add("http://img3.imgtn.bdimg.com/it/u=3967183915,4078698000&fm=27&gp=0.jpg");
        list.add("http://img0.imgtn.bdimg.com/it/u=3184221534,2238244948&fm=27&gp=0.jpg");
        list.add("http://img4.imgtn.bdimg.com/it/u=1794621527,1964098559&fm=27&gp=0.jpg");
        list.add("http://img4.imgtn.bdimg.com/it/u=1243617734,335916716&fm=27&gp=0.jpg");
        WebBannerAdapter webBannerAdapter=new WebBannerAdapter(this,list);
        webBannerAdapter.setOnBannerItemClickListener(new BannerLayout.OnBannerItemClickListener() {
            @Override
            public void onItemClick(int position) {
                Toast.makeText(MainActivity.this, "点击了第  " + position+"  项", Toast.LENGTH_SHORT).show();
            }
        });

        WebBannerAdapter WebBannerAdapter2 =new WebBannerAdapter(this,list);
        WebBannerAdapter2.setOnBannerItemClickListener(new BannerLayout.OnBannerItemClickListener() {
            @Override
            public void onItemClick(int position) {
                Toast.makeText(MainActivity.this, "点击了第  " + position+"  项", Toast.LENGTH_SHORT).show();
            }
        });
        recyclerBanner.setAdapter(webBannerAdapter);
        bannerVertical.setAdapter(WebBannerAdapter2);
    }


    public void jump(View view) {
        startActivity(new Intent(MainActivity.this, NormalActivity.class));
    }
    public void jumpOverFlying(View view) {
        startActivity(new Intent(MainActivity.this, OverFlyingActivity.class));
    }

    @Override
    public void onItemClick(int position) {

    }
}

```

## License



     Licensed under the Apache License, Version 2.0 (the "License");
     you may not use this file except in compliance with the License.
     You may obtain a copy of the License at

         http://www.apache.org/licenses/LICENSE-2.0

     Unless required by applicable law or agreed to in writing, software
     distributed under the License is distributed on an "AS IS" BASIS,
     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
     See the License for the specific language governing permissions and
     limitations under the License.

## Thanks
Part of the code is used [ViewPagerLayoutManager](https://github.com/leochuan/ViewPagerLayoutManager)
Old Source Library Project From [ren93RecyclerBanner](https://github.com/ren93/RecyclerBanner)
