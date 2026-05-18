# Quizzy

## Task Milne Par Step-by-Step Git Workflow

Jab bhi tumhe koi naya task mile, pehle apni fork repo ko main repo ke latest changes se update karo. Uske baad task ke liye alag branch banao.

### 1. Project folder open karo

```bash
cd path/to/Quizzy
```

Example:

```bash
cd c:/Users/asus/OneDrive/Desktop/Quizzy
```

### 2. Main branch par jao

```bash
git switch main
```

### 3. Main repo aur apni fork ke latest changes lao

```bash
git fetch upstream
git fetch origin
```

### 4. Apni local main branch update karo

```bash
git pull origin main
git merge upstream/main
```

Agar merge ke baad koi conflict aaye, to conflict files fix karo, phir:

```bash
git add .
git commit
```

### 5. Updated main ko apni fork par push karo

```bash
git push origin main
```

### 6. Task ke liye nayi branch banao

Branch ka naam task ke hisaab se rakho.

```bash
git switch -c feature/task-name
```

Example:

```bash
git switch -c feature/test-service-repository
```

### 7. Code changes karo

Task ke according files edit karo aur feature/fix complete karo.

### 8. Check karo kya-kya change hua

```bash
git status
```

### 9. Changes stage karo

```bash
git add .
```

### 10. Commit banao

Feature ke liye:

```bash
git commit -m "feat: add test service repository"
```

Bug fix ke liye:

```bash
git commit -m "fix: resolve repository issue"
```

Docs change ke liye:

```bash
git commit -m "docs: update readme"
```

### 11. Branch ko apni fork par push karo

```bash
git push -u origin feature/task-name
```

Example:

```bash
git push -u origin feature/test-service-repository
```

### 12. Pull Request banao

Push ke baad terminal me GitHub PR link aa sakta hai. Us link ko open karo aur PR create karo.

## Useful Commands

Current branch check karne ke liye:

```bash
git branch
```

Repo ka status check karne ke liye:

```bash
git status
```

Recent commits dekhne ke liye:

```bash
git log --oneline -5
```

Remote repositories check karne ke liye:

```bash
git remote -v
```

## Golden Rule

Direct `main` branch par task ka kaam mat karo. Har task ke liye:

1. Pehle `main` update karo.
2. Phir `main` se nayi branch banao.
3. Kaam complete karke branch push karo.
4. GitHub par Pull Request banao.
