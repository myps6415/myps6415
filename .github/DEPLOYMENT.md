# 部署說明文件

本文件記錄了此 GitHub Profile README 中使用的自架服務配置方式。

## GitHub Readme Stats 自架實例

為了避免使用公共服務時遇到的穩定性問題（503 錯誤、rate limit 限制），本專案使用自架的 GitHub Readme Stats 實例。

### 部署資訊

- **服務**: [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
- **部署平台**: Vercel
- **實例 URL**: `https://my-github-stats-git-main-myps6415s-projects.vercel.app`

### 部署步驟

#### 1. 建立 GitHub Personal Access Token

1. 前往 [GitHub Settings → Tokens](https://github.com/settings/tokens)
2. 點擊 "Generate new token" → "Generate new token (classic)"
3. 設定 Token：
   - **Note**: `GitHub Readme Stats`
   - **Expiration**: 選擇 "No expiration" 或 "1 year"
   - **Scopes**: 勾選以下權限
     - ✅ `repo` (完整勾選所有子項目)
       - `repo:status`
       - `repo_deployment`
       - `public_repo`
       - `repo:invite`
       - `security_events`
     - ✅ `read:user`
4. 點擊 "Generate token" 並複製 Token（格式：`ghp_` 開頭，共 40 字元）

#### 2. 部署到 Vercel

1. 訪問 [Vercel 一鍵部署連結](https://vercel.com/import/project?template=https://github.com/anuraghazra/github-readme-stats)
2. 使用 GitHub 帳號登入 Vercel
3. 設定 Repository：
   - Repository Name: `my-github-stats`（或自訂名稱）
   - 點擊 "Create" 建立 repository
4. 設定環境變數：
   - **Name**: `PAT_1`
   - **Value**: 貼上步驟 1 建立的 GitHub Token
   - 點擊 "Add"
5. 點擊 "Deploy" 開始部署
6. 等待部署完成（通常 1-2 分鐘）

#### 3. 停用 Deployment Protection

**重要步驟**：必須停用部署保護，否則會遇到 401 錯誤。

1. 前往 Vercel 專案設定頁面
2. 在左側選單找到 "Deployment Protection"
3. 停用所有保護機制：
   - Vercel Authentication
   - Password Protection
   - Trusted IPs
   - 其他任何保護選項
4. 儲存設定

#### 4. 設定存取白名單（安全性設定）

**強烈建議**：設定 WHITELIST 環境變數，限制只有你的帳號可以使用此實例，防止他人濫用你的 Vercel 資源和 GitHub API quota。

1. 前往 Vercel 專案的 Environment Variables 頁面
2. 新增環境變數：
   - **Name**: `WHITELIST`
   - **Value**: `myps6415`（你的 GitHub 使用者名稱）
   - **Environments**: 勾選 All Environments (Production, Preview, Development)
3. 點擊 "Save" 儲存

如果需要允許多個使用者，使用逗號分隔：
```
WHITELIST=myps6415,user2,user3
```

#### 5. 重新部署

1. 前往 "Deployments" 頁面
2. 找到最新的部署
3. 點擊右側的三個點 (•••) → "Redeploy"
4. 確認重新部署

#### 6. 驗證部署與安全性

測試以下 URL 是否正常運作：

```bash
# 測試你的帳號（應該成功）
curl https://my-github-stats-git-main-myps6415s-projects.vercel.app/api?username=myps6415

# 測試其他帳號（應該被阻擋，返回 "This username is not whitelisted"）
curl https://my-github-stats-git-main-myps6415s-projects.vercel.app/api?username=octocat
```

**預期結果**：
- ✅ 你的帳號應該返回 SVG 格式的統計卡片
- ❌ 其他帳號應該返回錯誤訊息，顯示 "This username is not whitelisted"

如果測試結果符合預期，表示部署成功且安全設定正確。

### 環境變數配置

| 變數名稱 | 說明 | 必要性 | 範例值 |
|---------|------|--------|--------|
| `PAT_1` | GitHub Personal Access Token | 必要 | `ghp_xxxxxxxxxxxx` |
| `WHITELIST` | 限制特定 GitHub 使用者名稱存取（強烈建議） | 建議 | `myps6415` 或 `user1,user2` |
| `CACHE_SECONDS` | 快取時間（秒），預設 86400 (24小時) | 選用 | `43200` (12小時) |
| `EXCLUDE_REPO` | 從統計中排除特定 repository | 選用 | `repo1,repo2` |

**安全性說明**：
- `PAT_1` 是必要的，用於存取 GitHub API
- `WHITELIST` 強烈建議設定，以防止他人濫用你的實例消耗 Vercel 資源和 GitHub API quota
- 設定 `WHITELIST` 後，只有列表中的使用者可以使用此實例查詢統計資料

### 常見問題排解

#### 401 Unauthorized 錯誤

**可能原因**：
1. GitHub Token 無效或權限不足
2. Vercel 環境變數未正確設定
3. Deployment Protection 未停用

**解決方法**：
1. 驗證 Token 是否有效：
   ```bash
   curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/user
   ```
2. 確認 Vercel 環境變數 `PAT_1` 已正確設定
3. 確認已停用所有 Deployment Protection
4. 重新部署（Redeploy）

#### 503 Service Unavailable 錯誤

如果遇到此錯誤，通常表示使用的是公共實例。確認 README.md 中的 URL 是否指向自架實例。

### 維護注意事項

1. **Token 過期**：如果設定了過期時間，記得在 Token 過期前更新
2. **更新環境變數**：修改環境變數後，必須重新部署才會生效
3. **監控使用量**：Vercel 免費方案有使用限制，注意監控用量

### 使用方式

在 README.md 中使用以下格式：

```markdown
![GitHub Stats](https://my-github-stats-git-main-myps6415s-projects.vercel.app/api?username=myps6415&count_private=true&show_icons=true&theme=radical)

![Top Languages](https://my-github-stats-git-main-myps6415s-projects.vercel.app/api/top-langs/?username=myps6415&layout=compact&theme=radical)
```

### 參考資源

- [GitHub Readme Stats 官方文件](https://github.com/anuraghazra/github-readme-stats)
- [Vercel 文件](https://vercel.com/docs)
- [GitHub Personal Access Token 說明](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

---

**最後更新**：2026-01-12
**維護者**：@myps6415
