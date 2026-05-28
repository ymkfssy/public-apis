# 贡献指南 - public-apis

> 虽然我们感谢大量的 Pull Request 和社区参与，但有些 Pull Request 是专门为了推销提供付费解决方案的公司 API 而提交的。本 API 列表不是营销工具，而是帮助社区构建应用程序并快速、轻松地使用免费公共 API 的工具。被识别为营销尝试的 Pull Request 将不被接受。
>
> 请确保您要添加的 API 具有完全的免费访问权限或至少有一个免费套餐，并且在提交之前不依赖于购买设备/服务。一个会被拒绝的例子是用于控制智能插座的 API——API 本身是免费的，但您必须购买智能设备。
>
> 感谢您的理解！:)

## 格式要求

当前 API 条目格式：

| API | 描述 | Auth | HTTPS | CORS | 调用此 API |
| --- | --- | --- | --- | --- | --- |
| API 名称（链接到 API 文档） | API 描述 | 此 API 是否需要身份验证？ * | API 是否支持 HTTPS？ | API 是否支持 [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)？ * | [此 API 是否具有公共 Postman Collection？](https://learning.postman.com/docs/publishing-your-api/run-in-postman/creating-run-button/) | 

示例条目：

```
| [NASA](https://api.nasa.gov) | NASA 数据，包括图像 | No | Yes | Yes | [在 Postman 中运行的按钮]
```

\* 目前，`Auth` 字段仅接受以下输入：

* `OAuth` - _API 支持 OAuth_
* `apiKey` - _API 使用私有密钥字符串/令牌进行身份验证——请尽量使用正确的参数_
* `X-Mashape-Key` - _可能需要发送的请求头名称_
* `No` - _API 无需身份验证即可运行_
* `User-Agent` - _发送 API 请求时需要包含的请求头名称_

\* 目前，`CORS` 字段仅接受以下输入：

* `Yes` - _API 支持 CORS_
* `No` - _API 不支持 CORS_
* `Unknown` - _未知 API 是否支持 CORS_

\* 对于"调用此 API"列，添加一个指向 Postman 集合的链接。您可能需要[创建一个集合](https://learning.postman.com/docs/getting-started/first-steps/creating-the-first-collection/)来创建"在 Postman 中运行"按钮。


_如果没有正确的 [CORS 配置](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)，API 将只能在服务端使用。_

在您的分支上创建包含更改的分支后，就可以[提交 Pull Request][pr-link] 了。

*在向 Public APIs 提交 Pull Request 时，请遵循以下指南*

## Pull Request 指南

* 切勿添加已列出的 API 的更新/新版本，旧版本的 API 将会被弃用。
* 继续遵循每个分类内已有的字母顺序排列。
* 每个表格列的两侧应填充一个空格。
* 描述不应超过 100 个字符。
* 如果某个 API 似乎属于多个分类，请将其放在与其提供的服务最相符的分类中。例如，Instagram API 被列在 `社交` 分类下，因为它主要是一个社交网络，尽管它也可以归入 `摄影` 分类。
* 每个 Pull Request 只添加一个链接。
* 确保 PR 标题格式为 `Add Api-name API`，*例如*：`Add Blockchain API`
* 使用简短且有描述性的提交信息。*例如*：❌`Update Readme.md`  ✔ `Add Blockchain API to Cryptocurrency`
* 在提交新的 Pull Request 或 Issue 之前，请先搜索已有的内容，您的可能是重复的。
* 不要在 API 名称中提及 TLD（顶级域名）。*例如*：❌Gmail.com ✔Gmail
* 请确保 API 名称不以 `API` 结尾。*例如*：❌Gmail API ✔Gmail
* 请确保 API 有适当的文档。
* 请确保在打开 Pull Request 之前将所有提交压缩在一起。如果您的 Pull Request 在审查后需要修改，请务必也将所有额外的提交一起压缩。[此 Wiki 页面][squash-link] 概述了压缩过程。
* 将您的 Pull Request 指向 `public-apis` 的 `master` 分支。

一旦您提交了 Pull Request，合作者可以审查您的更改，并决定是否合并（拉取）您的更改。

### Pull Request 小贴士

* [Fork][fork-link] 仓库并在本地 [clone][clone-link] 它。
通过将其添加为 [remote][remote-link] 来将本地仓库连接到原始的 `upstream` 仓库。
经常从 `upstream` 拉取更改，以保持同步，这样在提交 Pull Request 时，
合并冲突的可能性会更小。查看更详细的说明 [这里][syncing-link]。
* 为您的编辑创建一个 [branch][branch-link]。
* 按照上述项目风格进行贡献。这有助于合作者更容易地合并，
也便于其他人未来理解和维护。

### 打开的 Pull Request

一旦您打开了 Pull Request，将围绕您提出的更改展开讨论。

其他贡献者和用户可能会参与讨论，但最终决定由合作者做出。

在讨论过程中，您可能会被要求对 Pull Request 进行一些修改。

如果需要，请向您的分支添加更多提交并推送——它们将自动进入现有的 Pull Request。但不要忘记压缩它们。

打开 Pull Request 将触发构建，以验证项目中所有链接的有效性。构建完成后，**请确保构建已通过**。如果构建未通过，请查看构建日志并更正您的贡献中发现的任何错误。

*感谢您成为本项目的一部分，我们期待尽快收到您的消息！*

[branch-link]: <http://guides.github.com/introduction/flow/>
[clone-link]: <https://help.github.com/articles/cloning-a-repository/>
[fork-link]: <http://guides.github.com/activities/forking/>
[oauth-link]: <https://en.wikipedia.org/wiki/OAuth>
[pr-link]: <https://help.github.com/articles/creating-a-pull-request/>
[remote-link]: <https://help.github.com/articles/configuring-a-remote-for-a-fork/>
[syncing-link]: <https://help.github.com/articles/syncing-a-fork>
[squash-link]: <https://github.com/todotxt/todo.txt-android/wiki/Squash-All-Commits-Related-to-a-Single-Issue-into-a-Single-Commit>
