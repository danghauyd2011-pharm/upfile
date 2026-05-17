# TeleDrive — GitHub Pages Setup

## Cấu trúc repo

```
repo/
├── index.html                    ← app chính (không sửa)
├── .gitignore                    ← đã có config.js
├── .github/
│   └── workflows/
│       └── deploy.yml            ← tự động deploy khi push
└── README.md
```

> `config.js` **không commit vào repo** — được sinh tự động lúc deploy từ Secrets.

---

## Setup lần đầu (làm 1 lần cho mỗi repo)

### Bước 1 — Thêm Secrets vào GitHub

Vào repo trên GitHub → **Settings → Secrets and variables → Actions → New repository secret**

Thêm 3 secrets:

| Name | Value |
|------|-------|
| `BOT_TOKEN` | token bot của repo này, VD: `123456789:ABCdef...` |
| `BOT_CHAT_ID` | chat ID, VD: `-1001234567890` |
| `BOT_LABEL` | tên gợi nhớ, VD: `Bot Repo 1` |

### Bước 2 — Bật GitHub Pages

Vào repo → **Settings → Pages**
- Source: chọn **GitHub Actions**
- Bấm Save

### Bước 3 — Deploy

Push bất kỳ thay đổi lên `main`, hoặc vào **Actions → Deploy to GitHub Pages → Run workflow**.

---

## Dùng cho nhiều repo

Copy toàn bộ repo này sang repo 2, chỉ cần đổi **Secrets** khác token — file code giữ nguyên.
