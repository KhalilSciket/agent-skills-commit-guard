# commit-guard

在專案發佈前，以**非技術角度**自動審查安全問題——登入保護、權限管控、防呆驗證、憑證洩漏等。

專為透過 Claude Code Agent 建立產品的非開發背景團隊設計。

---

## 安裝

在終端機執行以下指令：

```bash
git clone https://github.com/KhalilSciket/agent-skills-commit-guard.git /tmp/commit-guard-install && mkdir -p ~/.claude/skills && cp -r /tmp/commit-guard-install/commit-guard ~/.claude/skills/ && rm -rf /tmp/commit-guard-install && echo "✅ commit-guard 安裝完成"
```

安裝後在任何專案都能使用，無需重複安裝。

---

## 使用方式

在 Claude Code 對話框輸入：

```
/commit-guard
```

---

## 審查項目

| 項目 | 說明 |
|------|------|
| 登入機制 | 是否需要帳號才能進入系統 |
| 權限管控 | 不同角色是否有不同操作限制 |
| 防呆驗證 | 表單輸入是否有格式檢查 |
| 危險操作確認 | 刪除等不可逆操作是否需二次確認 |
| 資料隔離 | 使用者是否只能看到自己的資料 |
| 錯誤處理 | 系統出錯時是否顯示友善訊息 |
| 操作紀錄 | 重要操作是否有 log |
| 自動登出 | Session 是否會過期 |
| 憑證安全 | 是否有 API key 或密碼洩漏風險 |

---

## 報告格式

審查完成後會輸出：

- 🔴 **立即修復** — 發佈後可能造成資料外洩或被濫用
- 🟡 **建議改善** — 不影響發佈，但實際使用時可能遇到麻煩
- ✅ **已具備** — 確認到位的防護項目

每個問題都附上**白話說明**與可直接貼給 Agent 的**修復指令**。
