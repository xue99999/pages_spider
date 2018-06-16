# pages_spider
爬取ajax获取的数据

#用到的库
Selenium、PhantomJS

#爬取的页面地址
https://www.shiyanlou.com/courses/427

#comments.json 
获取到的数据

#spider.py
以下这个方法必须用contains方法来获取， 否则报错
如果是用下面这种方式写的话， 最后一页next-page 多一个disabled的类名所以报错
response.xpath('//li[@class="next-page"]/@class').extract_first()

``` python
def has_next_page(response):
    classes = response.xpath('//li[contains(@class, "next-page")]/@class').extract_first()
    return 'disabled' not in classes
```

