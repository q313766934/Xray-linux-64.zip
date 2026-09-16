# Xray-linux-64

境外服务器部署用的 Xray 离线资源包（linux amd64）。

## 文件说明

| 文件 | 说明 |
|------|------|
| `Xray-linux-64.zip` | Xray 离线安装包（约 21 MB） |
| `Xray-linux-64.zip.dgst` | 完整性校验摘要（MD5/SHA1/SHA256/SHA512） |

## 境外服务器下载示例

私有仓库需 Token（`repo` 读权限或 Fine-grained Contents Read）：

```bash
export GITHUB_TOKEN="your_token"
export TAG="v1.0.0"
export REPO="q313766934/Xray-linux-64"

curl -fsSL -H "Authorization: Bearer ${GITHUB_TOKEN}" -L \
  -o Xray-linux-64.zip \
  "https://github.com/${REPO}/releases/download/${TAG}/Xray-linux-64.zip"

curl -fsSL -H "Authorization: Bearer ${GITHUB_TOKEN}" -L \
  -o Xray-linux-64.zip.dgst \
  "https://github.com/${REPO}/releases/download/${TAG}/Xray-linux-64.zip.dgst"

grep SHA2-256 Xray-linux-64.zip.dgst | awk '{print $2 "  Xray-linux-64.zip"}' | sha256sum -c -
```

也可直接从仓库根目录 clone / raw 拉取（见 Releases 或 main 分支）。
