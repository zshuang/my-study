#安装pip

###Python和系统版本支持列表
> pip可以在以下版本的CPython下运行：2.6、2.7、3.1、3.2、3.3、3.4和pypy。  
> pip可以在Unix/Linux, OS X和Window系统中运行

###使用脚本安装pip
1. 要安装pip，需要下载[get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)
2. 然后运行一下命令（需要管理员权限）  
	$ python get-pip.py   
>如果没有安装` setuptools `，` get-pip.py `会帮你安装
>如果已经安装了` setuptools `，可以运行下面命令进行升级
>	`pip install -U setuptools`  
3. 使用软件管理器安装  
在Linux系统中，pip通常可以在系统的软件管理器中安装，不过通过此方法安装的一般不会是最新版本的pip  
Debian和Ubuntu：
	$ sudo apt-get install python-pip
Fedora:
	$ sudo yum install python-pip

###遇到的问题
在window下面安装时，报错如下：   
    UnicodeDecodeError：‘ascii’ codec can't decode byte 0xb0 in position 1: ordinal not in range(128)

解决办法：  
打开`C:\Python27\Lib`下的`mimetypes.py`文件，找到`default_encoding = sys.getdefaultencoding()`。   
在这行前面添三行：    
    if sys.getdefaultencoding() != 'gbk':
	    reload(sys)
	    sys.setdefaultencoding('gbk')
    default_encoding = sys.getdefaultencoding()  

###参考：
[setuptools,pip,install,UnicodeDecodeError: 'ascii' codec can't decode byte.原因和解决方案](http://blog.csdn.net/hugleecool/article/details/17996993)      
[pip介绍与使用](http://zhonghuan.info/2014/10/01/pip%E4%BB%8B%E7%BB%8D%E4%B8%8E%E4%BD%BF%E7%94%A8/)