# Public APIs 脚本

此目录包含 Public APIs 使用的所有验证和测试脚本。

```bash
scripts
│   github_pull_request.sh  # 用于验证 Pull Request 的更改
│   requirements.txt  # 包含 validate 包的依赖项
│
├───tests  # 包含 validate 包的所有单元测试
│       test_validate_format.py
│       test_validate_links.py
│
└───validate  # validate 包
        format.py
        links.py
```

## 安装依赖

您必须安装 [python](https://www.python.org/) 才能使用这些脚本。

还需要安装验证包的依赖项，请使用 [pip 包管理器](https://pypi.org/project/pip/) 进行安装：

```bash
$ python -m pip install -r scripts/requirements.txt
```

## 运行验证

要运行 `README.md` 文件的格式验证，请在 public-apis 的根目录中执行：

```bash
$ python scripts/validate/format.py README.md
```

要运行 `README.md` 文件的链接验证，请在 public-apis 的根目录中执行：

```bash
$ python scripts/validate/links.py README.md
```

由于需要检查的链接很多，此过程可能需要一些时间。如果您的目标不是检查链接是否有效，您可以仅检查重复链接。请运行：

```bash
$ python scripts/validate/links.py README.md -odlc
```

*`-odlc` 是 `--only_duplicate_links_checker` 的缩写*

## 运行测试

要运行所有测试，需要切换到 scripts 目录：

```bash
$ cd scripts
```

然后运行：

```bash
$ python -m unittest discover tests/ --verbose
```

要仅运行格式测试，请运行：

```bash
$ python -m unittest discover tests/ --verbose --pattern "test_validate_format.py"
```

要仅运行链接测试，请运行：

```bash
$ python -m unittest discover tests/ --verbose --pattern "test_validate_links.py"
```
