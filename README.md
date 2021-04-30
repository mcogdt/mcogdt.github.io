# mcogdt.github.io

def urlrep(url):
    import urllib.request as ur
    uh = {
        "User-Agent": "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.81 Safari/537.36 SE 2.X MetaSr 1.0"
    }
    request = ur.Request(url, headers=uh)
    response = ur.urlopen(request)
    return response.read().decode("utf-8")
def spider(url):
    from lxml import etree
    response = urlrep(url)
    ht = etree.HTML(response)
    list = ht.xpath("//a[@class='card-view d-flex text-decoration-none color-tertiary']/@href")
    return list
print(spider("https://adultsearch.com/delaware/wilmington/female-escorts"))
