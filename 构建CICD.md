# 1、更新构建模板 ./github/workflows/build.yml 模板
# 2、推送版本
```
git add .
git commit -m ''
git push
git tag v1.0.1
git push origin v1.0.1

```

# 构建token出错解决

## 解决方法
### 方法 1️⃣：使用 GitHub Personal Access Token (推荐)

在 GitHub 生成 PAT（Personal Access Token）：

进入 Settings → Developer settings → Personal access tokens → Tokens (classic)

点击 Generate new token

权限选择 repo（包括创建 Release 的权限）

在仓库设置 Secrets：

仓库 → Settings → Secrets and variables → Actions → New repository secret

名称：GH_TOKEN

值：刚生成的 PAT

workflow 使用：

env:
  GH_TOKEN: ${{ secrets.GH_TOKEN }}
