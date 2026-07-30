## 前提环境

1. vscode
2. git

## 配置流程

1. 打开powershell安装uv：

```
winget install -e --id astral-sh.uv
```

2. 检查：

```
code --version
git --version
uv --version
```

3. powershell安装VS Code Python插件：

```
code --install-extension ms-python.python
```

4. 用uv安装Python：

```
uv python install 3.12
```

5. 查看已安装版本：

```
uv python list --only-installed
```

查看解释器路径：

```
uv python find 3.12
```

## 新建工程

1. 工程目录下，运行powershell：

```
New-Item -ItemType Directory -Path D:\Code -Force
Set-Location D:\Code

uv init --python 3.12 hello-python
Set-Location hello-python

uv sync
code .
```

其中：

- 要把D:\Code 换成实际工程路径。

- `uv init`：初始化工程。

- `--python 3.12`：指定工程Python版本。

- `uv sync`：创建 `.venv`，解析并安装依赖。

- `code .`：在VS Code中打开当前工程。