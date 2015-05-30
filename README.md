doubanInterface python lib
===

#说明
doubanInterface 类含有如下方法：  
> get_group_booklist(group_id)                           #获取豆列书目  

> get_member_booklist(member_id, list_type = 'wish') #获取一个成员的图书列表，默认为“想读”标记  

> get_book_info(book_id)                               #获取一本书的信息  


#用法
###get_group_booklist(group_id)
####获取青年群书目
    import doubanInterface
    
    def main():  
        dbif = doubanInterface.bookIf('http://www.douban.com/doulist/36847674/', 'http://www.douban.com/doulist/14090587/')  # 初始化，设置青年群和作者群豆列地址
        booklist = dbif.get_group_booklist("youth")
        print booklist 
 
    if __name__=='__main__':   
       main()  

####获取作者群书目
    import doubanInterface
    
    def main(): 
        dbif = doubanInterface.bookIf('http://www.douban.com/doulist/36847674/', 'http://www.douban.com/doulist/14090587/')# 初始化，设置青年群和作者群豆列地址
        booklist = dbif.get_group_booklist("author")
        print booklist

    if __name__=='__main__':
        main()

返回结果片段：  
> [{'book_name': 'Rise of the Robots', 'book_id': '26312794'}, {'book_name': '\xe7\xa7\x91\xe5\xad\xa6\xe4\xb8\x8e\xe6\x96\xb9\xe6\xb3\x95', 'book_id': '5373898'}, {'book_name': '\xe5\x88\x9b\xe9\x80\xa0\xe5\x8a\x9b\xe6\x89\x8b\xe5\x86\x8c', 'book_id': '1487698'},
......


###get_member_booklist(member_id, list_type = 'wish')
####获取阳志平老师的“在读”书列表
    import doubanInterface
    
    def main(): 
        dbif = doubanInterface.bookIf('http://www.douban.com/doulist/36847674/', 'http://www.douban.com/doulist/14090587/') # 初始化，设置青年群和作者群豆列地址
        booklist = dbif.get_member_booklist('ouyangzhiping',"reading")
        print booklist

    if __name__=='__main__':
        main()

####获取阳志平老师的“想读”书列表
    import doubanInterface
    
    def main(): 
        dbif = doubanInterface.bookIf('http://www.douban.com/doulist/36847674/', 'http://www.douban.com/doulist/14090587/') # 初始化，设置青年群和作者群豆列地址
        booklist = dbif.get_member_booklist('ouyangzhiping')
        print booklist

    if __name__=='__main__':
        main()

####获取阳志平老师的“已读”书列表
    import doubanInterface
    
    def main(): 
        dbif = doubanInterface.bookIf('http://www.douban.com/doulist/36847674/', 'http://www.douban.com/doulist/14090587/') # 初始化，设置青年群和作者群豆列地址
        booklist = dbif.get_member_booklist('ouyangzhiping', "done")
        print booklist

    if __name__=='__main__':
        main()

返回结果片段：  
> [{'rating': 0, 'book_name': '\xe4\xbd\x95\xe4\xbb\xa5\xe4\xb8\xad\xe5\x9b\xbd', 'book_id': '25850080'}, {'rating': 0, 'book_name': '\xe5\x8b\x9d\xe5\x88\xa9\xe7\x9a\x84\xe5\x9b\xb0\xe5\xa2\x83', 'book_id': '6148964'}, {'rating': 0, 'book_name': 'The Mind and Heart of the Negotiator', 'book_id': '11714487'}, {'rating': 0, 'book_name': 'Montessori', 'book_id': '3411981'}, 
......

###get_book_info(book_id)
####获取douban id为26340992的图书详细信息
    import doubanInterface
    
    def main(): 
        dbif = doubanInterface.bookIf('http://www.douban.com/doulist/36847674/', 'http://www.douban.com/doulist/14090587/') # 初始化，设置青年群和作者群豆列地址
        bookInfo = dbif.get_book_info('26340992')
        print bookInfo

    if __name__=='__main__':
        main()

返回结果片段：  
> {u'rating': {u'max': 10, u'numRaters': 2, u'average': u'0.0', u'min': 0}, u'subtitle': u'', u'pubdate': u'2015-3', u'image': u'http://img6.douban.com/mpic/s28023092.jpg', u'binding': u'', u'images': {u'small': u'http://img6.douban.com/spic/s28023092.jpg', u'large': u'http://img6.douban.com/lpic/s28023092.jpg',
......
