---?image=assets/images/title_bg.png
@snap[east span-60]

## Python 的包管理及 Pipenv

### @frostming

@snapend

---

@snap[west span-50]

## Who Am I

@ul[list-spaced-bullets](false)

- @fa[qq] Tencent
- 开源爱好者
- 从 2014 年开始用 Python , 前测试，现开发
- Pipenv 维护者之一
@ulend
@snapend

@snap[east span-50]
![Pipenv logo](assets/images/pipenv.png)
@snapend

+++

![Comic image](assets/images/comic.png)

队长别开抢，是我！

---

## 你是否遇到过这些问题

@ul[list-spaced-bullets]

- 安装了包却提示导入失败
- Python 版本升级了，原有的命令行程序全体罢工
- 升级了某个库的版本，导致别的应用（库）挂了
@ulend

+++

![python_environemnt](assets/images/python_environment_2x.png)

+++

## Python 定位包位置的机制

@ul[list-spaced-bullets](false)

- 到 `sys.prefix` 下面对应的 `Lib` 目录寻找包
- 所有 executable 均隐式对应一个 Python 解释器
- `pip` 亦将包安装到 `sys.prefix` 下面（默认配置下）
- `PYTHONPATH` 增加额外搜索路径
@ulend

![pip-flow](assets/images/pip-flow.png)

+++

## 使用虚拟环境!

@snap[midpoint span-50]
@box[bg-green text-white box-padding](Base Interpreter#/usr/local/bin/python3.7)
@fa[arrow-down]
@box[bg-blue text-white box-padding](Virtualenv#.venv/bin/python)
@snapend

创建新的解释器，将 `path_prefix` 值改变

+++

## 最坏实践

@ul[list-spaced-bullets]

- ❌ `sudo pip install <package>`
- ❌ `sudo ln -sf /path/to/my/python /usr/bin/python`
- ❌ 使用 homebrew 安装的 Python 安装命令行程序
@ulend

+++

## 最佳实践

@ul[list-spaced-bullets]

- ✅ 每个命令行程序使用自己单独的虚拟环境，然后将 executable 软链到 `PATH` 中
- ✅ 尽量使用 Python 3 自带的 `venv` 模块
- ✅ `pipx install <package>`
@ulend

---

@snap[west span-50]

### I have...

@ul[list-spaced-bullets]

- `virtualenv`
- `virtualenvwrapper`
- `pew`
- `pyenv-venv`
- `conda`
- `direnv`
- ...
@ulend
@snapend

@snap[east fragment]

### 依赖管理@css[text-bold text-14 text-blue](?)

@snapend

---

## 我们为什么需要依赖管理

@snap[north]
@ul[list-spaced-bullets]

- 「复制」开发环境到生产环境
- 跟踪、追溯依赖版本变更
- 确定合适的依赖版本以防止冲突
@ulend
@snapend

@snap[west span-50]

+++

## requirements.txt 能解决问题吗？

@snap[west span-50]

### 抽象依赖

```
Flask
requests
```

> 开发环境使用，无需关注具体版本及次级依赖，安装最新版即可

@snapend

@snap[east span-50]
### 具体依赖

```
Flask==1.0.2
itsdangerous==1.1.0
Click==7.0
Jinja2==2.10.3
MarkupSafe==1.1.1
werkzeug==0.16.0
requests==2.22.0
idna==2.8
certifi==2019.9.11
chardet==3.0.4
urllib3==1.25.6
```

> 生产环境使用，锚定依赖版本，减少版本不匹配带来的额外风险
@snapend

@snap[south]

```bash
$ pip freeze > requirements.txt
```

@snapend
