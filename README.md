# RxFetch

an easy to use http request library based on RxJava & OkHttp

一个简单易用的Http请求库，　基于RxJava和OkHttp封装

支持类型自动转换，支持Gson　、　Moshi, 可扩展
```
        OkHttpClient build = new OkHttpClient.Builder().build();
        fetch = new RxFetch(build, new GsonTypeAdapter(), new JsoupTypeAdapter());
```

```
        fetch.<Bean>get("http://example.com/get", params,Bean.class)
                .observeOn(Schedulers.io())
                .subscribeOn(AndroidSchedulers.mainThread())
                .subscribe(s -> {
                    System.out.println(s.msg);
                    }
                }, throwable -> fail());
```
