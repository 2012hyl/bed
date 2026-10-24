# bed · 个人图床

把图片 / 音频 / 视频扔进这个仓库，拿直链到处用。

## 三种直链（上传文件后任选）

以上传 `cat.jpg` 为例：

| 类型 | URL | 适合 |
|---|---|---|
| raw 直链 | `https://raw.githubusercontent.com/2012hyl/bed/main/cat.jpg` | 图片、音频、25MB 以内文件 |
| jsDelivr CDN | `https://cdn.jsdelivr.net/gh/2012hyl/bed@main/cat.jpg` | 全球加速、图片音频（20MB 以内） |
| Pages 链接 | `https://2012hyl.github.io/bed/cat.jpg` | 大文件、视频 |

## 怎么上传

1. **网页上传（最省事）**：打开 https://github.com/2012hyl/bed → Add file → Upload files → 拖入文件 → Commit（25MB 以内推荐）
2. **git push**：克隆仓库后 `git add 文件 && git commit && git push`
3. **API 上传**：`PUT https://api.github.com/repos/2012hyl/bed/contents/<文件名>`（body 里放 base64）

## 限制

- 单文件上限 100MB（超过需 Git LFS）
- raw 直链对 25MB 以上文件不生效（会返回错误页），大视频请用 Pages 链接
- jsDelivr 缓存上限 20MB，且有 CDN 缓存延迟
- 仓库保持 public，私有后所有直链失效

## 引用示例

```html
<img src="https://raw.githubusercontent.com/2012hyl/bed/main/图片名.jpg">
<audio src="https://raw.githubusercontent.com/2012hyl/bed/main/音频名.mp3" controls></audio>
<video src="https://2012hyl.github.io/bed/视频名.mp4" controls></video>
```