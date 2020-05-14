# Python 开发环境搭建

本教程针对 [Virtualenv](https://virtualenv.pypa.io/en/latest/) 与 [Visual Studio Code](https://code.visualstudio.com/)。 

1. 安装 Virtualenv（VS Code 的安装不再赘述）：

```bash
pip install virtualenv
```

2. 测试安装是否成功：

```bash
virtualenv --version
```

3. 新建一个测试项目目录，并进入：

```bash
mkdir virtual-env-test
cd virtual-env-test
```

4. 创建虚拟环境

```bash
virtualenv venv
```

其中 `venv` 是存放虚拟环境配置以及安装包的地方。这个名称随便命名，但是通常使用 `venv` 或 `env`，以便大家快速明白这个目录的作用。

5. 使用 VS Code 打开测试项目：

```bash
code .
```

6. 配置 Python 解释器：

使用 `Ctrl+Shift+P` 打开命令面板，输入 `Python: Select Interpreter`，选择刚刚创建的 `venv`。VS Code 会自动帮我们执行虚拟环境激活的任务，而不需要我们手动执行 active 脚本。

```powershell
PS C:\Users\Levid\projects\virtual-env-test> & c:/Users/Levid/projects/virtual-env-test/venv/Scripts/Activate.ps1
(venv) PS C:\Users\Levid\projects\virtual-env-test> 
```

其中最前面的 `(venv)` 表示我们已经进入虚拟环境，如需退出，使用 `deactivate` 命令：

```powershell
(venv) PS C:\Users\Levid\projects\virtual-env-test> deactivate
PS C:\Users\Levid\projects\virtual-env-test> 
```

VS Code 配置参见：[Environments](https://code.visualstudio.com/docs/python/environments)。

1. 修改 pip 镜像（可选，但是建议更改）：

在 `venv` 目录中新建 `pip.ini` 文件，文件中使用以下配置：

```ini
[global]
index-url=http://mirrors.aliyun.com/pypi/simple/

[install]
trusted-host=mirrors.aliyun.com
```
国内可用的镜像：

- 阿里云 http://mirrors.aliyun.com/pypi/simple/
- 豆瓣(douban) http://pypi.douban.com/simple/
- 网易 https://mirrors.163.com/pypi/simple/
- 清华大学 https://pypi.tuna.tsinghua.edu.cn/simple/
- 中国科学技术大学 http://pypi.mirrors.ustc.edu.cn/simple/

关于 `pip` 的配置内容参见：[pip User Guide](https://pip.pypa.io/en/stable/user_guide/#configuration)。
