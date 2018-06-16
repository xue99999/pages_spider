# pages_spider
爬取ajax获取的数据


#comments.json 
获取到的数据

#spider.py
以下这个方法必须用contains方法来获取， 否则报错

``` python
def has_next_page(response):
    classes = response.xpath('//li[contains(@class, "next-page")]/@class').extract_first()
    return 'disabled' not in classes
```

