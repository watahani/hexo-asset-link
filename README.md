# hexo-asset-link

Convert base-relative asset links to root-relative ones, so that user can insert assets like images in markdown way.

[![NPM version](https://badge.fury.io/js/hexo-asset-link.svg)](https://www.npmjs.com/package/hexo-asset-link)

## Install

```shell
$ npm i --save hexo-asset-link
```

## Config

This plugin only works when [`Asset Folders`](https://hexo.io/docs/asset-folders) feature enabled in `_config.yml`:

```yml
post_asset_folder: true
```

## Write

For example, if you have these files in `source/_post/`:

```
+-- _posts
|   +-- 2019-02-14-Test-Post.md
|   +-- 2019-02-14-Test-Post
|       +-- Test-Image.png
|       +-- Test-Other-File.pdf
```

Then in `2019-02-14-Test-Post.md`:

### Images

```markdown
![Alt Text](./2019-02-14-Test-Post/Test-Image.png "Title Text")
![Alt Text](2019-02-14-Test-Post/Test-Image.png "Title Text")
```

### Other Files

```markdown
[Text](./2019-02-14-Test-Post/Test-Other-File.pdf)
[Text](2019-02-14-Test-Post/Test-Other-File.pdf)
```

### Unrecommended Way

This way is quite dirty, and **only** works when there is **no subdirectory**, e.g. `2019-02-14-Test-Post/Sub/Directory/Test-Image.png`.

```markdown
![Alt Text](Test-Image.png "Title Text")
[Text](Test-Other-File.pdf)
```

> Writing in this way makes no sense, since vanilla markdown will **not** find asset files.