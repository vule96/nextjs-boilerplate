# Contributing Guide

## Commit Convention

Dự án này sử dụng [Conventional Commits](https://www.conventionalcommits.org/) để đảm bảo commit messages có cấu trúc rõ ràng và tự động tạo changelog.

### Format

```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types

| Type       | Mô tả                                       |
| ---------- | ------------------------------------------- |
| `feat`     | Thêm tính năng mới                          |
| `fix`      | Sửa lỗi                                     |
| `docs`     | Thay đổi tài liệu                           |
| `style`    | Thay đổi code style (không ảnh hưởng logic) |
| `refactor` | Refactor code                               |
| `perf`     | Cải thiện performance                       |
| `test`     | Thêm/sửa tests                              |
| `chore`    | Thay đổi build process, dependencies, etc.  |
| `ci`       | Thay đổi CI/CD                              |
| `build`    | Thay đổi hệ thống build                     |
| `revert`   | Revert commit trước đó                      |

### Ví dụ

```bash
# Thêm tính năng mới
feat(auth): add login with Google OAuth

# Sửa lỗi
fix(api): resolve 500 error on user profile endpoint

# Thay đổi nhỏ không ảnh hưởng logic
style(ui): format button component with prettier

# Cập nhật tài liệu
docs(readme): update installation instructions

# Breaking change
feat(api)!: change response format for /users endpoint
```

### Scope (tùy chọn)

Scope mô tả phần của codebase bị ảnh hưởng:

- `api` - API routes
- `ui` - UI components
- `auth` - Authentication
- `db` - Database
- `config` - Configuration

## Workflow

### Commit bằng Commitizen (Khuyến nghị)

```bash
# Thay vì git commit -m "..."
npm run commit
# hoặc
npx cz
```

### Commit thông thường

```bash
git add .
git commit -m "feat: add new feature"
```

## Git Hooks

Dự án sử dụng Lefthook để chạy các hooks:

### Pre-commit

- Chạy ESLint + Prettier + Knip trên các file staged
- Nếu có lỗi không fix được, commit sẽ bị block

### Commit-msg

- Validate commit message theo conventional commits
- Nếu không đúng format, commit sẽ bị block

### Pre-push

- Chạy TypeScript type check trước khi push

## Scripts

| Script                 | Mô tả                    |
| ---------------------- | ------------------------ |
| `npm run lint`         | Chạy ESLint              |
| `npm run lint:fix`     | Auto-fix ESLint errors   |
| `npm run format`       | Format code với Prettier |
| `npm run format:check` | Kiểm tra format          |
| `npm run commit`       | Commit với Commitizen    |

## Checklist trước khi commit

- [ ] Code đã được format (Format on Save hoặc `npm run format`)
- [ ] Không còn lỗi ESLint (`npm run lint`)
- [ ] Commit message đúng format conventional commits
- [ ] Đã test chức năng mới
