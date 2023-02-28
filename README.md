# pytest-cov-coverage-api
使用pytest-cov对web的api接口的测试用例覆盖率进行统计
## 使用命令行方式统计web接口覆盖率

### 环境准备

```shell
pip install python-cov
```

`coverage`是`python-cov`的一个依赖包，因此只要安装`pytest-cov` 就能以命令行的方式使用`coverage`

### 代码结构

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-37-29-image.png)



### 统计覆盖率步骤

#### 启动web服务

```shell
coverage run ./src/server.py
```

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-40-46-image.png)

#### 调用测试自动化脚本（自动化脚本是直接调的该服务提供的api ）

```shell
python main.py
```

在测试用例时，可以看到已经请求了web接口

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-45-29-image.png)

#### 待测试用例跑完后，ctr+c 终止web服务，可以看到生成`.coverage.*`，该文件主要是用来生成可视报告

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-47-49-image.png)

```context
`.coverage.*`文件是后面是否能生成可视化报告的关键，若没有`.coverage.*`文件，
则后面无法通过 `coverage report`或 `coverage html` 等命令生成可视化报告
```

#### 生成报告

###### 终端报告

```shell
coverage report
```

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-51-24-image.png)

##### html 报告

```shell
coverage html
```

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-52-31-image.png)

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-53-23-image.png)

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-53-51-image.png)

在当前目录下生成`/htmlcov/`，使用浏览器打开`index.html`可以看到报告

![](/Users/ashe/Library/Application%20Support/marktext/images/2023-02-28-14-59-08-image.png)



#### 更多

命令文档：[Command line usage &mdash; Coverage.py 7.2.1 documentation](https://coverage.readthedocs.io/en/7.2.1/cmd.html)



