## Python的包管理及Pipenv

### @frostming

---?color=linear-gradient(90deg, #197CAA 50%, white 50%)

@snap[west span-50 text-white h3-white]
### Who Am I

- @fa[github](frostming)
- @fa[twitter](frostming90)
- @fa[qq](Tencent)
- 从 2014 年开始用 Python , 前测试，现开发
@snapend

@snap[east span-50]

![Pipenv logo](assets/images/pipenv.png)

Pipenv 维护者
@snapend

+++

![Comic image](assets/images/comic.png)

队长别开抢，是我！

---

### 提问

@ul
- 安装了包为什么提示导入失败？
- Python 版本升级了原有的依赖包呢？
@ulend

+++

![python_environemnt](assets/images/python_environment_2x.png)

+++

### Python 定位包位置的机制

- 到 `sys.prefix` 下面对应的 `Lib` 目录寻找包
- 所有 executable 均对应一个 Python 解释器
- `pip` 亦将包安装到 `sys.prefix` 下面（默认配置下）
- `PYTHONPATH` 增加额外搜索路径
