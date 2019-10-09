---?image=assets/images/title_bg.png
@snap[east span-60]
## Python的包管理及Pipenv

### @frostming
@snapend
---

@snap[west span-50]
## Who Am I
@ul(false)
- @fa[qq] Tencent
- 开源爱好者
- 从 2014 年开始用 Python , 前测试，现开发
- Pipenv维护者之一
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

创建新的解释器，将 `path_prefix` 值改写

+++

## 最坏实践
@ul[list-spaced-bullets]
- ❌ `sudo ln -sf /path/to/my/python /usr/bin/python`
- ❌ `sudo pip install <package>`
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
