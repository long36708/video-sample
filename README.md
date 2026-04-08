# video-sample

视频样本文件仓库。

## Git LFS

本仓库使用 [Git LFS](https://git-lfs.github.com/) 管理大文件。

### 首次克隆

确保已安装 Git LFS，克隆后执行：

```bash
git lfs install
```

### 添加新的大文件

1. **确认 LFS 已跟踪对应文件类型**（查看 `.gitattributes`）：

   ```bash
   git lfs track
   ```

2. **如需新增跟踪类型**：

   ```bash
   git lfs track "*.mov"
   git lfs track "*.mp4"
   git lfs track "*.ps"
   git add .gitattributes
   git commit -m "chore: update Git LFS tracking"
   ```

3. **正常 add 和 commit 即可**，LFS 会自动接管已跟踪类型的文件：

   ```bash
   git add <file>
   git commit -m "feat: add new video file"
   ```

### 迁移已有文件到 LFS

如果大文件已被普通 Git 方式提交，需要迁移：

```bash
git lfs migrate import --include="*.mov,*.mp4,*.ps"
```

> ⚠️ `migrate import` 会重写历史，协作仓库需通知所有成员重新克隆。
