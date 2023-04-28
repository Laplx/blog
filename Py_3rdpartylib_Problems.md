# Python 第三方库管理等问题

> 以下均为我在碰到类似问题搜索并尝试后自己判断的结论，**无法保证正确性与普适性**。  
> 标有 [?] 为不清楚或待补充，[*] 为特殊情况或附注  
> 欢迎指正和补充，希望有所帮助！  
> 如果发现本文对你没有帮助，请上网探索：  
> <鸣谢> CSDN  知乎  官方文档  SatckOverflow  博客园  掘金  其他网站

### 1. 导入库失败

常见提示：`No module named xxx`  `DLL failed` 等

常见出现的三方库：`import matplotlib` `import docx` `import sqlite3` `import scrapy` 等等  
（如ipython在没有sqlite3时无法启用历史命令的功能，在启动ipython时会提示）

1. 不在搜索路径内：

   可以在 `sys.path` 查看，或各自IDE的面板选项里也可以显示和添加

   - 此次运行暂时加入：

     `import sys`  `sys.path.append(path)` 加入列表

   - 对某些包打补丁：

     在如anaconda3/Lib/site-packages下新建.pth文件（名称随意），内容为要加入的路径（可相对路径）  
     从Lib上级目录起其下的所有.pth文件都能被加入搜索路径

   - [?] 永久修改配置 PYTHONPATH ...

2. **版本不匹配**：

   非常常见，可上网搜索或查阅官方文档或conda会自己提示，确定依赖的包和py ipy的版本范围（更新跟不上，似乎 numpy pillow 等版本容易过高）

   `pip` / `conda` 重新管理安装库  
   `pip install --upgrade` 更新   
   `pip unistall` 卸载，再重装   
   `--user` 部分需要更高权限，需要加此参数  
   `pip install package==version` 指定安装版本

3. DLL缺失：

   原因不明，但我的ipython的sqlite3就这么治好了

   anaconda/DLLs 下要有对应的sqlite3.dll文件，可从anaconda/Library/bin里复制出来

### 2. Python与Anaconda

我的电脑里后来才发现有三个py内核，conda带的、微软商店下的、官网装的，建议清楚自己使用的解释器版本和地址  
（我发现有些安装选择了Global，不过在用户文件夹下似乎有一个'代理'的地方[?]，环境变量直接使用WindowsApps下的地址非根权限会拒绝访问）  
一般ipython在anaconda3\Scripts下，打开后 `pwd` 可能不同

- [*] 小白学习时间：

  .py默认运行方式可以到设置更改，如果想修改右键菜单，运行regedit添删注册表的项

  vscode ctrl+shift+P调出设置搜索 Python: Select Interpreter 查看并更换Python解释器

  白色图标的是pyw文件，运行不弹窗  
  带火箭的是Python Launcher，它根据文件头说明选择版本运行  
  pyc为二进制文件，即解释前先编译成的字节码（PythonCodeObject，可反编译），
  当被作为模块导入时会生成（运行后认为要写回硬盘，节省下次加载的时间），存于\__pycache__文件夹

- 关于cmd命令：

  可用 where 查看 pip python 等命令的调用对象及优先级

  直接下方查找栏找环境变量设置比较快  
  命令会先搜索系统变量后搜索用户变量  
  命令行终端需要重开才能更新环境变量等设置

  python.exe位于的文件夹路径决定了python命令，一般pip可能位于本文件夹或其\Scripts下

  通常 `python3.10 -m pip` 可以管理特定3.10版本的解释器

- [?] `pip` 与 `conda` ：

  conda install 安装在anaconda3/pkgs下，conda能够管理各环境而pip只对特定环境进行包管理  
  pip install（conda里的python的pip）安装在Lib/site-packages，这个文件夹有可能不认需要添加

  conda命令一直停留在 `Solving environment` 的问题：翻墙（从网上看可能还有其他不少原因会导致）

  `conda activate` 激活环境，'base'是基础环境，可以尝试virtualenv，使用环境隔离

（写不动了:joy:）

其他解决方案：各种重装、使用anaconda下的IDE（包都装了，基本不存在问题）



<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">知识共享署名 4.0 国际许可协议</a>进行许可。